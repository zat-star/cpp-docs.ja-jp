---
title: "/MANIFESTFILE (マニフェスト ファイルに名前を付ける) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.ManifestFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MANIFESTFILE リンカー オプション"
  - "MANIFESTFILE リンカー オプション"
  - "-MANIFESTFILE リンカー オプション"
ms.assetid: befa5ab2-a9cf-4c9b-969a-e7b4a930f08d
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /MANIFESTFILE (マニフェスト ファイルに名前を付ける)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MANIFESTFILE:filename  
```  
  
## 解説  
 \/MANIFESTFILE を指定すると、マニフェスト ファイルの既定の名前を変更できます。マニフェスト ファイルの既定の名前は、ファイル名に .manifest を付け加えたものです。  
  
 \/MANIFESTFILE は、リンクでさらに [\/MANIFEST](../../build/reference/manifest-create-side-by-side-assembly-manifest.md) を指定していない場合は無効です。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[構成プロパティ\]** ノードを展開します。  
  
3.  **\[リンカー\]** ノードを展開します。  
  
4.  **\[マニフェスト ファイル\]** プロパティ ページをクリックします。  
  
5.  **\[マニフェスト ファイル\]** プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ManifestFile%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)