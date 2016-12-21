---
title: "CWindowDC クラス | Microsoft Docs"
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
  - "CWindowDC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWindowDC クラス"
  - "デバイス コンテキスト, ウィンドウ"
  - "画面出力クラス"
ms.assetid: 876a3641-4cde-471c-b0d1-fe58b32af79c
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWindowDC クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CDC` の派生クラスです。  
  
## 構文  
  
```  
class CWindowDC : public CDC  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|Name|Description|  
|----------|-----------------|  
|[CWindowDC::CWindowDC](../Topic/CWindowDC::CWindowDC.md)|`CWindowDC` オブジェクトを構築します。|  
  
### プロテクト データ メンバー  
  
|Name|Description|  
|----------|-----------------|  
|[CWindowDC::m\_hWnd](../Topic/CWindowDC::m_hWnd.md)|`HWND` の割り当て先である `CWindowDC`。|  
  
## 解説  
 構築時の [GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947\(v=vs.85\).aspx) Windows 関数の呼び出しと、破棄時の [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920\(v=vs.85\).aspx) の呼び出しを処理します。  つまり、`CWindowDC` オブジェクトは、[CWnd](../Topic/CWnd%20Class.md) の画面全体 \(クライアント領域と非クライアント領域の両方\) にアクセスします。  
  
 `CWindowDC` の使い方の詳細については、「[デバイス コンテキスト](../Topic/Device%20Contexts.md)」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CDC](../Topic/CDC%20Class.md)  
  
 `CWindowDC`  
  
## 必要条件  
 ヘッダー: afxwin.h  
  
## 参照  
 [CDC クラス](../Topic/CDC%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDC クラス](../Topic/CDC%20Class.md)