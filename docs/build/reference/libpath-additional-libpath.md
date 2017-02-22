---
title: "/LIBPATH (追加ライブラリのパス) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/libpath"
  - "VC.Project.VCLinkerTool.AdditionalLibraryDirectories"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LIBPATH リンカー オプション"
  - "追加のライブラリ パス リンカー オプション"
  - "環境ライブラリ パスのオーバーライド"
  - "LIBPATH リンカー オプション"
  - "-LIBPATH リンカー オプション"
  - "ライブラリのパス リンカー オプション"
ms.assetid: 7240af0b-9a3d-4d53-8169-2a92cd6958ba
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /LIBPATH (追加ライブラリのパス)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LIBPATH:dir  
```  
  
## 解説  
 それぞれの文字について以下に説明します。  
  
 `dir`  
 環境変数 LIB で指定されたパスよりも前に検索するパスを指定します。  
  
## 解説  
 \/LIBPATH オプションは、環境ライブラリ パスをオーバーライドします。  まず、このオプションで指定されたパスで検索し、次に環境変数 LIB で指定されたパスで検索します。  入力する \/LIBPATH オプションごとに、1 つのディレクトリしか指定できません。  複数のディレクトリを指定する場合は、ディレクトリごとに \/LIBPATH オプションを指定します。  リンカーは、指定された順でディレクトリを検索します。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  \[全般\] プロパティ ページをクリックします。  
  
4.  \[追加のライブラリ ディレクトリ\] プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalLibraryDirectories%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)