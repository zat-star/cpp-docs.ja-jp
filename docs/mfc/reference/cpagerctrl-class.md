---
title: "CPagerCtrl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPagerCtrl クラス"
ms.assetid: 65ac58dd-4f5e-4b7e-b15c-e0d435a7e884
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CPagerCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CPagerCtrl` クラスは、Windows のページャー コントロールをラップします。ページャー コントロールには、外側のウィンドウに収まらない内側のウィンドウをスクロールによって表示する機能があります。  
  
## 構文  
  
```  
class CPagerCtrl : public CWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CPagerCtrl::CPagerCtrl](../Topic/CPagerCtrl::CPagerCtrl.md)|`CPagerCtrl` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CPagerCtrl::Create](../Topic/CPagerCtrl::Create.md)|指定されたスタイルのページャー コントロールを作成し、`CPagerCtrl` の現在のオブジェクトにアタッチします。|  
|[CPagerCtrl::CreateEx](../Topic/CPagerCtrl::CreateEx.md)|指定された拡張スタイルのページャー コントロールを作成し、`CPagerCtrl` の現在のオブジェクトにアタッチします。|  
|[CPagerCtrl::ForwardMouse](../Topic/CPagerCtrl::ForwardMouse.md)|[WM\_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616) のメッセージを現在のページャー コントロールに含まれているペインに転送有効または無効にします。|  
|[CPagerCtrl::GetBkColor](../Topic/CPagerCtrl::GetBkColor.md)|現在のページャー コントロールの背景色を取得します。|  
|[CPagerCtrl::GetBorder](../Topic/CPagerCtrl::GetBorder.md)|現在のページャー コントロールの境界線のサイズを取得します。|  
|[CPagerCtrl::GetButtonSize](../Topic/CPagerCtrl::GetButtonSize.md)|現在のページャー コントロールのボタンのサイズを取得します。|  
|[CPagerCtrl::GetButtonState](../Topic/CPagerCtrl::GetButtonState.md)|現在のページャー コントロールの指定したボタンの状態を取得します。|  
|[CPagerCtrl::GetDropTarget](../Topic/CPagerCtrl::GetDropTarget.md)|現在のページャー コントロールの [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) のインターフェイスを取得します。|  
|[CPagerCtrl::GetScrollPos](../Topic/CPagerCtrl::GetScrollPos.md)|現在のページャー コントロールのスクロール位置を取得します。|  
|[CPagerCtrl::IsButtonDepressed](../Topic/CPagerCtrl::IsButtonDepressed.md)|現在のページャー コントロールのボタンが指定 `pressed` の状態にあるかどうかを示します。|  
|[CPagerCtrl::IsButtonGrayed](../Topic/CPagerCtrl::IsButtonGrayed.md)|現在のページャー コントロールのボタンが指定 `grayed` の状態にあるかどうかを示します。|  
|[CPagerCtrl::IsButtonHot](../Topic/CPagerCtrl::IsButtonHot.md)|現在のページャー コントロールのボタンが指定 `hot` の状態にあるかどうかを示します。|  
|[CPagerCtrl::IsButtonInvisible](../Topic/CPagerCtrl::IsButtonInvisible.md)|現在のページャー コントロールのボタンが指定 `invisible` の状態にあるかどうかを示します。|  
|[CPagerCtrl::IsButtonNormal](../Topic/CPagerCtrl::IsButtonNormal.md)|現在のページャー コントロールのボタンが指定 `normal` の状態にあるかどうかを示します。|  
|[CPagerCtrl::RecalcSize](../Topic/CPagerCtrl::RecalcSize.md)|現在のページャー コントロールが含まれているウィンドウのサイズを再計算します。|  
|[CPagerCtrl::SetBkColor](../Topic/CPagerCtrl::SetBkColor.md)|現在のページャー コントロールの背景色を設定します。|  
|[CPagerCtrl::SetBorder](../Topic/CPagerCtrl::SetBorder.md)|現在のページャー コントロールの境界線のサイズを設定します。|  
|[CPagerCtrl::SetButtonSize](../Topic/CPagerCtrl::SetButtonSize.md)|現在のページャー コントロールのボタンのサイズを設定します。|  
|[CPagerCtrl::SetChild](../Topic/CPagerCtrl::SetChild.md)|現在のページャー コントロールの子のペインを設定します。|  
|[CPagerCtrl::SetScrollPos](../Topic/CPagerCtrl::SetScrollPos.md)|現在のページャー コントロールのスクロール位置を設定します。|  
  
## 解説  
 ページャー コントロールが含まれているウィンドウは、線形と、ビューに含まれるウィンドウをスクロールできるようにする別ペインをです。  ページャー コントロールは、ウィンドウが最も遠い範囲にスクロールされます。消え、が表示されると自動的に 2 個のスクロール ボタンを表示します。  水平または垂直にスクロールするページャー コントロールを作成できます。  
  
 たとえば、アプリケーションに完全に広く項目をすべて表示することでないツール バーがある場合は、ページャー コントロールにツール バーを割り当てるには、ユーザーが項目をすべて表示するに左または右にツール バーをスクロールできます。  Microsoft Internet Explorer Version 4.0 commctrl.dll \(Version 4.71\) は、ページャー コントロールを説明します。  
  
 `CPagerCtrl` のクラスは [CWnd](../Topic/CWnd%20Class.md) のクラスから派生します。  ページャー コントロールの詳細、および図では、[ページャー コントロール](http://msdn.microsoft.com/library/windows/desktop/bb760855)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CPagerCtrl`  
  
## 必要条件  
 **ヘッダー:** afxcmn.h  
  
## 参照  
 [CPagerCtrl Class](../../mfc/reference/cpagerctrl-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [ページャー コントロール](http://msdn.microsoft.com/library/windows/desktop/bb760855)