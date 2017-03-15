---
title: "[全般] ([&lt;プロジェクト名&gt; プロパティ ページ] ダイアログ ボックス - [構成プロパティ] - [マニフェスト ツール]) | Microsoft Docs"
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
  - "VC.Project.VCManifestTool.MergeRulesFile"
  - "VC.Project.VCManifestTool.UseUnicodeResponseFiles"
  - "VC.Project.VCManifestTool.SuppressStartupBanner"
  - "VC.Project.VCManifestTool.UseFAT32Workaround"
  - "VC.Project.VCManifestTool.VerboseOutput"
  - "VC.Project.VCManifestTool.AssemblyIdentity"
dev_langs: 
  - "C++"
ms.assetid: b99368a5-6819-482c-a06e-f2409290cfd1
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# [全般] ([&lt;プロジェクト名&gt; プロパティ ページ] ダイアログ ボックス - [構成プロパティ] - [マニフェスト ツール])
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このダイアログ ボックスを使用して、[Mt.exe](http://msdn.microsoft.com/library/aa375649) の全般的なオプションを指定します。  
  
 このプロパティ ページ ダイアログ ボックスを表示するには、プロジェクトまたはプロパティ シートのプロパティ ページを開きます。  **\[構成プロパティ\]** の **\[マニフェスト ツール\]** ノードを展開し、**\[全般\]** をクリックします。  
  
## UIElement の一覧  
 **\[著作権情報の非表示\]**  
 **\[はい \(\/NOLOGO\)\]** にすると、マニフェスト ツールの起動時に、標準の Microsoft 著作権データが表示されません。  ビルド処理の一環として、またはビルド環境から mt.exe を実行するときに、ログ ファイルに不必要な出力を行わない場合は、このオプションを使用します。  
  
 **\[Verbose 出力\]**  
 **\[はい \(\/verbose\)\]** にすると、マニフェストの生成時に、追加のビルド情報が表示されます。  
  
 **\[アセンブリ ID\]**  
 \/identity オプションを使用して、[\<assemblyIdentity\> 要素](../Topic/%3CassemblyIdentity%3E%20Element%20\(ClickOnce%20Application\).md) の属性で構成される ID 文字列を指定します。  ID 文字列は、`name` 属性の値で始まり、*attribute* \= *value* ペアが続きます。  ID 文字列内の属性は、コンマで区切ります。  
  
 ID 文字列の例を次に示します。  
  
 `Microsoft.Windows.Common-Controls, processorArchitecture=x86, version=6.0.0.0, type=win32, publicKeyToken=6595b64144ccf1df`  
  
## 参照  
 [ClickOnce アプリケーション マニフェスト](../Topic/ClickOnce%20Application%20Manifest.md)   
 [マニフェスト ツールのプロパティ ページ](../ide/manifest-tool-property-pages.md)   
 [方法 : プロジェクト プロパティ ページを開く](../misc/how-to-open-project-property-pages.md)   
 [方法 : プロジェクトのプロパティ シートを編集する](../misc/how-to-edit-project-property-sheets.md)