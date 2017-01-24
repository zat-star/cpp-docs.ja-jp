---
title: "CClientDC クラス | Microsoft Docs"
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
  - "CClientDC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CClientDC クラス"
  - "CDC クラス, デバイス コンテキスト (クライアント領域の)"
  - "クライアント領域デバイス コンテキスト"
  - "デバイス コンテキスト, クライアント領域"
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CClientDC クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

構築時の Windows 関数 [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871)、破棄時に [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920) の呼び出しを処理します。  
  
## 構文  
  
```  
  
class CClientDC : public CDC  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CClientDC::CClientDC](../Topic/CClientDC::CClientDC.md)|接続された `CWnd`への `CClientDC` オブジェクトを構築します。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CClientDC::m\_hWnd](../Topic/CClientDC::m_hWnd.md)|この `CClientDC` が有効であるウィンドウの `HWND`。|  
  
## 解説  
 これは `CClientDC` のオブジェクトに関連付けられたデバイス コンテキストがウィンドウのクライアント領域であることを意味します。  
  
 `CClientDC`の詳細については、[デバイス コンテキスト](../Topic/Device%20Contexts.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CDC](../Topic/CDC%20Class.md)  
  
 `CClientDC`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [MFC MDI サンプル](../../top/visual-cpp-samples.md)   
 [CDC クラス](../Topic/CDC%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDC クラス](../Topic/CDC%20Class.md)