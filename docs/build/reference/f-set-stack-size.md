---
title: "/F (スタック サイズの設定) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/f"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/F コンパイラ オプション [C++]"
  - "F コンパイラ オプション [C++]"
  - "-F コンパイラ オプション [C++]"
  - "設定 (スタック サイズの) コンパイラ オプション"
  - "スタック, 設定 (サイズの)"
ms.assetid: 17320b6f-8305-445b-9ec2-75833f4b29e0
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /F (スタック サイズの設定)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プログラムのスタック サイズをバイト単位で設定します。  
  
## 構文  
  
```  
/F number  
```  
  
## Arguments  
 `number`  
 スタック サイズのバイト数。  
  
## 解説  
 このオプションを指定しない場合、スタック サイズは既定で 1 MB に設定されます。  引数 `number` は、10 進表記または C 言語表記で指定できます。  この引数の範囲は、1 からリンカーの最大許容スタック サイズまでです。  指定した値は、4 バイト単位に切り上げられます。  **\/F** と `number` の間の空白は省略可能です。  
  
 スタック オーバーフロー メッセージが返された場合は、スタック サイズを増やしてください。  
  
 スタック サイズは、次の方法で設定することもできます。  
  
-   **\/STACK** リンカー オプションを使用する。  詳細については、「[\/STACK](../../build/reference/stack.md)」を参照してください。  
  
-   .exe ファイルで EDITBIN を使用する。  詳細については、「[EDITBIN リファレンス](../Topic/EDITBIN%20Reference.md)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  **\[追加のオプション\]** ボックスにコンパイラ オプションを入力します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)