---
title: "/C (プリプロセス時のコメントの保持) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.KeepComments"
  - "/c"
  - "VC.Project.VCCLWCECompilerTool.KeepComments"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/c コンパイラ オプション [C++]"
  - "c コンパイラ オプション [C++]"
  - "-c コンパイラ オプション [C++]"
  - "コメント, 取り除かない (プリプロセス時に)"
  - "保持 (プリプロセス時にコメントを)"
ms.assetid: 944567ca-16bc-4728-befe-d414a7787f26
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /C (プリプロセス時のコメントの保持)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プリプロセス時にコメントを保持します。  
  
## 構文  
  
```  
/C  
```  
  
## 解説  
 このコンパイラ オプションには、**\/E**、**\/P**、または **\/EP** のいずれかのオプションが必要です。  
  
 次のコード例は、ソース コードのコメントを表示します。  
  
```  
// C_compiler_option.cpp  
// compile with: /E /C /c  
int i;   // a variable  
```  
  
 この例の出力は次のようになります。  
  
```  
#line 1 "C_compiler_option.cpp"  
int i;   // a variable  
```  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[プリプロセッサ\]** プロパティ ページをクリックします。  
  
4.  **\[コメントを残す\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.KeepComments%2A>」を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)   
 [\/E \(プリプロセス出力の標準出力へのコピー\)](../../build/reference/e-preprocess-to-stdout.md)   
 [\/P \(プリプロセス出力のファイルへの書き込み\)](../../build/reference/p-preprocess-to-a-file.md)   
 [\/EP \(\#line ディレクティブを挿入しない stdout へのプリプロセス\)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)