---
title: "方法: カスタム ツールをプロジェクト プロパティに統合する | Microsoft Docs"
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
  - "msbuild.cpp.howto.integratecustomtools"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "msbuild (c++), 方法: カスタム ビルド ツールを統合する"
ms.assetid: f32d91a4-44e9-4de3-aa9a-1c7f709ad2ee
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 方法: カスタム ツールをプロジェクト プロパティに統合する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

基になる XML スキーマ ファイルを作成すると、Visual Studio の **\[プロパティ ページ\]** ウィンドウにカスタム ツール オプションを追加できます。  
  
 **\[プロパティ ページ\]** ウィンドウの **\[構成プロパティ\]** セクションに、*規則*という設定グループが表示されます。  すべての規則には、ツールまたは機能のグループの設定が含まれます。  たとえば、**リンカー**規則には、リンカー ツールの設定が含まれます。  規則の設定は、*カテゴリ*に細分化できます。  
  
 このドキュメントでは、カスタム ツールのプロパティを含む設定ディレクトリにファイルを作成して、Visual Studio が起動するときにそのプロパティが読み込まれるようにする方法を説明します。  ファイルを変更する方法の詳細については、Visual Studio の [プラットフォームの Extensibilty のパート２](http://go.microsoft.com/fwlink/?LinkID=191489) プロジェクト チーム ブログの投稿"を参照してください。  
  
### プロジェクト プロパティを追加または変更するには  
  
1.  XML エディターで XML ファイルを作成します。  
  
2.  そのファイルを %ProgramFiles%\\MSBuild\\Microsoft.Cpp\\v4.0\\ フォルダーに保存します。  **\[プロパティ ページ\]** ウィンドウのすべての規則は、このフォルダーの XML ファイルによって表現されます。  ファイルの名前がフォルダー内で一意であることを確認します。  
  
3.  %ProgramFiles%\\MSBuild\\Microsoft.Cpp\\v4.0\\cl.xml の内容をコピーし、変更を保存しないでファイルを閉じ、その内容を新しい XML ファイルに貼り付けます。  任意のXML スキーマ ファイルを使用できます。これは、テンプレートから起動するために使用できる方法の 1 つの例に過ぎません。  
  
4.  新しい XML ファイルで、必要に応じて内容を変更します。  ファイルの上部で **Rule Name** および **Rule.DisplayName** を変更します。  
  
5.  変更を保存してファイルを閉じます。  
  
6.  Visual Studio が開始するとき、%ProgramFiles%\\MSBuild\\Microsoft.Cpp\\v4.0\\ の XML ファイルが読み込まれます。  したがって、新しいファイルをテストするには、Visual Studio を再起動します。  
  
7.  **ソリューション エクスプローラー**で、プロジェクトを右クリックし、**\[プロパティ\]** をクリックします。  **\[プロパティ ページ\]** ウィンドウの左ペインで、新しいコードと自分の規則の名前があることを確認します。  
  
## 参照  
 [MSBuild \(Visual C\+\+\)](../Topic/MSBuild%20\(Visual%20C++\).md)