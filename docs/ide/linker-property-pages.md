---
title: "[リンカー] プロパティ ページ | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.RegisterOutput"
  - "VC.Project.VCLinkerTool.IgnoreImportLibrary"
  - "VC.Project.VCLinkerTool.UseLibraryDependencyInputs"
  - "VC.Project.VCLinkerTool.LinkLibraryDependencies"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ユーザーごとのリダイレクト"
  - "リンカー プロパティ ページ"
ms.assetid: 7e7671e5-a35a-4e67-9bdb-661d75c4d11e
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# [リンカー] プロパティ ページ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、**\[全般\]** \(\[リンカー\] プロパティ ページ\) の以下のプロパティについて説明します。  
  
 **\[インポート ライブラリの無視\]**  
 このビルドから生成された .lib 出力を依存プロジェクトにリンクしないように、リンカーに通知します。  このため、プロジェクト システムは、ビルド時に .lib ファイルを生成しない .dll ファイルを処理できます。  あるプロジェクトが DLL を生成する他のプロジェクトに依存している場合、プロジェクト システムでは子プロジェクトによって生成される .lib ファイルを自動的にリンクします。  この動作は COM DLL やリソースだけの DLL を生成するプロジェクトには不要な場合があります。これらの DLL には意味のあるエクスポート内容が含まれません。  DLL にエクスポート内容が含まれない場合は、リンカーで .lib ファイルが生成されません。  ディスクにエクスポート .lib ファイルがなく、この DLL とリンクするようにプロジェクト システムからリンカーに指示が出された場合は、リンクに失敗します。  
  
 この問題を解決するには、\[インポート ライブラリの無視\] を使用します。  このプロパティを `Yes` に設定すると、プロジェクト システムは .lib ファイルの有無を無視し、このプロジェクトに依存する他のプロジェクトが、存在しない .lib ファイルとリンクされないようにします。  
  
 プログラムを使用してこのプロパティにアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreImportLibrary%2A>」を参照してください。  
  
 **\[出力の登録\]**  
 .dll プロジェクトだけに有効な regsvr32.exe \/s $\(TargetPath\) を実行します。  .exe プロジェクトでは、このプロパティは無視されます。  .exe 出力を登録する場合は、構成にビルド後のイベントを設定し、登録済みの .exe ファイルに必要なカスタム登録を行います。  
  
 プログラムを使用してこのプロパティにアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RegisterOutput%2A>」を参照してください。  
  
 **\[ユーザーごとのリダイレクト\]**  
 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] の登録はこれまで、HKEY\_CLASSES\_ROOT \(HKCR\) で行われてきました。  [!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)] を使用して HKCR にアクセスするには、システム特権のあるモードで [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] を実行する必要があります。  開発者は常にシステム特権のあるモードで実行するわけではありませんが、登録を処理する必要があります。  ユーザーごとのリダイレクトにより、このモードで実行せずに登録を行うことができるようになります。  
  
 ユーザーごとのリダイレクトは、HKCR への書き込みが HKEY\_CURRENT\_USER \(HKCU\) にリダイレクトされるように強制します。  ユーザーごとのリダイレクトをオフにすると、プログラムが HKCR への書き込みを試行するときに[プロジェクト ビルド エラー PRJ0050](../error-messages/tool-errors/project-build-error-prj0050.md) が発生する場合があります。  
  
 **\[リンク ライブラリの依存関係\]**  
 依存プロジェクトによって生成された .lib ファイルをリンクするかどうかを選択できます。  通常は、.lib ファイルをリンクするように指定します。  
  
 また、ファイル名と相対パス \(たとえば **..\\..\\MyLibProject\\MyObjFile.obj**\) によって .obj ファイルを指定できます。  .obj ファイルのソース コードにプリコンパイル済みヘッダー \(たとえば pch.h\) が含まれている場合、pch.obj ファイルは **MyObjFile.obj** と同じフォルダーに置かれ、依存関係として **pch.obj** を追加する必要があります。  
  
 **\[ライブラリ依存関係の入力の使用\]**  
 大規模なプロジェクトでは、依存プロジェクトによって .lib ファイルが生成される場合、インクリメンタル リンクは無効にされています。  .lib ファイルを生成する依存プロジェクトが多数存在する場合、アプリケーションのビルドに長時間を要する場合があります。  このプロパティを `Yes` に設定すると、プロジェクト システムによってインクリメンタル リンクが有効にされ、依存プロジェクトが生成する .lib ファイルに対して .obj ファイルがリンクされます。  
  
 **\[全般\]** \(\[リンカー\] プロパティ ページ\) を表示する方法については、「[方法 : &#91;プロパティ ページ&#93; でプロジェクトのプロパティを指定する](../Topic/How%20to:%20Specify%20Project%20Properties%20with%20Property%20Pages.md)」を参照してください。  
  
## 参照  
 [VC\+\+ Directories, Projects and Solutions, Options Dialog Box](http://msdn.microsoft.com/ja-jp/e027448b-c811-4c3d-8531-4325ad3f6e02)   
 [プロパティ ページ](../ide/property-pages-visual-cpp.md)