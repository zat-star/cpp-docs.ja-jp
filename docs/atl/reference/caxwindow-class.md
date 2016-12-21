---
title: "CAxWindow クラス | Microsoft Docs"
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
  - "CAxWindowT"
  - "CAxWindow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, ホスト (ActiveX コントロールを)"
  - "CAxWindow クラス"
ms.assetid: 85e79261-43e4-4770-bde0-1ff87f222b0f
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAxWindow クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、ActiveX コントロールをホストするウィンドウを操作するためのメソッドが用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class CAxWindow : public CWindow  
  
```  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[AttachControl](../Topic/CAxWindow::AttachControl.md)|`CAxWindow` のオブジェクトに既存の ActiveX コントロールをアタッチします。|  
|[CAxWindow](../Topic/CAxWindow::CAxWindow.md)|`CAxWindow` オブジェクトを構築します。|  
|[CreateControl](../Topic/CAxWindow::CreateControl.md)|ActiveX コントロールを作成して初期化し、`CAxWindow` のウィンドウでホストします。|  
|[CreateControlEx](../Topic/CAxWindow::CreateControlEx.md)|ActiveX コントロールを作成し、コントロールからインターフェイスのポインター \(複数可\) を取得します。|  
|[GetWndClassName](../Topic/CAxWindow::GetWndClassName.md)|\(静的関数\) `CAxWindow` のオブジェクトの定義済みのクラス名を取得します。|  
|[QueryControl](../Topic/CAxWindow::QueryControl.md)|ホストされた ActiveX コントロールの **IUnknown** を取得します。|  
|[QueryHost](../Topic/CAxWindow::QueryHost.md)|`CAxWindow` のオブジェクトの **IUnknown** のポインターを取得します。|  
|[SetExternalDispatch](../Topic/CAxWindow::SetExternalDispatch.md)|外部ディスパッチ インターフェイスを `CAxWindow` のオブジェクトによって使用される設定します。|  
|[SetExternalUIHandler](../Topic/CAxWindow::SetExternalUIHandler.md)|外部の **IDocHostUIHandler** のインターフェイスを `CAxWindow` のオブジェクトによって使用される設定します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator \=](../Topic/CAxWindow::operator%20=.md)|**CAxWindow** の既存のオブジェクトに **HWND** を割り当てます。|  
  
## 解説  
 このクラスには、ActiveX コントロールをホストするウィンドウを操作するためのメソッドを提供します。  `CAxWindow`でラップされたホストは、「**AtlAxWin80"**によって提供されます。  
  
 クラス `CAxWindow` は `CAxWindowT` のクラスから特化したクラスとして実装されます。  この特殊化は次のように宣言されています:  
  
 `typedef CAxWindowT<CWindow> CAxWindow;`  
  
 基本クラスを変更する必要がある場合 `CAxWindowT` を使用し、テンプレート引数として新しい基本クラスを指定できます。  
  
## 必要条件  
 **Header:** atlwin.h  
  
## 参照  
 [ATLCON サンプル](../../top/visual-cpp-samples.md)   
 [CWindow クラス](../../atl/reference/cwindow-class.md)   
 [複合コントロールの基本](../Topic/ATL%20Composite%20Control%20Fundamentals.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [コントロール コンテインメント : Q & A 集](../../atl/atl-control-containment-faq.md)