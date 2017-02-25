---
title: "メイクファイル プロジェクトの作成 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.makefile.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "メイクファイル プロジェクト, 作成"
  - "プロジェクト ファイル [C++], メイクファイル プロジェクト"
ms.assetid: dd077af3-97a8-48fb-baaa-cf7e07ddef61
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# メイクファイル プロジェクトの作成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

メイクファイルを使用してコマンド ラインからビルドしたプロジェクトは、Visual Studio 開発環境では認識されません。  [!INCLUDE[vsUltShort](../ide/includes/vsultshort_md.md)]、[!INCLUDE[vsPro](../ide/includes/vspro_md.md)]、または Visual Studio Express for Windows Desktop を使用してプロジェクトを開き、ビルドするには、メイクファイル プロジェクトのテンプレートを選択して、最初に空のプロジェクトを作成します。  作成した空のプロジェクトを使用して、目的のプロジェクトを Visual Studio 開発環境でビルドします。  
  
 ソリューション エクスプローラーでは、プロジェクトのファイルは表示されません。  プロジェクトで指定したビルド構成は、プロジェクトのプロパティ ページに反映されます。  
  
 プロジェクトで指定した出力ファイルは、ビルド スクリプトの生成するファイルの名前には直接は影響しません。  
  
### メイクファイル プロジェクトを作成するには  
  
1.  「[Visual C\+\+ のアプリケーション ウィザードを使用したプロジェクトの作成](../ide/creating-desktop-projects-by-using-application-wizards.md)」の手順に従います。  
  
2.  **\[新しいプロジェクト\]** ダイアログ ボックスの \[テンプレート\] ペインの **\[メイクファイル プロジェクト\]** をクリックしてウィザードを開きます。  
  
3.  [&#91;アプリケーションの設定&#93;](../ide/application-settings-makefile-project-wizard.md) ページで、コマンド、出力、クリーンアップ、およびリビルドに関する情報を指定します。  
  
4.  **\[完了\]** をクリックしてウィザードを閉じ、新しく作成したプロジェクトを**ソリューション エクスプローラー**で開きます。  
  
 プロジェクトのプロパティは、プロパティ ページで表示および編集できます。  プロパティ ページの表示方法については、「[Visual C\+\+ プロジェクトのプロパティの設定](../ide/working-with-project-properties.md)」を参照してください。  
  
## 参照  
 [メイクファイル アプリケーション ウィザード](../ide/makefile-project-wizard.md)   
 [メイクファイルの特殊文字](../build/special-characters-in-a-makefile.md)   
 [メイクファイルの内容](../build/contents-of-a-makefile.md)