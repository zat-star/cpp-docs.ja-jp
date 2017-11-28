---
title: "[リンカー] プロパティ ページ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.RegisterOutput
- VC.Project.VCLinkerTool.OVERWRITEImportLibrary
- VC.Project.VCLinkerTool.UseLibraryDependencyInputs
- VC.Project.VCLinkerTool.LinkLibraryDependencies
dev_langs: C++
helpviewer_keywords:
- per-user redirection
- Linker property pages
ms.assetid: 7e7671e5-a35a-4e67-9bdb-661d75c4d11e
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c958b0bce27effc5362d107a3b6abe9fcc761d39
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="linker-property-pages"></a>リンカー プロパティ ページ
このトピックでは、次のプロパティをでに関する、**全般**リンカー プロパティ ページ。  
  
 **インポート ライブラリを無視します。**  
 このビルドから生成された .lib 出力を依存プロジェクトにリンクしないように、リンカーに通知します。 このため、プロジェクト システムは、ビルド時に .lib ファイルを生成しない .dll ファイルを処理できます。 あるプロジェクトが DLL を生成する他のプロジェクトに依存している場合、プロジェクト システムでは子プロジェクトによって生成される .lib ファイルを自動的にリンクします。 この動作は COM DLL やリソースだけの DLL を生成するプロジェクトには不要な場合があります。これらの DLL には意味のあるエクスポート内容が含まれません。 DLL にエクスポート内容が含まれない場合は、リンカーで .lib ファイルが生成されません。 ディスクにエクスポート .lib ファイルがなく、この DLL とリンクするようにプロジェクト システムからリンカーに指示が出された場合は、リンクに失敗します。  
  
 使用して**インポート ライブラリの無視**この問題を解決します。 このプロパティを `Yes` に設定すると、プロジェクト システムは .lib ファイルの有無を無視し、このプロジェクトに依存する他のプロジェクトが、存在しない .lib ファイルとリンクされないようにします。  
  
 プログラムを使用してこのプロパティにアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreImportLibrary%2A>」を参照してください。  
  
 **出力の登録**  
 .dll プロジェクトだけに有効な regsvr32.exe /s $(TargetPath) を実行します。 .exe プロジェクトでは、このプロパティは無視されます。 .exe 出力を登録する場合は、構成にビルド後のイベントを設定し、登録済みの .exe ファイルに必要なカスタム登録を行います。  
  
 プログラムを使用してこのプロパティにアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RegisterOutput%2A>」を参照してください。  
  
 **Per-user Redirection**  
 Visual Studio での登録には、HKEY_CLASSES_ROOT (HKCR) で処理が行っていました。 [!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)]、Visual Studio を管理者特権モードで実行する必要があります HKCR にアクセスします。 開発者は常にシステム特権のあるモードで実行するわけではありませんが、登録を処理する必要があります。 ユーザーごとのリダイレクトにより、このモードで実行せずに登録を行うことができるようになります。  
  
 ユーザーごとのリダイレクトは、HKCR への書き込みが HKEY_CURRENT_USER (HKCU) にリダイレクトされるように強制します。 ユーザーごとのリダイレクトを無効にすると、発生する可能性が[プロジェクト ビルド エラー PRJ0050](../error-messages/tool-errors/project-build-error-prj0050.md) HKCR への書き込みが開始するとき、プログラムです。  
  
 **ライブラリ依存関係のリンク**  
 依存プロジェクトによって生成された .lib ファイルをリンクするかどうかを選択できます。 通常は、.lib ファイルをリンクするように指定します。  
  
 たとえば、ファイル名と相対パスを提供することによって、.obj ファイルを指定することも**.\\..\MyLibProject\MyObjFile.obj**です。場合は、.obj ファイルのソース コードに # pch.obj ファイルと同じフォルダーにありますし、たとえば pch.h、プリコンパイル済みヘッダーを includes **MyObjFile.obj**も追加する必要がありますと**pch.obj**として追加依存関係です。  
  
 **ライブラリ依存関係の入力の使用**  
 大規模なプロジェクトでは、依存プロジェクトによって .lib ファイルが生成される場合、インクリメンタル リンクは無効にされています。 .lib ファイルを生成する依存プロジェクトが多数存在する場合、アプリケーションのビルドに長時間を要する場合があります。 このプロパティを `Yes` に設定すると、プロジェクト システムによってインクリメンタル リンクが有効にされ、依存プロジェクトが生成する .lib ファイルに対して .obj ファイルがリンクされます。  
  
 アクセスする方法については、**全般**リンカー プロパティ ページを参照してください[のプロジェクト プロパティの操作](../ide/working-with-project-properties.md)です。  
  
## <a name="see-also"></a>関連項目  
 [Vc++ ディレクトリ プロジェクトおよびソリューション、[オプション] ダイアログ ボックス](http://msdn.microsoft.com/en-us/e027448b-c811-4c3d-8531-4325ad3f6e02)   
 [プロパティ ページ](../ide/property-pages-visual-cpp.md)