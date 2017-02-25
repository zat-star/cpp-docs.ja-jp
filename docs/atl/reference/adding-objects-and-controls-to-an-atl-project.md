---
title: "ATL プロジェクトへのオブジェクトとコントロールの追加 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.appwiz.ATL.controls"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL コントロール ウィザード"
  - "ATL プロジェクト, 追加 (コントロールを)"
  - "ATL プロジェクト, 追加 (オブジェクトを)"
  - "コントロール [ATL], 追加 (プロジェクトに)"
  - "オブジェクト [C++], 追加 (ALT プロジェクトに)"
  - "ウィザード [C++], ATL プロジェクト"
ms.assetid: c0adcbd0-07fe-4c55-a8fd-8c2c65ecdaad
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# ATL プロジェクトへのオブジェクトとコントロールの追加
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL コード ウィザードを使用して、ATL ベースまたは MFC ベースのプロジェクトにオブジェクトやコントロールを追加できます。  ウィザードは、追加された COM オブジェクトやコントロールに対して、.cpp ファイル、.h ファイル、およびスクリプト ベースのレジストリをサポートする .rgs ファイルを生成します。  Visual Studio で使用できる ATL コード ウィザードは以下のとおりです。  
  
||||  
|-|-|-|  
|[ATL シンプル オブジェクト](../../atl/reference/atl-simple-object-wizard.md)|[ATL ダイアログ](../../atl/reference/atl-dialog-wizard.md)|[ATL コントロール](../../atl/reference/atl-control-wizard.md)|  
|[ATL プロパティ ページ](../../atl/reference/atl-property-page-wizard.md)|[ATL ASP \(Active Server Page\) コンポーネント](../../atl/reference/atl-active-server-page-component-wizard.md)|[ATL OLEDB コンシューマー](../../atl/reference/atl-ole-db-consumer-wizard.md)|  
|[MFC に ATL サポートを追加](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)|[ATL COM\+ 1.0 コンポーネント ウィザード](../../atl/reference/atl-com-plus-1-0-component-wizard.md)|[ATL OLE DB プロバイダー](../../atl/reference/atl-ole-db-provider-wizard.md)|  
  
> [!NOTE]
>  プロジェクトに ATL オブジェクトを追加する前に、関連するヘルプ トピックを参照して、オブジェクトの詳細と必要条件を確認してください。  
  
### ATL コントロール ウィザードを使用してオブジェクトやコントロールを追加するには  
  
1.  ソリューション エクスプローラーでプロジェクト ノードを右クリックし、ショートカット メニューの \[追加\] をクリックします。  \[クラスの追加\] をクリックします。  
  
     [&#91;クラスの追加&#93;](../../ide/add-class-dialog-box.md) ダイアログ ボックスが表示されます。  
  
2.  \[カテゴリ\] ペインの \[ATL\] フォルダーを選択し、フォルダーに追加するオブジェクトを \[テンプレート\] ペインで選択します。  **\[開く\]** をクリックします。  選択したオブジェクトに対応するコード ウィザードが表示されます。  
  
    > [!NOTE]
    >  MFC プロジェクトに ATL オブジェクトを追加する場合は、プロジェクトに ATL サポートを追加する必要があります。  ATL サポートを追加するには、「[MFC プロジェクトへの ATL サポートの追加](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)」の指示に従ってください。  
  
     事前に ATL サポートを追加せずに MFC プロジェクトへの ATL オブジェクトの追加しようとすると、プロジェクトに ATL サポートを追加するかどうかを確認するダイアログ ボックスが表示されます。  **\[はい\]** をクリックしてプロジェクトに ATL サポートを追加し、選択した ATL ウィザードを開きます。  
  
## 参照  
 [ATL プロジェクト ウィザード](../Topic/ATL%20Project%20Wizard.md)   
 [Visual C\+\+ プロジェクトの種類](../../ide/visual-cpp-project-types.md)   
 [アプリケーション ウィザードを使用したデスクトップ プロジェクトの作成](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [ATL COM オブジェクトの基本事項](../../atl/fundamentals-of-atl-com-objects.md)   
 [ATL および C ランタイム コードによるプログラミング](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [ATL プロジェクトの既定の構成](../../atl/reference/default-atl-project-configurations.md)