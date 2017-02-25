---
title: "/Zs (構文のみチェック) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/zs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zs コンパイラ オプション [C++]"
  - "Syntax Check Only コンパイラ オプション"
  - "Zs コンパイラ オプション"
  - "-Zs コンパイラ オプション [C++]"
ms.assetid: b4b41e6a-3f41-4d09-9cb6-fde5aa2cfecf
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /Zs (構文のみチェック)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コマンド ラインで指定したソース ファイルの構文だけをチェックします。  
  
## 構文  
  
```  
/Zs  
```  
  
## 解説  
 このオプションを使用した場合、出力ファイルは作成されず、エラー メッセージが標準出力に書き込まれます。  
  
 **\/Zs** オプションを使うと、ソース ファイルのコンパイルとリンクを実行する前に、構文エラーをすぐに見つけて修正できます。  
  
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