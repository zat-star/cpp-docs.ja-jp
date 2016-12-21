---
title: "CDefaultCharTraits クラス | Microsoft Docs"
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
  - "CDefaultCharTraits"
  - "ATL::CDefaultCharTraits<T>"
  - "ATL.CDefaultCharTraits"
  - "ATL.CDefaultCharTraits<T>"
  - "ATL::CDefaultCharTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDefaultCharTraits クラス"
ms.assetid: f94a3934-597f-401d-8513-ed6924ae069a
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDefaultCharTraits クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、大文字と小文字を変換するための 2 つの静的関数が用意されています。  
  
## 構文  
  
```  
  
      template <  
   typename T  
>  
class CDefaultCharTraits  
```  
  
#### パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDefaultCharTraits::CharToLower](../Topic/CDefaultCharTraits::CharToLower.md)|\(静的\) 文字を大文字に変換するには、この関数を呼び出します。|  
|[CDefaultCharTraits::CharToUpper](../Topic/CDefaultCharTraits::CharToUpper.md)|\(静的\) 文字を小文字に変換するには、この関数を呼び出します。|  
  
## 解説  
 このクラスは、クラス [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)によって使用される関数を提供します。  
  
## 必要条件  
 **Header:** atlcoll.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)