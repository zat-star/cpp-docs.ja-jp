---
title: "/P (プリプロセス出力のファイルへの書き込み) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.GeneratePreprocessedFile"
  - "/p"
  - "VC.Project.VCCLWCECompilerTool.GeneratePreprocessedFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/P コンパイラ オプション [C++]"
  - "出力ファイル, プリプロセッサ"
  - "P コンパイラ オプション [C++]"
  - "-P コンパイラ オプション [C++]"
  - "プリプロセス (出力ファイルを)"
ms.assetid: 123ee54f-8219-4a6f-9876-4227023d83fc
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /P (プリプロセス出力のファイルへの書き込み)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C と C\+\+ のソース ファイルに対してプリプロセスが実行され、プリプロセス出力がファイルに書き込まれます。  
  
## 構文  
  
```  
/P  
```  
  
## 解説  
 ファイル名は、ソース ファイルの基本名に拡張子 .i が付加されます。  プロセスでは、すべてのプリプロセッサ ディレクティブが実行され、マクロ拡張が実行されて、コメントが削除されます。  プリプロセスの出力のコメントを保持するには、**\/P** オプションに加えて、[\/C \(プリプロセス時のコメントの保持\)](../../build/reference/c-preserve-comments-during-preprocessing.md) オプションも使用します。  
  
 **\/P** オプションを使用すると、出力される各インクルード ファイルの先頭と末尾に `#line` ディレクティブが挿入されます。また、条件付きコンパイルを指定するプリプロセッサ ディレクティブがある場合は、そのディレクティブで削除される行の前後にも挿入されます。  これらのディレクティブがあると、プリプロセス済みファイルの行番号が付け直されます。  その結果、処理の後半で生成されたエラーは、プリプロセス済みファイルの行番号ではなく、元のソース ファイルの行番号を参照します。  `#line` ディレクティブが生成されないようにするには、**\/P** に加えて [\/EP \(\#line ディレクティブを挿入しない stdout へのプリプロセス\)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) を使用します。  
  
 **\/P** オプションはコンパイルを中止します。  [\/Fo \(オブジェクト ファイルの名前の指定\)](../../build/reference/fo-object-file-name.md) を指定した場合でも .obj ファイルは生成されません。  プリプロセス済みファイルをコンパイルに再送信する必要があります。  また **\/P** は、**\/FA**、**\/Fa**、および **\/Fm** の各オプションによる出力ファイルも出力しません。  詳細については、「[\/FA、\/Fa \(リスティング ファイル\)](../../build/reference/fa-fa-listing-file.md)」および「[\/Fm \(マップ ファイルの名前の指定\)](../Topic/-Fm%20\(Name%20Mapfile\).md)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[プリプロセッサ\]** プロパティ ページをクリックします。  
  
4.  **\[プリプロセス ファイルの生成\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>」を参照してください。  
  
## 使用例  
 次のコマンド ラインは、`ADD.C` をプリプロセスし、コメントを保持し、`#line` ディレクティブを挿入し、結果を `ADD.I` というファイルに書き込みます。  
  
```  
CL /P /C ADD.C  
```  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)   
 [\/Fi \(出力ファイル名のプリプロセス\)](../../build/reference/fi-preprocess-output-file-name.md)