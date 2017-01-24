---
title: "ARM Assembler Command-Line Reference | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: f7b89478-1ab5-4995-8cde-a805f0462c45
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ARM Assembler Command-Line Reference
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

この資料で、マイクロソフトの ARM アセンブラーのコマンドラインについての提供 *armasm*は、マイクロソフトの実装の一般的なオブジェクト ファイルの形式 \(COFF\) に ARMv7 サムのアセンブリ言語をコンパイルします。  リンカーは、COFF のコードでは、ARM アセンブラーまたはライブラリアンで作成されるオブジェクト ライブラリと、C のコンパイラによって生成されたオブジェクト コードをリンクできます。  
  
## 構文  
  
```  
armasm [[options]] sourcefile objectfile  
```  
  
```  
armasm [[options]] -o objectfile sourcefile  
```  
  
#### パラメーター  
 `options`  
 \-エラー`filename`  
 エラー メッセージと警告メッセージにリダイレクト`filename`。  
  
 ・ i`dir[;dir]`  
 インクルード検索パスに指定されたディレクトリを追加します。  
  
 \-事前定義`directive`  
 シンボルをあらかじめ定義するセット、SETL、またはセットのディレクティブを指定します。  例 : **armasm.exe \-predefine "COUNT SETA 150" source.asm**。  詳細についてを参照してください、 [ARM アセンブラー ツール ガイド](http://go.microsoft.com/fwlink/?LinkId=246102)。  
  
 nowarn\-  
 すべての警告メッセージを無効にします。  
  
 \-を無視します。`warning`  
 指定された警告を無効にします。  可能な値は、警告についての説明を参照してください。  
  
 \-ヘルプ  
 コマンドラインのヘルプ メッセージを印刷します。  
  
 ・ マシン`machine`  
 PE ヘッダーに設定するのには、コンピューターの種類を指定します。  値`machine`です。   
**ARM**\-IMAGE\_FILE\_MACHINE\_ARMNT するには、コンピューターの種類を設定します。  これは、既定の設定です。   
**THUMB**\-IMAGE\_FILE\_MACHINE\_THUMB するには、コンピューターの種類を設定します。  
  
 \-oldit  
 ARMv7 スタイルを生成する IT ブロックします。  既定では、ARMv8 と互換性のある IT ブロック生成されます。  
  
 \-を介して`filename`  
 追加のコマンドライン引数を読み取る`filename`。  
  
 \-16  
 16 ビット Thumb 命令をアセンブルするソース。  これは、既定の設定です。  
  
 \-32  
 32 ビット ARM 命令をアセンブルするソース。  
  
 ・ g  
 デバッグ情報を生成します。  
  
 \-errorReport。`option`  
 どのように内部のアセンブラー エラーを Microsoft に報告されるを指定します。  値`option`です。   
**none**— レポートを送信しません。  
**prompt**\-すぐにレポートを送信すると、ユーザー プロンプトを表示します。  
**queue**\-次への管理ログオン時にレポートを送信するのには、ユーザー プロンプトを表示します。  これは、既定の設定です。   
**send**\-自動的にレポートを送信します。  
  
 `sourcefile`  
 ソース ファイルの名前。  
  
 `objectfile`  
 オブジェクト \(出力\) ファイルの名前。  
  
 一般的なシナリオでは、armasm を使用する方法の例を次に示します。  まず、armasm を使用して、アセンブリ言語ソース \(.asm\) ファイルをオブジェクト \(.obj\) ファイルを作成します。  CL コマンドライン C コンパイラを使用して、ソース \(.c\) ファイルをコンパイルするしARMのオブジェクト ファイルをリンクするには、リンカー オプションも指定します。  
  
 **armasm myasmcode.asm \-o myasmcode.obj**  
  
 **cl myccode.c \/link myasmcode.obj**  
  
## 参照  
 [ARM Assembler Diagnostic Messages](../../assembler/arm/arm-assembler-diagnostic-messages.md)   
 [ARM Assembler Directives](../../assembler/arm/arm-assembler-directives.md)