---
title: "/X (標準インクルード パスの無視) | Microsoft Docs"
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
  - "/x"
  - "VC.Project.VCCLCompilerTool.IgnoreStandardIncludePath"
  - "VC.Project.VCCLWCECompilerTool.IgnoreStandardIncludePath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/X コンパイラ オプション [C++]"
  - "無視 (標準インクルード パスを) コンパイラ オプション"
  - "インクルード ディレクトリ, 無視 (標準を)"
  - "インクルード ファイル, 無視 (標準パスを)"
  - "X コンパイラ オプション"
  - "-X コンパイラ オプション [C++]"
ms.assetid: 16bdf2cc-c8dc-46e4-bdcc-f3caeba5e1ef
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /X (標準インクルード パスの無視)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

環境変数 PATH と INCLUDE で指定されたディレクトリ内でインクルード ファイルが検索されなくなります。  
  
## 構文  
  
```  
/X  
```  
  
## 解説  
 このオプションは [\/I \(追加インクルード ディレクトリ\)](../../build/reference/i-additional-include-directories.md) \(**\/I**`directory`\) オプションと併用できます。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[プリプロセッサ\]** プロパティ ページをクリックします。  
  
4.  **\[標準インクルード パスの無視\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.IgnoreStandardIncludePath%2A>」を参照してください。  
  
## 使用例  
 次のコマンドは、`/X` オプションにより、環境変数 PATH と INCLUDE で指定された場所を無視し、`/I` で指定されたディレクトリでインクルード ファイルを検索します。  
  
```  
CL /X /I \ALT\INCLUDE MAIN.C  
```  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)