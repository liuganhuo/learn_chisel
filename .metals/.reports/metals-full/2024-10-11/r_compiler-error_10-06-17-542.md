file://<WORKSPACE>/src/main/scala/Consts.scala
### java.lang.IndexOutOfBoundsException: 0

occurred in the presentation compiler.

presentation compiler configuration:
Scala version: 3.3.3
Classpath:
<HOME>/.cache/coursier/v1/https/repo1.maven.org/maven2/org/scala-lang/scala3-library_3/3.3.3/scala3-library_3-3.3.3.jar [exists ], <HOME>/.cache/coursier/v1/https/repo1.maven.org/maven2/org/scala-lang/scala-library/2.13.12/scala-library-2.13.12.jar [exists ]
Options:



action parameters:
offset: 1408
uri: file://<WORKSPACE>/src/main/scala/Consts.scala
text:
```scala
package common

import chisel3._
import chisel3.util._

object Consts {
    val WORD_LEN            = 32
    val START_ADDR          = 0.U(WORD_LEN.W)

    val EXE_FUN_LEN         = 5
    val ALU_X               = 0.U(EXE_FUN_LEN.W)
    val ALU_ADD             = 0.U(EXE_FUN_LEN.W)
    val ALU_SUB             = 0.U(EXE_FUN_LEN.W)
    val ALU_AND             = 0.U(EXE_FUN_LEN.W)
    val ALU_OR              = 0.U(EXE_FUN_LEN.W)
    val ALU_XOR             = 0.U(EXE_FUN_LEN.W)
    val ALU_SLL             = 0.U(EXE_FUN_LEN.W)
    val ALU_SRL             = 0.U(EXE_FUN_LEN.W)
    val ALU_SRA             = 0.U(EXE_FUN_LEN.W)
    val ALU_SLT             = 0.U(EXE_FUN_LEN.W)
    val ALU_SLTU            = 0.U(EXE_FUN_LEN.W)
    val BR_BEQ              = 0.U(EXE_FUN_LEN.W)
    val BR_BNE              = 0.U(EXE_FUN_LEN.W)
    val BR_BLT              = 0.U(EXE_FUN_LEN.W)
    val BR_BGE              = 0.U(EXE_FUN_LEN.W)
    val BR_BLTU             = 0.U(EXE_FUN_LEN.W)
    val BR_BGEU             = 0.U(EXE_FUN_LEN.W)
    val ALU_JALR            = 0.U(EXE_FUN_LEN.W)
    val ALU_COPY1           = 0.U(EXE_FUN_LEN.W)
    val ALU_VADDVV          = 0.U(EXE_FUN_LEN.W)
    val VSET                = 0.U(EXE_FUN_LEN.W)
    val ALU_PCNT            = 0.U(EXE_FUN_LEN.W)

    val OP1_LEN             = 2
    val OP1_RS1             = 0.U(OP1_LEN.W)

    val OP2_LEN             = 3
    val OP2_RS2             = 1.U()@@

}
```



#### Error stacktrace:

```
scala.collection.LinearSeqOps.apply(LinearSeq.scala:131)
	scala.collection.LinearSeqOps.apply$(LinearSeq.scala:128)
	scala.collection.immutable.List.apply(List.scala:79)
	dotty.tools.dotc.util.Signatures$.countParams(Signatures.scala:501)
	dotty.tools.dotc.util.Signatures$.applyCallInfo(Signatures.scala:186)
	dotty.tools.dotc.util.Signatures$.computeSignatureHelp(Signatures.scala:94)
	dotty.tools.dotc.util.Signatures$.signatureHelp(Signatures.scala:63)
	scala.meta.internal.pc.MetalsSignatures$.signatures(MetalsSignatures.scala:17)
	scala.meta.internal.pc.SignatureHelpProvider$.signatureHelp(SignatureHelpProvider.scala:51)
	scala.meta.internal.pc.ScalaPresentationCompiler.signatureHelp$$anonfun$1(ScalaPresentationCompiler.scala:435)
```
#### Short summary: 

java.lang.IndexOutOfBoundsException: 0