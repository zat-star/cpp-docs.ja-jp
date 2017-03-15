---
title: "[入力と出力] ([&lt;プロジェクト名&gt; プロパティ ページ] ダイアログ ボックス - [構成プロパティ] - [マニフェスト ツール]) | Microsoft Docs"
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
  - "VC.Project.VCManifestTool.OutputManifestFile"
  - "VC.Project.VCManifestTool.InputResourceManifests"
  - "VC.Project.VCManifestTool.EmbedManifest"
  - "VC.Project.VCManifestTool.AdditionalManifestFiles"
  - "VC.Project.VCManifestTool.DependencyInformationFile"
  - "VC.Project.VCManifestTool.OutputResourceManifest"
  - "VC.Project.VCManifestTool.GenerateCatalogFiles"
dev_langs: 
  - "C++"
ms.assetid: a8bb20f6-7ace-45ca-bab0-b4f4a5caf170
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# [入力と出力] ([&lt;プロジェクト名&gt; プロパティ ページ] ダイアログ ボックス - [構成プロパティ] - [マニフェスト ツール])
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このダイアログ ボックスを使用して、[Mt.exe](http://msdn.microsoft.com/library/aa375649) の入出力オプションを指定します。  
  
 このプロパティ ページ ダイアログ ボックスを表示するには、プロジェクトまたはプロパティ シートのプロパティ ページを開きます。  **\[構成プロパティ\]** の **\[マニフェスト ツール\]** ノードを展開し、**\[入力と出力\]** をクリックします。  
  
## UIElement の一覧  
 **\[追加のマニフェスト ファイル\]**  
 **\/manifest** オプションを使用して、マニフェスト ツールで処理またはマージされる追加のマニフェスト ファイルの完全パスを指定します。  完全パスは、セミコロンで区切ります。  
  
 **\[入力リソース マニフェスト\]**  
 **\/inputresource** オプションを使用して、マニフェスト ツールに入力される RT\_MANIFEST 型のリソースの完全パスを指定します。  パスの後には、特定のリソース ID を続けることができます。  次に例を示します。  
  
 `dll_with_manifest.dll;#1`  
  
 リソース ID は省略可能であり、既定は winuser.h で CREATEPROCESS\_MANIFEST\_RESOURCE\_ID に設定されています。  
  
 **\[埋め込みマニフェスト\]**  
 **\[はい\]** を指定すると、アプリケーション マニフェスト ファイルがアセンブリに埋め込まれます。  
  
 **\[いいえ\]** を指定すると、アプリケーション マニフェスト ファイルがスタンドアロン ファイルとして作成されます。  
  
 **\[出力マニフェスト ファイル\]**  
 出力マニフェスト ファイルの名前を指定します。  マニフェスト ツールで操作されるマニフェスト ファイルが 1 つだけの場合、このプロパティは省略可能です。  
  
 **\[マニフェスト リソース ファイル\]**  
 プロジェクト出力へのマニフェストの埋め込みに使用される出力リソース ファイルを指定します。  
  
 **\[カタログ ファイルの生成\]**  
 **\/makecdfs** オプションを使用して、カタログを作成するために使用されるカタログ定義ファイル \(.cdf ファイル\) をマニフェスト ツールで生成します。  
  
 **\[マネージ アセンブリからマニフェストを生成\]**  
 マネージ アセンブリからマニフェストを生成します   \(**\-managedassemblyname:***file*\)。  
  
 **\[dependency 要素の抑制\]**  
 **\-managedassembly** オプションと共に使用します。  このタグは、最終的なマニフェストでの dependency 要素の生成を抑制します。  
  
 **\[カテゴリのタグの生成\]**  
 **\-managedassembly** オプションと共に使用します。  このタグにより、カテゴリのタグが生成されます。  
  
 **\[DPI 認識の有効化\]**  
 アプリケーションが DPI 対応かどうかを指定します。  既定では、この設定は MFC プロジェクトの場合は **\[はい\]**、それ以外の場合は **\[いいえ\]** に指定されています。これは、MFC プロジェクトのみが DPI 認識でビルドされるためです。  別の DPI 設定を扱うコードを追加すると、この設定をオーバーライドして **\[はい\]** にすることができます。  DPI 認識ではないのに DPI 認識として設定すると、アプリケーションが不明瞭にまたは小さく見えることがあります。  
  
## 参照  
 [ClickOnce アプリケーション マニフェスト](../Topic/ClickOnce%20Application%20Manifest.md)   
 [マニフェスト ツールのプロパティ ページ](../ide/manifest-tool-property-pages.md)   
 [方法 : プロジェクト プロパティ ページを開く](../misc/how-to-open-project-property-pages.md)   
 [方法 : プロジェクトのプロパティ シートを編集する](../misc/how-to-edit-project-property-sheets.md)