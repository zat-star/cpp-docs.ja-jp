---
title: "/GH (_pexit フック関数の有効化) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_pexit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gh コンパイラ オプション [C++]"
  - "_pexit 関数"
  - "Gh コンパイラ オプション [C++]"
  - "-Gh コンパイラ オプション [C++]"
ms.assetid: 93181453-2676-42e5-bf63-3b19e07299b6
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /GH (_pexit フック関数の有効化)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

すべてのメソッドまたは関数の最後に `_pexit`  関数を呼び出します。  
  
## 構文  
  
```  
/GH  
```  
  
## 解説  
 `_pexit`  関数はライブラリ関数ではなく、`_pexit` の定義はユーザー自身が行います。  
  
 `_pexit` 関数のプロトタイプを宣言する必要があるのは、\_pexit 関数を明示的に呼び出す場合だけです。  この関数は、次に示すプロトタイプがあらかじめ宣言されているものとして記述します。この関数では、呼び出し元から制御が渡された時点ですべてのレジスタの内容をプッシュし、呼び出し元に制御を返す時点でそれをポップして元の状況に戻す必要があります。  
  
```  
void __declspec(naked) _cdecl _pexit( void );  
```  
  
 `_pexit` と `_penter` は類似しています。`_pexit` 関数の書き方の例については、「[\/Gh \(\_penter フック関数の有効化\)](../../build/reference/gh-enable-penter-hook-function.md)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  \[追加のオプション\]ボックスにコンパイラ オプションを入力します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)