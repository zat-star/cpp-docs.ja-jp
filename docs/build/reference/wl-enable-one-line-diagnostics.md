---
title: "/WL (1 行診断の有効化) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/wl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/WL コンパイラ オプション [C++]"
  - "WL コンパイラ オプション [C++]"
  - "-WL コンパイラ オプション [C++]"
ms.assetid: 332cadb4-8ea6-45fe-b67d-33ddec1f2c2e
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /WL (1 行診断の有効化)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

エラー メッセージまたは警告メッセージに追加情報を表示します。  
  
## 構文  
  
```  
/WL  
```  
  
## 解説  
 C\+\+ コンパイラのエラー メッセージや警告メッセージに続けて、追加情報を表示できます。既定では、追加情報は新しい行に表示されます。  コマンド ラインからコンパイルする場合は、エラー メッセージや警告メッセージに追加情報の行を付加できます。  これは、ビルドの出力をログ ファイルに取り込み、そのログを処理してすべてのエラーや警告を見つける場合に便利です。  エラー メッセージおよび警告メッセージと追加の行の間には、セミコロンが挿入されます。  
  
 すべてのエラー メッセージと警告メッセージに追加情報の行があるとは限りません。  次のコードは、追加情報の行があるエラーを生成します。**\/WL** を使用した場合の効果をテストできます。  
  
```  
// compiler_option_WL.cpp  
// compile with: /WL  
#include <queue>  
int main() {  
   std::queue<int> q;  
   q.fromthecontinuum();   // C2039  
}  
```  
  
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