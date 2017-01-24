---
title: "[VC++ ディレクトリ] プロパティ ページ | Microsoft Docs"
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
  - "VC.Project.VCDirectories.IncludePath"
  - "VC.Project.VCDirectories.ReferencePath"
  - "VC.Project.VCDirectories.SourcePath"
  - "VC.Project.VCDirectories.LibraryWPath"
  - "VC.Project.VCDirectories.ExecutablePath"
  - "VC.Project.VCDirectories.LibraryPath"
  - "VS.ToolsOptionsPages.Projects.VCDirectories"
  - "VC.Project.VCDirectories.ExcludePath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "[VC++ ディレクトリ] プロパティ ページ"
ms.assetid: 428eeef6-f127-4271-b3ea-0ae6f2c3d624
caps.latest.revision: 25
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# [VC++ ディレクトリ] プロパティ ページ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プロジェクトをビルドするために Visual Studio によって使用されるディレクトリを指定します。  このプロパティ ページにアクセスするには、**ソリューション エクスプローラー**でプロジェクトのショートカット メニューを開いて **\[プロパティ\]** を選択し、**\[プロパティ ページ\]** ダイアログ ボックスの左ペインで **\[構成プロパティ\]** を展開して **\[VC\+\+ ディレクトリ\]** を選択します。  
  
 Visual Studio を使用してプロジェクトを作成すると、特定のディレクトリが継承されます。  それらの多くは、マクロとして提供されます。  マクロの現在の値を調べるには、**\[VC\+\+ ディレクトリ\]** ページの右ペインで行 \(たとえば **\[インクルード ディレクトリ\]**\) を選択し、右側の下向き矢印ボタンを選択して **\[編集\]** を選択し、表示されたダイアログ ボックスで **\[マクロ\]** ボタンを選択します。  詳細については、ブログの投稿「[VC\+\+ Directories \(VC\+\+ ディレクトリ\)](http://blogs.msdn.com/b/vsproject/archive/2009/07/07/vc-directories.aspx)」、「[Inherited Properties and Property Sheets \(継承されたプロパティとプロパティ シート\)](http://blogs.msdn.com/b/vsproject/archive/2009/06/23/inherited-properties-and-property-sheets.aspx)」、および「[Visual Studio 2010 C\+\+ Project Upgrade Guide \(Visual Studio 2010 C\+\+ プロジェクト アップグレード ガイド\)](http://blogs.msdn.com/b/vcblog/archive/2010/03/02/visual-studio-2010-c-project-upgrade-guide.aspx)」を参照してください。  
  
## ディレクトリの種類  
 また、次のように、その他のディレクトリも指定できます。  
  
 **\[実行ファイル ディレクトリ\]**  
 実行可能ファイルを検索するディレクトリ。  **PATH** 環境変数と対応します。  
  
 **\[インクルード ディレクトリ\]**  
 ソース コードで参照されるインクルード ファイルを検索するディレクトリ。  **INCLUDE** 環境変数と対応します。  
  
 **\[参照ディレクトリ\]**  
 [\#using](../preprocessor/hash-using-directive-cpp.md) ディレクティブによってソース コード内で参照されるアセンブリおよびモジュール \(メタデータ\) ファイルを検索するディレクトリ。  **LIBPATH** 環境変数と対応します。  
  
 **\[ライブラリ ディレクトリ\]**  
 ライブラリ \(.lib\) ファイル \(ランタイム ライブラリを含む\) を検索するディレクトリ。  **LIB** 環境変数と対応します。  この設定は、.obj ファイルには適用されません。.obj ファイルにリンクするには、[リンカー](../ide/linker-property-pages.md)の **\[全般\]** プロパティ ページで **\[Additional Library Dependencies\] \(追加のライブラリ依存関係\)** を選択してファイルの相対パスを指定します。  
  
 **\[ソース ディレクトリ\]**  
 IntelliSense で使用されるソース ファイルを検索するディレクトリ。  
  
 **\[ディレクトリを除外\]**  
 ビルド依存関係をチェックするときに検索しないディレクトリ。  
  
#### ディレクトリ設定を指定または変更するには  
  
1.  **ソリューション エクスプローラー**で、変更するプロジェクトのショートカット メニューを開き、**\[プロパティ\]** をクリックします。  
  
2.  **\[プロパティ ページ\]** ダイアログ ボックスの左ペインで **\[構成プロパティ\]** を展開し、**\[VC\+\+ ディレクトリ\]** を選択します。  
  
3.  ディレクトリの一覧の 1 つを変更するには、それを選択して右側の下向き矢印ボタンを選択し、**\[編集\]** を選択します。  
  
     表示されたダイアログ ボックスのボックスで、値を追加または削除したり、値が表示される順序を変更したりできます。  また、**\[親またはプロジェクトの既定値から継承\]** をオンまたはオフにすることによって、プロジェクトが設定を継承するかどうかを変更することもできます。  
  
## 設定の共有  
 プロジェクトのプロパティを、他のユーザーと共有したり、複数のコンピューター間で共有したりできます。  詳細については、「[プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)」を参照してください。  
  
## 参照  
 [プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)