---
title: "/Qsafe_fp_loads | Microsoft Docs"
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
ms.assetid: 2b2ce52d-ba57-4bd3-a739-47a7f8bfaba9
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /Qsafe_fp_loads
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

浮動小数点値の整数移動命令を要求し、特定の浮動小数点読み込み最適化を無効にします。  
  
## 構文  
  
```  
/Qsafe_fp_loads  
```  
  
## 解説  
 **\/Qsafe\_fp\_loads** は、x86 を対象とするコンパイラでのみ使用でき、x64 または ARM を対象とするコンパイラでは使用できません。  
  
 **\/Qsafe\_fp\_loads** を指定すると、コンパイル時、浮動小数点移動命令ではなく整数移動命令を使用して、メモリと MMX レジスタとの間でデータが移動されます。  また、このオプションを指定すると、値の読み込み時に例外が発生する可能性がある場合 \(NaN 値の読み込み時など\)、複数のコントロール パスに読み込める浮動小数点値に対してレジスタ読み込み最適化が無効になります。  
  
 このオプションは [\/fp:except](../../build/reference/fp-specify-floating-point-behavior.md) でオーバーライドされます。  **\/Qsafe\_fp\_loads** では、**\/fp:except** で指定したコンパイラの動作のサブセットを指定します。  
  
 **\/Qsafe\_fp\_loads** は [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) および [\/fp:fast](../../build/reference/fp-specify-floating-point-behavior.md) と互換性がありません。  浮動小数点コンパイラ オプションの詳細については、「[\/fp \(浮動小数点の動作の指定\)](../../build/reference/fp-specify-floating-point-behavior.md)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーを選択します。  
  
3.  **\[コマンド ライン\]** プロパティ ページを選択します。  
  
4.  **\[追加のオプション\]** ボックスにコンパイラ オプションを入力します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> を参照してください。  
  
## 参照  
 [\/Q オプション \(低水準の操作\)](../../build/reference/q-options-low-level-operations.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)