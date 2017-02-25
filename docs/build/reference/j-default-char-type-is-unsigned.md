---
title: "/J (既定の char 型の unsigned への変更) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.DefaultCharIsUnsigned"
  - "VC.Project.VCCLWCECompilerTool.DefaultCharIsUnsigned"
  - "/j"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/J コンパイラ オプション [C++]"
  - "char 型"
  - "既定の char 型が符号なし"
  - "既定値, char 型"
  - "J コンパイラ オプション [C++]"
  - "-J コンパイラ オプション [C++]"
ms.assetid: 50973667-6638-491e-9c41-bff73acae19f
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# /J (既定の char 型の unsigned への変更)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`signed char` から `unsigned char`に既定の `char` の種類を変更し、`int` の型に拡大変換される場合 `char` の型はゼロ拡張されたです。  
  
## 構文  
  
```  
/J  
```  
  
## 解説  
 `char` 値が `signed`として明示的に宣言する場合は、**\/J** オプションは影響し、`int` の型に拡大変換される場合は、その値が印拡張されたです。  
  
 **\/J** オプションでは、識別子 `_CHAR_UNSIGNED` が定義されます。この識別子は、LIMITS.h ファイルの `#ifndef` で使用し、既定の `char` 型の範囲を定義します。  
  
 ANSI C と C\+\+ では、`char` 型の特別な実装は必要ありません。  \/J オプションが必要になるのは、最終的に英語以外の言語に翻訳する文字データを扱う場合です。  
  
> [!NOTE]
>  ATL\/MFC でこのコンパイラ オプションを使用すると、エラーが発生する場合があります。  `_ATL_ALLOW_CHAR_UNSIGNED`を定義することで、このエラーを無効にすることはできますが、この代替手段はサポートされず、常に動作しないことがあります。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  **\[ソリューション エクスプローラー\]** で、プロジェクトのショートカット メニューを開き、**\[プロパティ\]** をクリックします。  
  
2.  **\[構成プロパティ\]** の下の左ペインのプロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスで、**\[C\/C\+\+\]** を展開し、**\[コマンド ライン\]** を選択します。  
  
3.  **\[追加のオプション\]** ペインで、**\/J** コンパイラ オプションを指定します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DefaultCharIsUnsigned%2A>」を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)   
 [方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)