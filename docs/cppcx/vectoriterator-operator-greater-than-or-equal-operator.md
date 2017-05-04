---
title: "VectorIterator::operator&gt;= 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator>="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator>= 演算子"
ms.assetid: 8154015e-8da7-4381-8128-d3669eb88e16
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator&gt;= 演算子
現在の VectorIterator が、指定された VectorIterator 以上であるかどうかを示します。  
  
## 構文  
  
```cpp  
  
bool operator>=(  
   const VectorIterator& other  
) const   
```  
  
#### パラメーター  
 `other`  
 別の VectorIterator。  
  
## 戻り値  
 現在の VectorIterator が `true` 以上の場合は `other`。それ以外の場合は `false`。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::VectorIterator クラス](../cppcx/platform-collections-vectoriterator-class.md)