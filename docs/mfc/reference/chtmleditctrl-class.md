---
title: "CHtmlEditCtrl クラス | Microsoft Docs"
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
  - "CHtmlEditCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHtmlEditCtrl クラス"
ms.assetid: 0fc4a238-b05f-4874-9edc-6a6701f064d9
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHtmlEditCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC ウィンドウ内の WebBrowser ActiveX コントロールの機能が用意されています。  
  
## 構文  
  
```  
class CHtmlEditCtrl: public CWnd,   
   public CHtmlEditCtrlBase< CHtmlEditCtrl >  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CHtmlEditCtrl::CHtmlEditCtrl](../Topic/CHtmlEditCtrl::CHtmlEditCtrl.md)|`CHtmlEditCtrl` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CHtmlEditCtrl::Create](../Topic/CHtmlEditCtrl::Create.md)|WebBrowser ActiveX コントロールを作成し、`CHtmlEditCtrl` のオブジェクトにアタッチします。  この関数は編集モードに自動的に WebBrowser ActiveX コントロールを同期します。|  
|[CHtmlEditCtrl::GetDHtmlDocument](../Topic/CHtmlEditCtrl::GetDHtmlDocument.md)|現在格納されている WebBrowser コントロールで読み込まれるドキュメントの [IHTMLDocument2](https://msdn.microsoft.com/en-us/library/aa752574.aspx) のインターフェイスを取得します。|  
|[CHtmlEditCtrl::GetStartDocument](../Topic/CHtmlEditCtrl::GetStartDocument.md)|既定のドキュメントに含まれる URL を WebBrowser コントロールで読み込むに取得します。|  
  
## 解説  
 ホストされた WebBrowser コントロールが編集モードに自動的に作成後に同期されます。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CHtmlEditCtrlBase](../Topic/CHtmlEditCtrlBase%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CHtmlEditCtrl`  
  
## 必要条件  
 **ヘッダー:** afxhtml.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)