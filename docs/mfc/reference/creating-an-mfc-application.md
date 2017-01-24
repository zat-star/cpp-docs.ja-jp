---
title: "MFC アプリケーションの作成 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アプリケーション [MFC]"
  - "MFC [C++]、作成 (アプリケーションを)"
  - "MFC アプリケーション"
ms.assetid: b8b8aa08-9c49-404c-8078-b42079ac18f0
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC アプリケーションの作成
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC アプリケーションは、MFC \(Microsoft Foundation Class\) ライブラリに基づく Windows 対応の実行可能なアプリケーションです。  MFC アプリケーションを作成する最も簡単な方法は、MFC アプリケーション ウィザードを使用する方法です。  
  
> [!IMPORTANT]
>  MFC プロジェクトは、Visual Studio Express エディションではサポートされていません。  
  
 通常、MFC アプリケーションは、標準の Windows アプリケーション、ダイアログ ボックス、フォーム ベースのアプリケーション、エクスプローラー形式のアプリケーション、Web ブラウザー形式のアプリケーションの 5 つのタイプに分かれます。  詳細については、次のトピックを参照してください。  
  
-   [クラスを使用した Windows アプリケーションの作成](../Topic/Using%20the%20Classes%20to%20Write%20Applications%20for%20Windows.md)  
  
-   [ダイアログ ボックスの作成と表示](../../mfc/creating-and-displaying-dialog-boxes.md)  
  
-   [フォーム ベースの MFC アプリケーションの作成](../Topic/Creating%20a%20Forms-Based%20MFC%20Application.md)  
  
-   [エクスプローラー形式の MFC アプリケーションの作成](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)  
  
-   [Web ブラウザー形式の MFC アプリケーションの作成](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)  
  
 MFC アプリケーション ウィザードでは、これらのアプリケーションのすべてに適したクラスやファイルが生成されます。作成されるクラスやファイルは、ウィザードで選択したオプションによって異なります。  
  
### MFC アプリケーション ウィザードを使用して MFC アプリケーションを作成するには  
  
1.  「[Visual C\+\+ のアプリケーション ウィザードを使用したプロジェクトの作成](../../ide/creating-desktop-projects-by-using-application-wizards.md)」の手順に従います。  
  
2.  **\[新しいプロジェクト\]** ダイアログ ボックスのテンプレート ペインの **\[MFC アプリケーション\]** を選択してウィザードを開きます。  
  
3.  [MFC アプリケーション ウィザード](../Topic/MFC%20Application%20Wizard.md)を使用してアプリケーションの設定を定義します。  
  
    > [!NOTE]
    >  ウィザードの既定の設定を使用する場合は、この手順を省略します。  
  
4.  **\[完了\]** をクリックしてウィザードを閉じ、新しいプロジェクトを開発環境で開きます。  
  
 作成したプロジェクトは**ソリューション エクスプローラー**で確認できます。  ウィザードでプロジェクト用に作成されるファイルの詳細については、プロジェクトが生成する ReadMe.txt ファイルを参照してください。  ファイルの種類の詳細については、「[Visual C\+\+ プロジェクトに対して作成されるファイルの種類](../../ide/file-types-created-for-visual-cpp-projects.md)」を参照してください。  
  
## 参照  
 [Debugging Preparation: Visual C\+\+ Windows Applications](http://msdn.microsoft.com/ja-jp/a8bc54de-41a3-464d-9a12-db9bdcbc1ad5)   
 [コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [プロパティ ページ](../../ide/property-pages-visual-cpp.md)   
 [Deploying Applications](http://msdn.microsoft.com/ja-jp/4ff8881d-0daf-47e7-bfe7-774c625031b4)