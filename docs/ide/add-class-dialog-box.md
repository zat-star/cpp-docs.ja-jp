---
title: "[クラスの追加] ダイアログ ボックス | Microsoft Docs"
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
  - "vc.addclass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "[クラスの追加] ダイアログ ボックス"
ms.assetid: 916259b8-8e5f-4267-bd10-313483beba67
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# [クラスの追加] ダイアログ ボックス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\[クラスの追加\]** ダイアログ ボックスのテンプレートを使用すると、次の操作を実行できます。  
  
-   対応するコード ウィザードを開始する \(使用できる場合\)。 詳細については、「[コード ウィザードを使用した機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)」を参照してください。  
  
 または  
  
-   適したファイルおよびソース コードをプロジェクトに追加して、新しいクラスを自動作成する。  
  
 **\[クラスの追加\]** ダイアログ ボックスには、**\[プロジェクト\]** メニュー、**ソリューション エクスプローラー**、[クラス ビュー](http://msdn.microsoft.com/ja-jp/8d7430a9-3e33-454c-a9e1-a85e3d2db925)からアクセスできます。  
  
> [!NOTE]
>  現在のプロジェクトに対応しないクラスを追加しようとすると、エラー メッセージが表示されます。**\[OK\]** をクリックすると、**\[クラスの追加\]** ダイアログ ボックスに戻ります。  
  
## クラスの追加テンプレート  
 **クラスの追加**テンプレートには、4 つのカテゴリ \(.NET、ATL、MFC、汎用\) があります。**\[テンプレート\]** ウィンドウでテンプレートを選択すると、選択したテンプレートの説明が **\[カテゴリ\]** ウィンドウと **\[テンプレート\]** ウィンドウに表示されます。  
  
### .NET  
  
|テンプレート|ウィザード|  
|------------|-----------|  
|ASP.NET Web サービス|使用できません|  
|コンポーネント クラス \(.NET\)|使用できません|  
|インストーラー クラス \(.NET\)|使用できません|  
|ユーザー コントロール \(.NET\)|使用できません|  
|Windows フォーム \(.NET\)|使用できません|  
  
### ATL  
  
|テンプレート|ウィザード|  
|------------|-----------|  
|MFC に ATL サポートを追加|使用できません|  
|ATL Active Server Page コンポーネント|[ATL Active Server Page コンポーネント ウィザード](../atl/reference/atl-active-server-page-component-wizard.md)|  
|ATL コントロール|[ATL コントロール ウィザード](../atl/reference/atl-control-wizard.md)|  
|ATL ダイアログ|[ATL ダイアログ ウィザード](../atl/reference/atl-dialog-wizard.md)|  
|ATL COM\+ 1.0 コンポーネント|[ATL COM\+ 1.0 コンポーネント ウィザード](../atl/reference/atl-com-plus-1-0-component-wizard.md)|  
|ATL OLEDB コンシューマー|[ATL OLE DB コンシューマー ウィザード](../atl/reference/atl-ole-db-consumer-wizard.md)|  
|ATL OLEDB プロバイダー|[ATL OLE DB プロバイダー ウィザード](../atl/reference/atl-ole-db-provider-wizard.md)|  
|ATL プロパティ ページ|[ATL プロパティ ページ ウィザード](../atl/reference/atl-property-page-wizard.md)|  
|ATL シンプル オブジェクト|[ATL シンプル オブジェクト ウィザード](../atl/reference/atl-simple-object-wizard.md)|  
|WMI イベント プロバイダー|WMI イベント プロバイダー ウィザード|  
|WMI インスタンス プロバイダー|WMI インスタンス プロバイダー ウィザード|  
  
### MFC  
  
|テンプレート|ウィザード|  
|------------|-----------|  
|MFC クラス|[MFC クラス追加ウィザード](../mfc/reference/mfc-add-class-wizard.md)|  
|ActiveX コントロールの MFC クラス|[ActiveX コントロール クラス追加ウィザード](../ide/add-class-from-activex-control-wizard.md)|  
|TypeLib からの MFC クラス|[Typelib クラス追加ウィザード](../mfc/reference/add-class-from-typelib-wizard.md)|  
|MFC ODBC コンシューマー|[MFC ODBC コンシューマー ウィザード](../mfc/reference/mfc-odbc-consumer-wizard.md)|  
  
### 汎用クラス  
  
|テンプレート|ウィザード|  
|------------|-----------|  
|汎用 C\+\+ クラス|[汎用 C\+\+ クラス ウィザード](../ide/generic-cpp-class-wizard.md)|  
  
## 参照  
 [メンバー関数の追加](../ide/adding-a-member-function-visual-cpp.md)   
 [メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md)   
 [仮想関数のオーバーライド](../Topic/Overriding%20a%20Virtual%20Function%20\(Visual%20C++\).md)   
 [MFC メッセージ ハンドラー](../mfc/reference/adding-an-mfc-message-handler.md)   
 [クラス各部へのジャンプ](../ide/navigating-the-class-structure-visual-cpp.md)