---
title: "/E (プリプロセス出力の標準出力へのコピー) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/e"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/E コンパイラ オプション [C++]"
  - "-E コンパイラ オプション [C++]"
  - "プリプロセッサ出力"
  - "プリプロセッサ出力, コピー (標準出力に)"
ms.assetid: ddbb1725-d950-4978-ab2f-30a5cd7b778c
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /E (プリプロセス出力の標準出力へのコピー)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C と C\+\+ のソース ファイルに対してプリプロセスが実行され、プリプロセスされたファイルが標準出力デバイスにコピーされます。  
  
## 構文  
  
```  
/E  
```  
  
## 解説  
 このプロセスでは、すべてのプリプロセッサ ディレクティブが実行され、マクロ拡張が実行されて、コメントが削除されます。  プリプロセスの出力のコメントを保持するには、[\/C \(プリプロセス時のコメントの保持\)](../../build/reference/c-preserve-comments-during-preprocessing.md) コンパイラ オプションも使用します。  
  
 **\/E** オプションを使用すると、出力される各インクルード ファイルの先頭と末尾に `#line` ディレクティブが挿入されます。また、条件付きコンパイルを指定するプリプロセッサ ディレクティブがある場合は、そのディレクティブで削除される行の前後にも挿入されます。  これらのディレクティブがあると、プリプロセス済みファイルの行番号が付け直されます。  その結果、処理の後半で生成されたエラーは、プリプロセス済みファイルの行番号ではなく、元のソース ファイルの行番号を参照します。  
  
 **\/E** オプションを指定すると、コンパイルが行われません。  プリプロセス済みファイルをコンパイルに再送信する必要があります。  また **\/E** は、**\/FA**、**\/Fa**、および **\/Fm** の各オプションによる出力ファイルも出力しません。  詳細については、「[\/FA、\/Fa \(リスティング ファイル\)](../../build/reference/fa-fa-listing-file.md)」および「[\/Fm \(マップ ファイルの名前の指定\)](../Topic/-Fm%20\(Name%20Mapfile\).md)」を参照してください。  
  
 `#line` ディレクティブが挿入されないようにするには、[\/EP \(\#line ディレクティブを挿入しない stdout へのプリプロセス\)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) オプションを使用します。  
  
 プリプロセスの出力を `stdout` ではなく、任意のファイルに送るには、[\/P \(プリプロセス出力のファイルへの書き込み\)](../../build/reference/p-preprocess-to-a-file.md) オプションを使用します。  
  
 `#line` ディレクティブを挿入せずにプリプロセスの出力を任意のファイルに送るには、**\/P** と **\/EP** を同時に使用します。  
  
 **\/E** オプションでは、プリコンパイル済みヘッダーは使用できません。  
  
 プリプロセスの出力を別のファイルに送る場合、トークンの後にスペースは挿入されません。  その結果、不正なプログラムまたは意図しない副作用が生じることがあります。  以下のプログラムは、正常にコンパイルされます。  
  
```  
#define m(x) x  
m(int)main( )  
{  
   return 0;  
}  
```  
  
 ただし、次のように指定すると、正しくコンパイルされません。  
  
```  
cl -E test.cpp > test2.cpp  
```  
  
 test2.cpp の `int main` は、`intmain` になります。これは正しくありません。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  **\[追加のオプション\]** ボックスにコンパイラ オプションを入力します 。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>」を参照してください。  
  
## 使用例  
 次のコマンド ラインは、`ADD.C` をプリプロセスし、コメントを保持し、`#line` ディレクティブを挿入し、結果を標準出力デバイスに表示します。  
  
```  
CL /E /C ADD.C  
```  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)