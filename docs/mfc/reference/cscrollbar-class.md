---
title: "CScrollBar クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CScrollBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コントロール [MFC], スクロール バー"
  - "CScrollBar クラス"
  - "スクロール バー"
  - "SCROLLBAR ウィンドウ クラス"
  - "Windows コモン コントロール [C++], CScrollBar"
ms.assetid: f3735ca5-73ea-46dc-918b-4d824c9fe47f
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CScrollBar クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows のスクロール バー コントロールの機能を提供します。  
  
## 構文  
  
```  
class CScrollBar : public CWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CScrollBar::CScrollBar](../Topic/CScrollBar::CScrollBar.md)|`CScrollBar` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CScrollBar::Create](../Topic/CScrollBar::Create.md)|Windows のスクロール バーを作成し、`CScrollBar` のオブジェクトにアタッチします。|  
|[CScrollBar::EnableScrollBar](../Topic/CScrollBar::EnableScrollBar.md)|スクロール バーの矢印の一方または両方を有効または無効にします。|  
|[CScrollBar::GetScrollBarInfo](../Topic/CScrollBar::GetScrollBarInfo.md)|`SCROLLBARINFO` の構造体を使用してスクロール バーについての情報を取得します。|  
|[CScrollBar::GetScrollInfo](../Topic/CScrollBar::GetScrollInfo.md)|スクロール バーの情報を取得します。|  
|[CScrollBar::GetScrollLimit](../Topic/CScrollBar::GetScrollLimit.md)|スクロール バーの境界を取得します|  
|[CScrollBar::GetScrollPos](../Topic/CScrollBar::GetScrollPos.md)|スクロール ボックスの現在位置を取得します。|  
|[CScrollBar::GetScrollRange](../Topic/CScrollBar::GetScrollRange.md)|指定されたスクロール バーの現在の最小位置と最大位置を取得します。|  
|[CScrollBar::SetScrollInfo](../Topic/CScrollBar::SetScrollInfo.md)|スクロール バーの情報を設定します。|  
|[CScrollBar::SetScrollPos](../Topic/CScrollBar::SetScrollPos.md)|スクロール ボックスの現在位置を設定します。|  
|[CScrollBar::SetScrollRange](../Topic/CScrollBar::SetScrollRange.md)|指定されたスクロール バーの最小位置と最大位置を設定します。|  
|[CScrollBar::ShowScrollBar](../Topic/CScrollBar::ShowScrollBar.md)|スクロール バーを表示または非表示にします。|  
  
## 解説  
 2 ステップのスクロール バーを作成します。  最初に、`CScrollBar` のオブジェクトを構築するコンストラクターを呼び出して `CScrollBar` および Windows のスクロール バー コントロールを作成し、`CScrollBar` のオブジェクトにアタッチするに [&#91;作成&#93;](../Topic/CScrollBar::Create.md) のメンバー関数を呼び出します。  
  
 ダイアログ ボックス内の `CScrollBar` のオブジェクトをダイアログ リソースを通じて作成する場合は、`CScrollBar` では、ユーザーがダイアログ ボックスを閉じると、破棄されます。  
  
 ウィンドウ内の `CScrollBar` のオブジェクトを作成する場合、そのオブジェクトを破棄する必要があります。  
  
 `CScrollBar` オブジェクトをスタック上に作成したときは、自動的に破棄されます。  **new** 関数を使ってヒープ領域の `CScrollBar` のオブジェクトを作成し、ユーザーが Windows のスクロール バーを終了するときに破棄するオブジェクトの **\[削除\]** を呼び出す必要があります。  
  
 `CScrollBar` オブジェクトのメモリを割り当てた場合、割り当てを破棄するに `CScrollBar` のデストラクターをオーバーライドします。  
  
 `CScrollBar`の使用に関する関連情報については、[コントロール](../../mfc/controls-mfc.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CScrollBar`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [CButton クラス](../../mfc/reference/cbutton-class.md)   
 [CComboBox クラス](../../mfc/reference/ccombobox-class.md)   
 [CEdit クラス](../Topic/CEdit%20Class.md)   
 [CListBox クラス](../Topic/CListBox%20Class.md)   
 [CStatic クラス](../Topic/CStatic%20Class.md)   
 [CDialog クラス](../../mfc/reference/cdialog-class.md)