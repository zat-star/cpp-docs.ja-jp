---
title: "CMFCToolBarsCustomizeDialog クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCToolBarsCustomizeDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarsCustomizeDialog クラス"
ms.assetid: 78e2cddd-4f13-4097-afc3-1ad646a113f1
caps.latest.revision: 28
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarsCustomizeDialog クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

モードレス タブ ダイアログ ボックス \([CPropertySheet クラス](../../mfc/reference/cpropertysheet-class.md)\) を使用して、アプリケーションのツール バー、メニュー、キーボード ショートカット、ユーザー定義のツール、および表示スタイルをカスタマイズできます。  通常、このダイアログ ボックスを表示するには、**\[ツール\]** メニューの **\[ユーザー設定\]** をクリックします。  
  
 **\[ユーザー設定\]** ダイアログ ボックスには、**\[コマンド\]**、**\[ツール バー\]**、**\[ツール\]**、**\[キーボード\]**、**\[メニュー\]**、および **\[オプション\]** の 6 個のタブがあります。  
  
## 構文  
  
```  
class CMFCToolBarsCustomizeDialog : public CPropertySheet  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog](../Topic/CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog.md)|`CMFCToolBarsCustomizeDialog` オブジェクトを構築します。|  
|`CMFCToolBarsCustomizeDialog::~CMFCToolBarsCustomizeDialog`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddButton](../Topic/CMFCToolBarsCustomizeDialog::AddButton.md)|**\[コマンド\]** ページのコマンドの一覧にツール バー ボタンを挿入します。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddMenu](../Topic/CMFCToolBarsCustomizeDialog::AddMenu.md)|メニューをリソースから読み込み、[CMFCToolBarsCustomizeDialog::AddMenuCommands](../Topic/CMFCToolBarsCustomizeDialog::AddMenuCommands.md) を呼び出して **\[Commands\]** ページのコマンドの一覧にそのメニューを追加します。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddMenuCommands](../Topic/CMFCToolBarsCustomizeDialog::AddMenuCommands.md)|メニューをリソースから読み込み、[CMFCToolBarsCustomizeDialog::AddMenuCommands](../Topic/CMFCToolBarsCustomizeDialog::AddMenuCommands.md) を呼び出して **\[Commands\]** ページのコマンドの一覧にそのメニューを追加します。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddToolBar](../Topic/CMFCToolBarsCustomizeDialog::AddToolBar.md)|リソースからツール バーを読み込みます。  その後、メニュー内の各コマンドについて、[CMFCToolBarsCustomizeDialog::AddButton](../Topic/CMFCToolBarsCustomizeDialog::AddButton.md) メソッドを呼び出して、指定したカテゴリの下の **\[コマンド\]** ページのコマンドの一覧にボタンを挿入します。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::Create](../Topic/CMFCToolBarsCustomizeDialog::Create.md)|**\[Customization\]** ダイアログ ボックスを表示します。|  
|`CMFCToolBarsCustomizeDialog::EnableTools`|将来利用するために予約されています。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars](../Topic/CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars.md)|**\[Customize\]** ダイアログ ボックスを使用した新しいツール バーの作成を有効または無効にします。|  
|[CMFCToolBarsCustomizeDialog::FillAllCommandsList](../Topic/CMFCToolBarsCustomizeDialog::FillAllCommandsList.md)|指定された `CListBox` オブジェクトを、**\[すべてのコマンド\]** カテゴリのコマンドで追加します。|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](../Topic/CMFCToolBarsCustomizeDialog::FillCategoriesComboBox.md)|指定された `CComboBox` オブジェクトを、**\[ユーザー設定\]** ダイアログ ボックスの各コマンド カテゴリの名前で追加します。|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesListBox](../Topic/CMFCToolBarsCustomizeDialog::FillCategoriesListBox.md)|指定された `CListBox` オブジェクトを、**\[ユーザー設定\]** ダイアログ ボックスの各コマンド カテゴリの名前で追加します。|  
|[CMFCToolBarsCustomizeDialog::GetCommandName](../Topic/CMFCToolBarsCustomizeDialog::GetCommandName.md)|指定されたコマンド ID に関連付けられた名前を取得します。|  
|[CMFCToolBarsCustomizeDialog::GetCountInCategory](../Topic/CMFCToolBarsCustomizeDialog::GetCountInCategory.md)|指定されたテキスト ラベルを持つ、指定されたリストの項目数を取得します。|  
|[CMFCToolBarsCustomizeDialog::GetFlags](../Topic/CMFCToolBarsCustomizeDialog::GetFlags.md)|ダイアログ ボックスの動作に影響を与える一連のフラグを取得します。|  
|`CMFCToolBarsCustomizeDialog::GetThisClass`|このクラス型に関連付けられた [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage](../Topic/CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage.md)|ユーザーがツール バー ボタンまたはメニュー項目アイコンをカスタマイズできるように、イメージ エディターを起動します。|  
|[CMFCToolBarsCustomizeDialog::OnInitDialog](../Topic/CMFCToolBarsCustomizeDialog::OnInitDialog.md)|プロパティ シートの初期化処理を拡張するためにオーバーライドします。  \([CPropertySheet::OnInitDialog](../Topic/CPropertySheet::OnInitDialog.md) をオーバーライドします\)。|  
|[CMFCToolBarsCustomizeDialog::PostNcDestroy](../Topic/CMFCToolBarsCustomizeDialog::PostNcDestroy.md)|ウィンドウが破棄された後に、フレームワークによって呼び出されます。  \(`CPropertySheet::PostNcDestroy` をオーバーライドします\)。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::RemoveButton](../Topic/CMFCToolBarsCustomizeDialog::RemoveButton.md)|指定したコマンド ID を持つボタンを、指定したカテゴリまたはすべてのカテゴリから削除します。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::RenameCategory](../Topic/CMFCToolBarsCustomizeDialog::RenameCategory.md)|**\[コマンド\]** タブのカテゴリのリスト ボックスで、カテゴリの名前を変更します。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::ReplaceButton](../Topic/CMFCToolBarsCustomizeDialog::ReplaceButton.md)|**\[コマンド\]** タブのコマンドのリスト内のボタンを、新しいツール バー ボタン オブジェクトに置き換えます。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::SetUserCategory](../Topic/CMFCToolBarsCustomizeDialog::SetUserCategory.md)|**\[コマンド\]** タブに表示されるカテゴリのリストにカテゴリを追加します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::CheckToolsValidity](../Topic/CMFCToolBarsCustomizeDialog::CheckToolsValidity.md)|ユーザー定義のツールの一覧が有効かどうかを判断するために、フレームワークによって呼び出されます。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnAfterChangeTool](../Topic/CMFCToolBarsCustomizeDialog::OnAfterChangeTool.md)|ユーザー定義のツールのプロパティが変更されるとフレームワークによって呼び出されます。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnAssignKey](../Topic/CMFCToolBarsCustomizeDialog::OnAssignKey.md)|指定したキーボード ショートカットをアクションに割り当てることができるかどうかを判断します。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnBeforeChangeTool](../Topic/CMFCToolBarsCustomizeDialog::OnBeforeChangeTool.md)|ユーザー定義のツールを変更できるかどうかを判断します。|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnInitToolsPage](../Topic/CMFCToolBarsCustomizeDialog::OnInitToolsPage.md)|ユーザーが **\[ツール\]** タブをクリックすると、フレームワークによって呼び出されます。|  
  
## 解説  
 **\[ユーザー設定\]** ダイアログ ボックスを表示するには、`CMFCToolBarsCustomizeDialog` オブジェクトを作成し、[CMFCToolBarsCustomizeDialog::Create](../Topic/CMFCToolBarsCustomizeDialog::Create.md) メソッドを呼び出します。  
  
 **\[ユーザー設定\]** ダイアログ ボックスがアクティブな間、アプリケーションはユーザーによるタスクのカスタマイズを制限する特殊モードで動作します。  
  
## 使用例  
 `CMFCToolBarsCustomizeDialog` クラスのさまざまなメソッドの使用方法を示す例を次に示します。  例では、**\[コマンド\]** ページのコマンドのリスト ボックスにあるツール バー ボタンを置き換える方法、**\[ユーザー設定\]** ダイアログ ボックスを使用して新しいツール バーを作成できるようにする方法、および **\[カスタマイズ\]** ダイアログ ボックスを表示する方法を示します。  このコード スニペットは [IE のデモのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_IEDemo#4](../../mfc/reference/codesnippet/CPP/cmfctoolbarscustomizedialog-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCToolBarsCustomizeDialog](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)  
  
## 必要条件  
 **ヘッダー :** afxToolBarsCustomizeDialog.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CPropertySheet クラス](../../mfc/reference/cpropertysheet-class.md)