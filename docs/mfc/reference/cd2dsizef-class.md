---
title: "CD2DSizeF クラス | Microsoft Docs"
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
  - "afxrendertarget/CD2DSizeF"
  - "CD2DSizeF"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DSizeF クラス"
ms.assetid: f486a1e1-997d-4286-8cb9-26369dc82055
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CD2DSizeF クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

D2D1\_SIZE\_F のラッパー。  
  
## 構文  
  
```  
class CD2DSizeF : public D2D1_SIZE_F;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CD2DSizeF::CD2DSizeF](../Topic/CD2DSizeF::CD2DSizeF.md)|オーバーロードされます。  `D2D1_SIZE_F` のオブジェクトの `CD2DSizeF` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CD2DSizeF::IsNull](../Topic/CD2DSizeF::IsNull.md)|式は有効なデータ \(`null`\) が含まれていないかどうかを示す `boolean` の値を返します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CD2DSizeF::operator CSize](../Topic/CD2DSizeF::operator%20CSize.md)|`CSize` のオブジェクトに変換します `CD2DSizeF`。|  
  
## 継承階層  
 `D2D1_SIZE_F`  
  
 [CD2DSizeF](../../mfc/reference/cd2dsizef-class.md)  
  
## 必要条件  
 **ヘッダー:** afxrendertarget.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)