---
title: "CPaintDC クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPaintDC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPaintDC クラス"
  - "OnPaint ハンドラー"
  - "WM_PAINT メッセージ"
ms.assetid: 7e245baa-bf9b-403e-a637-7218adf28fab
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CPaintDC クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CDC](../Topic/CDC%20Class.md)から派生したデバイス コンテキスト クラスです。  
  
## 構文  
  
```  
class CPaintDC : public CDC  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CPaintDC::CPaintDC](../Topic/CPaintDC::CPaintDC.md)|指定 [CWnd](../Topic/CWnd%20Class.md)に接続されている `CPaintDC` を構築します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CPaintDC::m\_ps](../Topic/CPaintDC::m_ps.md)|クライアント領域の塗りつぶしに使用する [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) が含まれます。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CPaintDC::m\_hWnd](../Topic/CPaintDC::m_hWnd.md)|この `CPaintDC` のオブジェクトがアタッチされている `HWND`。|  
  
## 解説  
 これは、構築時に [CWnd::BeginPaint](../Topic/CWnd::BeginPaint.md)、破棄時に [CWnd::EndPaint](../Topic/CWnd::EndPaint.md) を実行します。  
  
 `CPaintDC` のオブジェクトは、の `OnPaint` のメッセージ ハンドラー メンバー関数で [WM\_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) のメッセージに応答する場合、通常は使用できません。  
  
 `CPaintDC`の使用の詳細については、[デバイス コンテキスト](../Topic/Device%20Contexts.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CDC](../Topic/CDC%20Class.md)  
  
 `CPaintDC`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [MFC MDI サンプル](../../top/visual-cpp-samples.md)   
 [CDC クラス](../Topic/CDC%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)