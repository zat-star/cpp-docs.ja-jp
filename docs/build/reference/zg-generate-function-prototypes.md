---
title: "/Zg (関数プロトタイプの生成) | Microsoft Docs"
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
  - "/zg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zg コンパイラ オプション [C++]"
  - "関数プロトタイプ, 生成 (関数プロトタイプを) コンパイラ オプション"
  - "生成 (関数プロトタイプを) コンパイラ オプション"
  - "Zg コンパイラ オプション [C++]"
  - "-Zg コンパイラ オプション [C++]"
ms.assetid: c8df1b46-24ff-46f2-8356-e0a144b21dd2
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zg (関数プロトタイプの生成)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

削除されました。 ソース ファイルで定義された各関数の関数プロトタイプを作成しますが、ソース ファイルはコンパイルされません。  
  
## 構文  
  
```  
/Zg  
```  
  
## 解説  
 このコンパイラ オプションは使用できなくなりました。 Visual C\+\+ 2015 で削除されました。 このページは、前のバージョンの Visual C\+\+ のユーザーのために残されています。  
  
 関数プロトタイプには、この関数の戻り値の型と引数の型リストが含まれます。 引数の型リストは、関数の仮パラメーターの型から作成されます。 ソース ファイル内に既に存在する関数プロトタイプは無視されます。  
  
 プロトタイプのリストは、標準出力に書き込まれます。 このリストは、関数の実際の引数と仮パラメーターに互換性があることを確認するのに役立ちます。 標準出力をファイルにリダイレクトすることで、リストを保存できます。 その後 **\#include** を使って、関数プロトタイプのリストをソース ファイルの一部にすることができます。 これにより、コンパイラは引数の型チェックを実行できます。  
  
 **\/Zg** オプションを使っており、構造体型、列挙型、共用体型 \(またはそのような型へのポインター\) を持つ仮パラメーターがプログラムに含まれる場合、各構造体型、列挙型、共用体型の宣言にはタグ \(名前\) が必要です。 次の例で、タグ名は `MyStruct` です。  
  
```  
// Zg_compiler_option.c  
// compile with: /Zg  
typedef struct MyStruct { int i; } T2;  
void f2(T2 * t) {}  
```  
  
 **\/Zg** は使用されなくなりました。 Visual C\+\+ コンパイラでは、以前の C スタイル コードへのサポートが削除される予定です。 詳しくは、「[Visual C\+\+ 2005 で使用されなくなったコンパイラ オプション](http://msdn.microsoft.com/ja-jp/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce)」をご覧ください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。 詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  \[追加のオプション\]ボックスにコンパイラ オプションを入力します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)