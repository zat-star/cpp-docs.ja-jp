---
title: "[分離された COM] ([&lt;プロジェクト名&gt; プロパティ ページ] ダイアログ ボックス - [構成プロパティ] - [マニフェスト ツール]) | Microsoft Docs"
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
  - "VC.Project.VCManifestTool.RegistrarScriptFile"
  - "VC.Project.VCManifestTool.ComponentFileName"
  - "VC.Project.VCManifestTool.TypeLibraryFile"
  - "VC.Project.VCManifestTool.ReplacementsFile"
dev_langs: 
  - "C++"
ms.assetid: 457582b8-cfde-49c0-92e3-3a6b9e8c08eb
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# [分離された COM] ([&lt;プロジェクト名&gt; プロパティ ページ] ダイアログ ボックス - [構成プロパティ] - [マニフェスト ツール])
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このダイアログ ボックスを使用して、[Mt.exe](http://msdn.microsoft.com/library/aa375649) の **\[分離された COM\]** オプションを指定します。  
  
 このプロパティ ページ ダイアログ ボックスを表示するには、プロジェクトまたはプロパティ シートのプロパティ ページを開きます。  **\[共通プロパティ\]** の **\[マニフェスト ツール\]** ノードを展開し、**\[分離された COM\]** をクリックします。  
  
## タスク一覧  
  
-   [方法 : COM コンポーネントを使用する分離アプリケーションをビルドする](../Topic/How%20to:%20Build%20Isolated%20Applications%20to%20Consume%20COM%20Components.md)  
  
## UIElement の一覧  
 **\[タイプ ライブラリ ファイル\]**  
 マニフェスト ファイルを生成するためにマニフェスト ツールが使用するタイプ ライブラリ ファイル \(.tlb ファイル\) の名前を指定するには、\/tlb オプションを使用します。  
  
 **\[レジスタ スクリプト ファイル\]**  
 マニフェスト ファイルを生成するためにマニフェスト ツールが使用するレジストラー スクリプト ファイル \(.rgs ファイル\) の名前を指定するには、\/rgs オプションを使用します。  
  
 **\[コンポーネント ファイル名\]**  
 マニフェスト ツールで生成されるリソースの名前を指定するには、\/dll オプションを使用します。  **\[タイプ ライブラリ ファイル\]** の値または **\[レジスタ スクリプト ファイル\]** の値が指定されている場合は、このプロパティの値を入力する必要があります。  
  
 **\[置換ファイル\]**  
 .rgs ファイル内の置換可能な文字列の値が格納されているファイルへの完全パスを指定するには、\/replacements オプションを使用します。  
  
## 参照  
 [分離アプリケーション](http://msdn.microsoft.com/library/aa375190)   
 [side\-by\-side アセンブリ](_win32_side_by_side_assemblies)   
 [ClickOnce アプリケーション マニフェスト](../Topic/ClickOnce%20Application%20Manifest.md)   
 [マニフェスト ツールのプロパティ ページ](../ide/manifest-tool-property-pages.md)   
 [方法 : プロジェクト プロパティ ページを開く](../misc/how-to-open-project-property-pages.md)   
 [方法 : プロジェクトのプロパティ シートを編集する](../misc/how-to-edit-project-property-sheets.md)