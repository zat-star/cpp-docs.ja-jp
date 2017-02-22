---
title: "CGdiObject クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CGdiObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ブラシ, 基本クラス"
  - "CGdiObject クラス"
  - "フォント, 基本クラス"
  - "GDI オブジェクト, 基本クラス"
  - "パレット, 基本クラス"
  - "ペン, 基本クラス"
  - "領域, 基本クラス"
ms.assetid: 1cba3ba5-3d49-4e43-8293-209299f2f6f4
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CGdiObject クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ビットマップ、領域、ブラシ、ペン、パレット、フォントなどの Windows のさまざまな種類のグラフィックス デバイス インターフェイス \(GDI\) の基本クラスを提供します。  
  
## 構文  
  
```  
class CGdiObject : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CGdiObject::CGdiObject](../Topic/CGdiObject::CGdiObject.md)|`CGdiObject` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CGdiObject::Attach](../Topic/CGdiObject::Attach.md)|`CGdiObject` のオブジェクトへの Windows GDI オブジェクトをアタッチします。|  
|[CGdiObject::CreateStockObject](../Topic/CGdiObject::CreateStockObject.md)|Windows で定義済みのストック ペン、ブラシ、フォントの 1 種類のハンドルを取得します。|  
|[CGdiObject::DeleteObject](../Topic/CGdiObject::DeleteObject.md)|オブジェクトに関連付けられたすべてのシステムのメモリの解放によって割り当てられたメモリから `CGdiObject` のオブジェクトへの Windows GDI オブジェクトを削除します。|  
|[CGdiObject::DeleteTempMap](../Topic/CGdiObject::DeleteTempMap.md)|`FromHandle`によって作成された `CGdiObject` の一時的なオブジェクトを削除します。|  
|[CGdiObject::Detach](../Topic/CGdiObject::Detach.md)|`CGdiObject` のオブジェクトの Windows GDI オブジェクトをデタッチし、Windows GDI オブジェクトへのハンドルを返します。|  
|[CGdiObject::FromHandle](../Topic/CGdiObject::FromHandle.md)|Windows GDI オブジェクトへのハンドルを持つ `CGdiObject` オブジェクトへのポインターを返します。|  
|[CGdiObject::GetObject](../Topic/CGdiObject::GetObject.md)|アタッチされた `CGdiObject` のオブジェクトへの Windows GDI オブジェクトを説明するデータのバッファーに格納します。|  
|[CGdiObject::GetObjectType](../Topic/CGdiObject::GetObjectType.md)|GDI オブジェクトの型を取得します。|  
|[CGdiObject::GetSafeHandle](../Topic/CGdiObject::GetSafeHandle.md)|`NULL` がを返した場合 `this` が `NULL`である `m_hObject` を返します。|  
|[CGdiObject::UnrealizeObject](../Topic/CGdiObject::UnrealizeObject.md)|ブラシの原点をリセットするか、または論理パレットをリセットします。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CGdiObject::operator \!\=](../Topic/CGdiObject::operator%20!=.md)|2 個の GDI オブジェクトが論理的に等しくないかどうかを判定します。|  
|[CGdiObject::operator \=\=](../Topic/CGdiObject::operator%20==.md)|2 個の GDI オブジェクトが論理的に等しいかどうかを判定します。|  
|[CGdiObject::operator HGDIOBJ](../Topic/CGdiObject::operator%20HGDIOBJ.md)|アタッチされた Windows GDI オブジェクトに `HANDLE` を取得します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CGdiObject::m\_hObject](../Topic/CGdiObject::m_hObject.md)|`HBITMAP`、`HPALETTE`、`HRGN`、`HBRUSH`、このオブジェクトにアタッチされている `HPEN`、または `HFONT` を含む `HANDLE`。|  
  
## 解説  
 は `CGdiObject` を直接作成されません。  なく、`CPen` または `CBrush`のような派生クラスの 1 つがからオブジェクトを作成します。  
  
 `CGdiObject` の詳細については、「[グラフィック オブジェクト](../../mfc/graphic-objects.md)」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CGdiObject`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CBitmap クラス](../../mfc/reference/cbitmap-class.md)   
 [CBrush クラス](../../mfc/reference/cbrush-class.md)   
 [CFont クラス](../../mfc/reference/cfont-class.md)   
 [CPalette クラス](../../mfc/reference/cpalette-class.md)   
 [CPen クラス](../Topic/CPen%20Class.md)   
 [CRgn クラス](../../mfc/reference/crgn-class.md)