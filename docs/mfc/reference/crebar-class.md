---
title: "CReBar クラス | Microsoft Docs"
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
  - "CReBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CReBar クラス"
  - "Internet Explorer 4.0 コモン コントロール"
  - "rebar コントロール, コントロール バー"
ms.assetid: c1ad2720-1d33-4106-8e4e-80aa84f93559
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CReBar クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Rebar コントロールのレイアウト、永続性、および状態に関する情報を提供するコントロール バーです。  
  
## 構文  
  
```  
  
class CReBar : public CControlBar  
  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CReBar::AddBar](../Topic/CReBar::AddBar.md)|Rebar にバンドを追加します。|  
|[CReBar::Create](../Topic/CReBar::Create.md)|Rebar コントロールを作成し、`CReBar` オブジェクトに結び付けます。|  
|[CReBar::GetReBarCtrl](../Topic/CReBar::GetReBarCtrl.md)|基になるコモン コントロールであるに直接アクセスできます。|  
  
## 解説  
 Rebar オブジェクトは、さまざまな子ウィンドウ、通常、エディット ボックス、ツール バー、リスト ボックスなど、他のコントロールを含めることができます。  Rebar オブジェクトは、指定したビットマップに子ウィンドウを表示できます。  アプリケーションが自動的に Rebar のサイズを変更する。ユーザーは、グリップ バーをクリックまたはドラッグして、Rebar のサイズを手動で変更できます。  
  
 ![RebarMenu の例](../../mfc/reference/media/vc4sc61.png "vc4SC61")  
  
## Rebar コントロール  
 Rebar オブジェクトは、ツール バー オブジェクトに似ています。  rebar はバンドのサイズを変更するときにクリック アンド ドラッグ機構を使用します。  Rebar コントロールは、グリップ バー、ビットマップ、テキスト ラベル、子ウィンドウを組み合わせて使用して各バンドが、バンドを含めることができます。  ただし、バンドは、複数の子ウィンドウを含めることはできません。  
  
 **CReBar** は、の実装を提供するために [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) クラスを使用します。  [GetReBarCtrl](../Topic/CReBar::GetReBarCtrl.md) してコントロールのカスタマイズ オプションを利用するには、Rebar コントロールにアクセスできます。  Rebar コントロールの詳細については、`CReBarCtrl`を参照してください。  Rebar コントロールの使用方法の詳細については、[CReBarCtrl を使用する](../Topic/Using%20CReBarCtrl.md)を参照してください。  
  
> [!CAUTION]
>  rebar や rebar コントロールのオブジェクトは、MFC コントロール バーのドッキングをサポートしていません。  **CRebar::EnableDocking** を呼び出すと、アプリケーションはアサートします。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CReBar`  
  
## 必要条件  
 **Header:** afxext.h  
  
## 参照  
 [MFC MFCIE サンプル](../../top/visual-cpp-samples.md)   
 [CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)