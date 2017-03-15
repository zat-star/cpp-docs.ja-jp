---
title: "/EP (#line ディレクティブを挿入しない stdout へのプリプロセス) | Microsoft Docs"
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
  - "/ep"
  - "VC.Project.VCCLCompilerTool.GeneratePreprocessedFileNoLines"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/EP コンパイラ オプション [C++]"
  - "コピー (プリプロセッサの出力を標準出力に)"
  - "EP コンパイラ オプション [C++]"
  - "-EP コンパイラ オプション [C++]"
  - "プリプロセッサ出力, コピー (標準出力に)"
ms.assetid: 6ec411ae-e33d-4ef5-956e-0054635eabea
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /EP (#line ディレクティブを挿入しない stdout へのプリプロセス)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C と C\+\+ のソース ファイルに対してプリプロセスが実行され、プリプロセスされたファイルが標準出力デバイスにコピーされます。  
  
## 構文  
  
```  
/EP  
```  
  
## 解説  
 プロセスでは、すべてのプリプロセッサ ディレクティブが実行され、マクロ拡張が実行されて、コメントが削除されます。  プリプロセスの出力のコメントを保持するには、[\/C \(プリプロセス時のコメントの保持\)](../../build/reference/c-preserve-comments-during-preprocessing.md) オプションと **\/EP** オプションを併用します。  
  
 **\/EP** オプションはコンパイルを中止します。  プリプロセス済みファイルをコンパイルに再送信する必要があります。  また **\/EP** は、**\/FA**、**\/Fa**、および **\/Fm** の各オプションによる出力ファイルも出力しません。  詳細については、「[\/FA、\/Fa \(リスティング ファイル\)](../../build/reference/fa-fa-listing-file.md)」および「[\/Fm \(マップ ファイルの名前の指定\)](../Topic/-Fm%20\(Name%20Mapfile\).md)」を参照してください。  
  
 処理の後半で生成されたエラーは、元のソース ファイルではなく、プリプロセス済みファイルの行番号を参照します。  元のソース ファイルの行番号を参照するには、代わりに [\/E \(プリプロセス出力の標準出力へのコピー\)](../../build/reference/e-preprocess-to-stdout.md) を使用します。  **\/E** オプションを指定すると、`#line` ディレクティブが出力に挿入されるため、エラーの発生した場所が見つかりやすくなります。  
  
 `#line` ディレクティブを使ったプリプロセス済みの出力を任意のファイルに送るには、[\/P \(プリプロセス出力のファイルへの書き込み\)](../../build/reference/p-preprocess-to-a-file.md) オプションを使用します。  
  
 `#line` ディレクティブを使ったプリプロセス済みの出力を標準出力に送るには、**\/P** と **\/EP** を併用します。  
  
 **\/EP** オプションでは、プリコンパイル済みヘッダーは使用できません。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[プリプロセッサ\]** プロパティ ページをクリックします。  
  
4.  **\[プリプロセス ファイルの生成\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>」を参照してください。  
  
## 使用例  
 次のコマンド ラインは、`ADD.C` ファイルをプリプロセスし、コメントを保持し、結果を標準出力デバイスに表示します。  
  
```  
CL /EP /C ADD.C  
```  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)