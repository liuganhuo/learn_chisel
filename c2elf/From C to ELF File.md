# From C to ELF File



#### 先将C源代码编译为可重定位文件(.o)

-march指定了指令集架构

-mabi指定了使用的 ABI（Application Binary Interface），它定义了如何在函数调用、参数传递等方面进行二进制接口的标准。

- `ilp32` 表示整数、长整数和指针都是32位。

```bash
riscv64-unknown-elf-gcc -march=rv32i -mabi=ilp32 -c -o test.o test.c 
```

也可以获得中间过程的汇编代码

```bash
riscv64-unknown-elf-gcc -march=rv32i -mabi=ilp32 -c -S test.c 
```



#### 再进行链接操作获得可知性文件

与link.ld进行链接。

`-b elf32-littleriscv`指定了输出文件的格式。`elf32-littleriscv` 表示生成一个32位的 Little-Endian 格式的 ELF 文件，适用于 RISC-V 架构。

```bash
riscv64-unknown-elf-ld -b elf32-littleriscv test.o -T link.ld  -o test
```



#### 将可执行文件转化为二进制文件，最后在到十六进制文件

先转化为二进制

```
riscv64-unknown-elf-objcopy -O binary test test.bin
```

- 也可以用该指令将可执行文件转化回汇编：`riscv64-unknown-elf-objdump -b elf32-littleriscv -D test > test.elf.dmp`

再转化为十六进制

- `-An`: 这个选项指定了不输出地址信息。
- `-tx1`: 这个选项指定了输出格式为十六进制，每个字节一组。
- `-w1`: 这个选项指定了每行输出一个字节。
- `-v`: 这个选项指示输出所有输入数据，包括重复的行

```
od -An -tx1 -w1 -v test.bin  > ./test.hex	
```



最终得到的该test.hex即可以直接运行在CPU上的文件。