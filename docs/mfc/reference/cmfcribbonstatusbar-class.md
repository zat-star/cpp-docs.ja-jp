---
title: "CMFCRibbonStatusBar クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonStatusBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonStatusBar クラス"
ms.assetid: 921eb57f-3b40-49fa-a38c-3f2fb6dc2893
caps.latest.revision: 37
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 39
---
# CMFCRibbonStatusBar クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCRibbonStatusBar` クラスは、リボン要素を表示できるステータス バー コントロールを実装します。  
  
## 構文  
  
```  
class CMFCRibbonStatusBar : public CMFCRibbonBar  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonStatusBar::AddDynamicElement](../Topic/CMFCRibbonStatusBar::AddDynamicElement.md)|リボン ステータス バーに動的な要素を追加します。|  
|[CMFCRibbonStatusBar::AddElement](../Topic/CMFCRibbonStatusBar::AddElement.md)|新しいリボン要素をリボン ステータス バーに追加します。|  
|[CMFCRibbonStatusBar::AddExtendedElement](../Topic/CMFCRibbonStatusBar::AddExtendedElement.md)|リボン ステータス バーの拡張領域にリボン要素を追加します。|  
|[CMFCRibbonStatusBar::AddSeparator](../Topic/CMFCRibbonStatusBar::AddSeparator.md)|リボン ステータス バーに区分線を追加します。|  
|[CMFCRibbonStatusBar::Create](../Topic/CMFCRibbonStatusBar::Create.md)|リボン ステータス バーを作成します。|  
|[CMFCRibbonStatusBar::CreateEx](../Topic/CMFCRibbonStatusBar::CreateEx.md)|拡張スタイルを持つリボン ステータス バーを作成します。|  
|[CMFCRibbonStatusBar::FindByID](../Topic/CMFCRibbonStatusBar::FindByID.md)||  
|[CMFCRibbonStatusBar::FindElement](../Topic/CMFCRibbonStatusBar::FindElement.md)|指定したコマンド ID を持つ要素へのポインターを返します。|  
|[CMFCRibbonStatusBar::GetCount](../Topic/CMFCRibbonStatusBar::GetCount.md)|リボン ステータス バーのメイン領域にある要素数を返します。|  
|[CMFCRibbonStatusBar::GetElement](../Topic/CMFCRibbonStatusBar::GetElement.md)|指定されたインデックスにある要素へのポインターを返します。|  
|[CMFCRibbonStatusBar::GetExCount](../Topic/CMFCRibbonStatusBar::GetExCount.md)|リボン ステータス バーの拡張領域にある要素数を返します。|  
|[CMFCRibbonStatusBar::GetExElement](../Topic/CMFCRibbonStatusBar::GetExElement.md)|リボン ステータス バーの拡張領域で、指定されたインデックスにある要素へのポインターを返します。|  
|[CMFCRibbonStatusBar::GetExtendedArea](../Topic/CMFCRibbonStatusBar::GetExtendedArea.md)||  
|[CMFCRibbonStatusBar::GetSpace](../Topic/CMFCRibbonStatusBar::GetSpace.md)||  
|[CMFCRibbonStatusBar::IsBottomFrame](../Topic/CMFCRibbonStatusBar::IsBottomFrame.md)||  
|[CMFCRibbonStatusBar::IsExtendedElement](../Topic/CMFCRibbonStatusBar::IsExtendedElement.md)||  
|[CMFCRibbonStatusBar::IsInformationMode](../Topic/CMFCRibbonStatusBar::IsInformationMode.md)|リボン ステータス バーの情報モードが有効かどうかを判断します。|  
|[CMFCRibbonStatusBar::RecalcLayout](../Topic/CMFCRibbonStatusBar::RecalcLayout.md)|\([CMFCRibbonBar::RecalcLayout](../Topic/CMFCRibbonBar::RecalcLayout.md) をオーバーライドします。\)|  
|[CMFCRibbonStatusBar::RemoveAll](../Topic/CMFCRibbonStatusBar::RemoveAll.md)|リボン ステータス バーからすべての要素を削除します。|  
|[CMFCRibbonStatusBar::RemoveElement](../Topic/CMFCRibbonStatusBar::RemoveElement.md)|指定したコマンド ID を持つ要素をリボン ステータス バーから削除します。|  
|[CMFCRibbonStatusBar::SetInformation](../Topic/CMFCRibbonStatusBar::SetInformation.md)|リボン ステータス バーの情報モードを有効または無効にします。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonStatusBar::OnDrawInformation](../Topic/CMFCRibbonStatusBar::OnDrawInformation.md)|情報モードが有効である場合に、リボン ステータス バーに表示される情報文字列を表示します。|  
  
## 解説  
 ユーザーは、リボン ステータス バーの組み込みコンテキスト メニューを使用して、リボン ステータス バー上のリボン要素の表示状態を変更できます。  要素の追加または削除を動的に行うことができます。  
  
 リボン ステータス バーには、メイン領域と拡張領域の 2 つの領域があります。  拡張領域は、リボン ステータス バーの右側にメイン領域とは異なる色で表示されます。  
  
 通常、ステータス バーのメイン領域には状態通知が表示され、拡張領域にはビュー コントロールが表示されます。  拡張領域は、ユーザーがリボン ステータス バーのサイズを変更した場合も、可能な限り表示されています。  
  
## 使用例  
 `CMFCRibbonStatusBar` クラスのさまざまなメソッドの使用方法を次の例に示します。  リボン ステータス バーへの新しいリボン要素の追加、リボン ステータス バーの拡張領域へのリボン要素の追加、区分線の追加、およびリボン ステータス バーの通常モードの有効化を行う方法を示しています。  
  
 [!code-cpp[NVC_MFC_RibbonApp#15](../../mfc/reference/codesnippet/CPP/cmfcribbonstatusbar-class_1.cpp)]  
[!code-cpp[NVC_MFC_RibbonApp#16](../../mfc/reference/codesnippet/CPP/cmfcribbonstatusbar-class_2.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)  
  
 [CMFCRibbonStatusBar](../../mfc/reference/cmfcribbonstatusbar-class.md)  
  
## 必要条件  
 **ヘッダー :** afxribbonstatusbar.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)   
 [CMFCRibbonBaseElement クラス](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)