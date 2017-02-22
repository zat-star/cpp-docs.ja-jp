---
title: "ARM Assembler Diagnostic Messages | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 52b38267-6023-4bdc-a0ef-863362f48eec
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ARM Assembler Diagnostic Messages
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

マイクロソフトの ARM アセンブラー \(*armasm*\)、それらを検出すると診断の警告およびエラーを出力します。  この資料では、最もよく発生するメッセージについて説明します。  
  
## 構文  
  
```  
  
filename(lineno) : [error|warning] Anum: message  
```  
  
## 診断メッセージ  
  
### \[エラー\]  
 A2193: この命令予測できない現象が生成されます。  
 ARM アーキテクチャは、この命令を実行したときの動作を保証できません。  この命令の明確な形式の詳細についてを参照してください、 [ARM アーキテクチャ マニュアル](http://go.microsoft.com/fwlink/?LinkId=246464)。  
  
```  
  
ADD r0, r8, pc         ; A2193: this instruction generates unpredictable behavior  
  
```  
  
 A2196: 16 ビットの命令をエンコードできません。  
 指定された命令は 16 ビットの Thumb 命令としてエンコードできません。  32 ビットの命令を指定またはターゲット ラベルに範囲の 16 ビットの命令を表示するためのコードの配置を変更します。  
  
 エンコードに対応させる、32 ビットの分岐であるにもかかわらず、アセンブラー分岐では、16 ビットをエンコードして、このエラーが発生する場合は、失敗しようとします。  この問題を解決するには使用して、 `.W` 32 ビットとして分岐を明示的に示すには、指定子。  
  
```  
  
  ADD.N r0, r1, r2      ; A2196: instruction cannot be encoded in 16 bits  
  
  B.W label             ; OK  
  B.N label             ; A2196: instruction cannot be encoded in 16 bits  
  SPACE 10000  
label  
  
```  
  
 A2202: サムの領域では使用できません事前 UAL 命令構文  
 スクロール ボックスのコードは、アセンブラー言語の統合 \(UAL\) 構文を使用する必要があります。  古い構文は受け付けられません  
  
```  
  
ADDEQS r0, r1         ; A2202: Pre-UAL instruction syntax not allowed in THUMB region  
ADDSEQ r0, r1         ; OK  
  
```  
  
 A2513: 回転をもする必要があります。  
 ARM モードでは、定数を指定する、代替構文があります。  書き込みではなく`#<const>`、書き込むことができます`#<byte>,#<rot>`、値を回転させることによって得られる定数値を表す`<byte>`で`<rot>`。  この構文を使用するの値をする必要があります`<rot>`も。  
  
```  
  
MOV r0, #4, #2       ; OK  
MOV r0, #4, #1       ; A2513: Rotation must be even  
  
```  
  
 A2557: のバックアップに書き込まれるバイトの数が正しくありません。  
 ネオンの構造をロードし、ストアの手順 \(`VLDn`、 `VSTn`\)、基本レジスタへの書き戻しを指定する、代替構文があります。  アドレスの後ろに感嘆符 \(\!\) を配置するのではなく、基本レジスタに追加するオフセットを示す即時の値を指定できます。  この構文を使用する場合は、ロードや、命令によって格納されたバイト数を指定してください。  
  
```  
  
VLD1.8 {d0-d3}, [r0]!         ; OK  
VLD1.8 {d0-d3}, [r0], #32     ; OK  
VLD1.8 {d0-d3}, [r0], #100    ; A2557: Incorrect number of bytes to write back  
  
```  
  
### 警告  
 A4228: 領域の配置位置揃えの値を超えています。 保証の配置  
 指定した配置、 `ALIGN`ディレクティブは、すぐ外側の配置よりも大きい`AREA`。  結果として、アセンブラーは保証できない、 `ALIGN`ディレクティブは無視されます。  
  
 この問題を解決するには、上で指定できます、 `AREA`ディレクティブは、 `ALIGN`が配置を希望以上の属性。  
  
```  
  
AREA |.myarea1|  
ALIGN 8           ; A4228: Alignment value exceeds AREA alignment; alignment not guaranteed  
  
AREA |.myarea2|,ALIGN=3  
ALIGN 8           ; OK  
  
```  
  
 A4508: この回転の定数の使用は使用されなくなりました  
 ARM モードでは、定数を指定する、代替構文があります。  書き込みではなく`#<const>`、書き込むことができます`#<byte>,#<rot>`、値を回転させることによって得られる定数値を表す`<byte>`で`<rot>`。  一部のコンテキストでは、ARM回転定数の使用を廃止します。  このような場合は、基本を使用して`#<const>`の構文ではなく。  
  
```  
  
ANDS r0, r0, #1                ; OK  
ANDS r0, r0, #4, #2            ; A4508: Use of this rotated constant is deprecated  
  
```  
  
 A4509: このフォームの条件付きの命令は。  
 この種の条件付きの命令によってARMv8 アーキテクチャで廃止されました。  条件分岐を使用すると、コードを変更することをお勧めします。  どの条件の命令がサポートされているを確認するを参照してください、 [ARM アーキテクチャ マニュアル](http://go.microsoft.com/fwlink/?LinkId=246464)。  
  
 この警告ではありませんが発生、  `- oldit` コマンド ライン スイッチを使用します。  
  
```  
  
ADDEQ r0, r1, r8              ; A4509: This form of conditional instruction is deprecated  
  
```  
  
## 参照  
 [ARM Assembler Command\-Line Reference](../../assembler/arm/arm-assembler-command-line-reference.md)   
 [ARM Assembler Directives](../../assembler/arm/arm-assembler-directives.md)