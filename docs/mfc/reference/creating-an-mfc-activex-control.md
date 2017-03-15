---
title: "MFC ActiveX コントロールの作成 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.activex.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX コントロール [C++], 作成"
  - "MFC ActiveX コントロール [C++], 作成"
ms.assetid: 8bd5a93c-d04d-414e-bb28-163fdc1c0dd5
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# MFC ActiveX コントロールの作成
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ActiveX コントロール プログラムは、親アプリケーションに特定の機能を提供するモジュール プログラムです。  たとえば、ダイアログ ボックスのボタンや Web ページのツール バーなどのコントロールを作成できます。  
  
 MFC ActiveX コントロールを作成する最も簡単な方法は、[MFC ActiveX コントロール ウィザード](../../mfc/reference/mfc-activex-control-wizard.md)を使用する方法です。  
  
### MFC ActiveX コントロール ウィザードを使用して MFC ActiveX コントロールを作成するには  
  
1.  「[Visual C\+\+ のアプリケーション ウィザードを使用したプロジェクトの作成](../../ide/creating-desktop-projects-by-using-application-wizards.md)」の手順に従います。  
  
2.  **\[新しいプロジェクト\]** ダイアログ ボックスのテンプレート ペインの \[MFC ActiveX コントロール\] アイコンをクリックし、MFC ActiveX コントロール ウィザードを開きます。  
  
3.  MFC ActiveX コントロール ウィザードを使用して、[アプリケーションの設定](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)、[コントロール名](../../mfc/reference/control-names-mfc-activex-control-wizard.md)、および[コントロールの設定](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)を定義します。  
  
    > [!NOTE]
    >  ウィザードの既定の設定を使用する場合は、この手順を省略します。  
  
4.  **\[完了\]** をクリックしてウィザードを閉じ、新しいプロジェクトを開発環境で開きます。  
  
 作成したプロジェクトは**ソリューション エクスプローラー**で確認できます。  ウィザードでプロジェクト用に作成されるファイルの詳細については、プロジェクトが生成する ReadMe.txt ファイルを参照してください。  ファイルの種類の詳細については、「[Visual C\+\+ プロジェクトに対して作成されるファイルの種類](../../ide/file-types-created-for-visual-cpp-projects.md)」を参照してください。  
  
 プロジェクトを作成したら、コード ウィザードを使用して[関数](../../ide/add-member-function-wizard.md)、[変数](../../ide/add-member-variable-wizard.md)、[イベント](../../ide/add-event-wizard.md)、[プロパティ](../../ide/names-add-property-wizard.md)、および[メソッド](../../ide/add-method-wizard.md)を追加します。  ActiveX コントロールのカスタマイズの詳細については、「[MFC ActiveX コントロール](../../mfc/mfc-activex-controls.md)」を参照してください。  
  
## 参照  
 [コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [プロパティ ページ](../../ide/property-pages-visual-cpp.md)   
 [Deploying Applications](http://msdn.microsoft.com/ja-jp/4ff8881d-0daf-47e7-bfe7-774c625031b4)