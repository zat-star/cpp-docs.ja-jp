---
title: "/MERGE (セクションの結合) | Microsoft Docs"
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
  - "/merge"
  - "VC.Project.VCLinkerTool.MergeSections"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MERGE リンカー オプション"
  - "MERGE リンカー オプション"
  - "-MERGE リンカー オプション"
  - "sections"
  - "sections, 結合"
  - "sections, 名前付け"
ms.assetid: 10fb20c2-0b3f-4c8d-98a8-f69aedf03d52
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /MERGE (セクションの結合)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MERGE:from=to  
```  
  
## 解説  
 \/MERGE オプションは、最初のセクション \(*from*\) と 2 番目のセクション \(*to*\) を結合し、結合後のセクションの名前を *to* にします。  たとえば、`/merge:.rdata=.text` のようにします。  
  
 2 番目のセクションがない場合は、*from* セクションの名前が *to* になります。  
  
 この \/MERGE オプションは、VxD を作成して、コンパイラが生成したセクション名を無効にするときに便利です。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  \[詳細\] プロパティ ページをクリックします。  
  
4.  \[セクションの結合\] プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergeSections%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)