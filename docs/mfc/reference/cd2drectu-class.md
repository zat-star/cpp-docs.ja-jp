---
title: "CD2DRectU クラス | Microsoft Docs"
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
  - "CD2DRectU"
  - "afxrendertarget/CD2DRectU"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DRectU クラス"
ms.assetid: a62f17d1-011d-4867-8f51-fd7e7c00561d
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CD2DRectU クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`D2D1_RECT_U`のラッパー。  
  
## 構文  
  
```  
class CD2DRectU : public D2D1_RECT_U;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CD2DRectU::CD2DRectU](../Topic/CD2DRectU::CD2DRectU.md)|オーバーロードされます。  `D2D1_RECT_U` のオブジェクトの `CD2DRectU` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CD2DRectU::IsNull](../Topic/CD2DRectU::IsNull.md)|式は有効なデータ \(`null`\) が含まれていないかどうかを示す `boolean` の値を返します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CD2DRectU::operator CRect](../Topic/CD2DRectU::operator%20CRect.md)|`CRect` のオブジェクトに変換します `CD2DRectU`。|  
  
## 継承階層  
 `D2D1_RECT_U`  
  
 [CD2DRectU](../../mfc/reference/cd2drectu-class.md)  
  
## 必要条件  
 **ヘッダー:** afxrendertarget.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)