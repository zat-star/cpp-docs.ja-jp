---
title: "_variant_t 関係演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_variant_t::operator=="
  - "_variant_t.operator!="
  - "_variant_t::operator!="
  - "_variant_t.operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "!= 演算子"
  - "== 演算子, Visual C++ 固有のオブジェクトを使用する"
  - "!= 演算子, 関係演算子"
  - "!= 演算子, バリアント"
  - "== 演算子, バリアント"
  - "operator!=, 関係演算子"
  - "operator!=, バリアント"
  - "operator==, バリアント"
  - "関係演算子, _variant_t クラス"
ms.assetid: 141bacb8-41a2-44dd-b3c0-4ad1f884f4ea
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _variant_t 関係演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 2 つの `_variant_t` オブジェクトを比較して、等しいかどうかを確認します。  
  
## 構文  
  
```  
  
      bool operator==(  
   const VARIANT& varSrc   
) const;  
bool operator==(  
   const VARIANT* pSrc   
) const;  
bool operator!=(  
   const VARIANT& varSrc   
) const;  
bool operator!=(  
   const VARIANT* pSrc   
) const;  
```  
  
#### パラメーター  
 *varSrc*  
 `_variant_t` オブジェクトと比較する **VARIANT**。  
  
 `pSrc`  
 `_variant_t` オブジェクトと比較される **VARIANT** へのポインター。  
  
## 戻り値  
 比較が成立する場合は **true**、それ以外の場合は **false** を返します。  
  
## 解説  
 `_variant_t` オブジェクトを **VARIANT** と比較し、等しいかどうかをテストします。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_variant\_t クラス](../cpp/variant-t-class.md)