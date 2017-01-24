---
title: "/DEF (モジュール定義ファイルの指定) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.ModuleDefinitionFile"
  - "/def"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DEF リンカー オプション"
  - "DEF リンカー オプション"
  - "-DEF リンカー オプション"
  - "モジュール定義ファイル"
  - "モジュール定義ファイル, 指定"
ms.assetid: 6497fa68-65f0-48ca-8f66-b87166fc631a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /DEF (モジュール定義ファイルの指定)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DEF:filename  
```  
  
## 解説  
 それぞれの文字について以下に説明します。  
  
 *filename*  
 リンカーに渡すモジュール定義ファイル \(.def ファイル\) の名前。  
  
## 解説  
 \/DEF オプションは、モジュール定義ファイル \(.def ファイル\) をリンカーに渡します。  .def ファイルは 1 つしか LINK に指定できません。  .def ファイルについては、「[モジュール定義 \(.def\) ファイル](../Topic/Module-Definition%20\(.Def\)%20Files.md)」を参照してください。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  \[入力\] プロパティ ページをクリックします。  
  
4.  \[モジュール定義ファイル\] プロパティを変更します。  
  
 開発環境で .def ファイルを指定するには、ほかのファイルと一緒にプロジェクトに登録し、\/DEF オプションで指定します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ModuleDefinitionFile%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)