---
title: "CMiniFrameWnd クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMiniFrameWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMiniFrameWnd クラス"
  - "ミニフレーム ウィンドウ"
  - "ツール バー [C++]"
ms.assetid: b8f534ed-0532-4d8e-9657-5595cf677749
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CMiniFrameWnd クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

フローティング ツール バーの周りなどで使用される、半分の高さのフレーム ウィンドウを表します。  
  
## 構文  
  
```  
class CMiniFrameWnd : public CFrameWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMiniFrameWnd::CMiniFrameWnd](../Topic/CMiniFrameWnd::CMiniFrameWnd.md)|`CMiniFrameWnd` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMiniFrameWnd::Create](../Topic/CMiniFrameWnd::Create.md)|構造体の後に `CMiniFrameWnd` のオブジェクトを作成します。|  
|[CMiniFrameWnd::CreateEx](../Topic/CMiniFrameWnd::CreateEx.md)|構造体の後に `CMiniFrameWnd` オブジェクト \(追加のオプションで\) 作成します。|  
  
## 解説  
 これらのミニフレーム ウィンドウは標準フレーム ウィンドウのように動作します。ただし、最大化ボタンまたは最小化することがないシステム メニューのシングルクリック文字だけを閉じるか、メニュー、およびがあります。  
  
 `CMiniFrameWnd` のオブジェクトを使用するには、まずオブジェクトを定義します。  その後、ミニフレーム ウィンドウを表示するに [&#91;作成&#93;](../Topic/CMiniFrameWnd::Create.md) のメンバー関数を呼び出します。  
  
 `CMiniFrameWnd` のオブジェクトを使用する方法の詳細については、" " [フローティング ツール バーとドッキング](../../mfc/docking-and-floating-toolbars.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMiniFrameWnd`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)