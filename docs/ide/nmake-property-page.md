---
title: "[Nmake] プロパティ ページ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCNMakeTool.ReBuildCommandLine"
  - "VC.Project.VCNMakeTool.CleanCommandLine"
  - "VC.Project.VCNMakeTool.Output"
  - "VC.Project.VCNMakeTool.BuildCommandLine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NMake プロパティ ページ"
ms.assetid: bd20cb52-9f1d-4240-b4fc-4f43205ac94b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# [Nmake] プロパティ ページ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\[NMake\]** プロパティ ページを使用すると、NMake プロジェクトのビルド設定を指定できます。  
  
 NMake プロジェクトの詳細については、「[メイクファイル プロジェクトの作成](../ide/creating-a-makefile-project.md)」を参照してください。  
  
 **\[NMake\]** プロパティ ページには、以下のプロパティが含まれています。  
  
## UIElement の一覧  
 **\[ビルド コマンド ライン\]**  
 **\[ビルド\]** メニューの **\[ビルド\]** をクリックしたときに実行するコマンドを指定します。  
  
 **\[すべてリビルド コマンド ライン\]**  
 **\[ビルド\]** メニューの **\[すべてリビルド\]** をクリックしたときに実行するコマンドを指定します。  
  
 **\[消去コマンド ライン\]**  
 **\[ビルド\]** メニューの **\[クリーン\]** をクリックしたときに実行するコマンドを指定します。  
  
 **\[出力\]**  
 コマンド ラインの出力を格納するファイルの名前を指定します。  既定では、このファイル名はプロジェクト名に基づいた名前になります。  
  
 **\[プリプロセッサの定義\]**  
 ソース ファイルで使用されるプリプロセッサの定義を指定します。  既定値は、現在のプラットフォームおよび構成によって決まります。  
  
 **\[インクルードの検索パス\]**  
 コンパイラがインクルード ファイルを検索するディレクトリを指定します。  
  
 **\[強制インクルード\]**  
 プロジェクト ファイルに含まれていない場合でも、プリプロセッサで自動的に処理するファイルを指定します。  
  
 **\[アセンブリの検索パス\]**  
 .NET Framework で .NET アセンブリを解決するときに検索するディレクトリを指定します。  
  
 **\[アセンブリの強制使用\]**  
 .NET Framework で自動的に処理するアセンブリを指定します。  
  
 **\[追加のオプション\]**  
 IntelliSense で C\+\+ ファイルを解析するときに使用する追加のコンパイラ スイッチを指定します。  
  
 **\[NMake\]** プロパティ ページにアクセスする方法については、「[方法 : \[プロパティ ページ\] でプロジェクトのプロパティを指定する](../Topic/How%20to:%20Specify%20Project%20Properties%20with%20Property%20Pages.md)」を参照してください。  
  
 プログラムでこのオブジェクトのメンバーにアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCNMakeTool>」を参照してください。  
  
## 参照  
 [プロパティ ページ](../ide/property-pages-visual-cpp.md)   
 [方法 : メイクファイル プロジェクトで IntelliSense を使用可能にする](../ide/how-to-enable-intellisense-for-makefile-projects.md)