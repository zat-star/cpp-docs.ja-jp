---
title: "CMFCRibbonSeparator クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "GetThisClass"
  - "CMFCRibbonSeparator::GetThisClass"
  - "CMFCRibbonSeparator.CreateObject"
  - "CMFCRibbonSeparator::CreateObject"
  - "CMFCRibbonSeparator"
  - "CreateObject"
  - "CMFCRibbonSeparator.GetThisClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonSeparator クラス"
  - "CreateObject メソッド"
  - "GetThisClass メソッド"
ms.assetid: bedb1a53-cb07-4c3c-be12-698c5409e7cf
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CMFCRibbonSeparator クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

リボンの区分線を実装します。  
  
## 構文  
  
```  
class CMFCRibbonSeparator : public CMFCRibbonBaseElement  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCRibbonSeparator::CMFCRibbonSeparator](../Topic/CMFCRibbonSeparator::CMFCRibbonSeparator.md)|`CMFCRibbonSeparator` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCRibbonSeparator::AddToListBox](../Topic/CMFCRibbonSeparator::AddToListBox.md)|**\[カスタマイズ\]** ダイアログ ボックスの **\[コマンド\]** ボックスの一覧に区分線を追加します。  \([CMFCRibbonBaseElement::AddToListBox](../Topic/CMFCRibbonBaseElement::AddToListBox.md) をオーバーライドします。\)|  
|`CMFCRibbonSeparator::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークによって使用されます。|  
|`CMFCRibbonSeparator::GetThisClass`|このクラス型に関連付けられた [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|  
  
### プロテクト メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCRibbonSeparator::CopyFrom](../Topic/CMFCRibbonSeparator::CopyFrom.md)|他のオブジェクトからコピーして区分線のメンバー変数を設定するコピー メソッド。|  
|[CMFCRibbonSeparator::GetRegularSize](../Topic/CMFCRibbonSeparator::GetRegularSize.md)|区分線のサイズを返します。|  
|[CMFCRibbonSeparator::IsSeparator](../Topic/CMFCRibbonSeparator::IsSeparator.md)|対象が区分線であるかどうかを示します。|  
|[CMFCRibbonSeparator::IsTabStop](../Topic/CMFCRibbonSeparator::IsTabStop.md)|これがタブ ストップであるかどうかを示します。|  
|[CMFCRibbonSeparator::OnDraw](../Topic/CMFCRibbonSeparator::OnDraw.md)|リボンまたはクイック アクセス ツール バーに区分線を描画するために、システムによって呼び出されます。|  
|[CMFCRibbonSeparator::OnDrawOnList](../Topic/CMFCRibbonSeparator::OnDrawOnList.md)|**\[コマンド\]** ボックスの一覧に区分線を描画するために、システムによって呼び出されます。|  
  
## 解説  
 リボンの区分線とは、リボン要素を論理的に仕切る垂直線または水平線です。  区分線は、リボン コントロール、メイン アプリケーション メニュー、リボン ステータス バー、およびクイック アクセス ツール バーに描画できます。  
  
 アプリケーションで区分線を使用するには、新しいオブジェクトを構築し、それを次のようにメイン アプリケーション メニューに追加します。  
  
```  
CMFCRibbonMainPanel* pMainPanel = m_wndRibbonBar.AddMainCategory(_T("Main Menu"), IDB_FILESMALL, IDB_FILELARGE);   
...  
pMainPanel->Add(new CMFCRibbonSeparator(TRUE));  
```  
  
 区分線をリボン パネルに追加するには、[CMFCRibbonPanel::AddSeparator](../Topic/CMFCRibbonPanel::AddSeparator.md) を呼び出します。  区分線は、`AddSeparator` メソッドによって内部的に割り当てられ、追加されます。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSeparator](../../mfc/reference/cmfcribbonseparator-class.md)  
  
## 必要条件  
 **ヘッダー :** afxbaseribbonelement.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)