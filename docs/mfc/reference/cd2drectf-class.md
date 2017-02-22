---
title: "CD2DRectF クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxrendertarget/CD2DRectF"
  - "CD2DRectF"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DRectF クラス"
ms.assetid: 87c12d87-9d18-4a19-ba14-0f51d6b6835a
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CD2DRectF クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`D2D1_RECT_F`のラッパー。  
  
## 構文  
  
```  
class CD2DRectF : public D2D1_RECT_F;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CD2DRectF::CD2DRectF](../Topic/CD2DRectF::CD2DRectF.md)|オーバーロードされます。  `D2D1_RECT_F` のオブジェクトの `CD2DRectF` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CD2DRectF::IsNull](../Topic/CD2DRectF::IsNull.md)|式は有効なデータ \(`null`\) が含まれていないかどうかを示す `boolean` の値を返します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CD2DRectF::operator CRect](../Topic/CD2DRectF::operator%20CRect.md)|`CRect` のオブジェクトに変換します `CD2DRectF`。|  
  
## 継承階層  
 `D2D1_RECT_F`  
  
 [CD2DRectF](../../mfc/reference/cd2drectf-class.md)  
  
## 必要条件  
 **ヘッダー:** afxrendertarget.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)