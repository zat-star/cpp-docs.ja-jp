---
title: "マニフェスト ツール分離 COM プロパティ (Visual C) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCManifestTool.RegistrarScriptFile
- VC.Project.VCManifestTool.ComponentFileName
- VC.Project.VCManifestTool.TypeLibraryFile
- VC.Project.VCManifestTool.ReplacementsFile
dev_langs:
- C++
ms.assetid: 457582b8-cfde-49c0-92e3-3a6b9e8c08eb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fe2098c4caead6ebc9ad4747354ae96f093f2c91
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="isolated-com-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>COM、マニフェスト ツールは、[構成プロパティを分離&lt;Projectname&gt;プロパティ ページ] ダイアログ ボックス
このダイアログ ボックスを使用して、**分離された COM**オプション[Mt.exe](http://msdn.microsoft.com/library/aa375649)です。  
  
 このプロパティ ページ ダイアログ ボックスにアクセスするには、プロジェクトまたはプロパティ シートのプロパティ ページを開きます。 展開して、**マニフェスト ツール**ノードの下**共通プロパティ**、し、**分離された COM**です。  
  
## <a name="task-list"></a>タスク一覧  
  
-   [方法 : COM コンポーネントを使用する分離アプリケーションをビルドする](../build/how-to-build-isolated-applications-to-consume-com-components.md)  
  
## <a name="uielement-list"></a>UIElement の一覧  
 **タイプ ライブラリ ファイル**  
 /Tlb オプションを使用すると、マニフェストのツールを使用して、マニフェスト ファイルを生成するタイプ ライブラリ ファイル (.tlb ファイル) の名前を指定します。  
  
 **レジストラー スクリプト ファイル**  
 /Rgs オプションを使用すると、マニフェスト ファイルを生成するのにマニフェスト ツールを使用するレジスタ スクリプト ファイル (.rgs ファイル) の名前を指定します。  
  
 **コンポーネントのファイル名**  
 /Dll オプションを使用すると、マニフェスト ツールにより生成されるリソースの名前を指定します。 このプロパティの値を入力する必要があるときにいずれかの値**タイプ ライブラリ ファイル**または**レジスタ スクリプト ファイル**が指定されています。  
  
 **置換ファイル**  
 /Replacements オプションを使用すると、.rgs ファイルで置換できる文字列の値を含むファイルへの完全パスを指定します。  
  
## <a name="see-also"></a>参照  
 [分離アプリケーション](http://msdn.microsoft.com/library/aa375190)   
 [ClickOnce アプリケーション マニフェスト](/visualstudio/deployment/clickonce-application-manifest)   
 [マニフェスト ツールのプロパティ ページ](../ide/manifest-tool-property-pages.md)   
 [プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)   