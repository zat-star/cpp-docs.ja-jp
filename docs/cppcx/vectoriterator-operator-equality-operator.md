---
title: "VectorIterator::operator== 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator== 演算子"
ms.assetid: 1152153c-a564-40bb-8924-a3c6a0ea3752
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator== 演算子
現在の VectorIterator が、指定された VectorIterator と等しいかどうかを示します。  
  
## 構文  
  
```  
bool operator==(  
   const VectorIterator& other  
) const;  
```  
  
#### パラメーター  
 `other`  
 別の VectorIterator。  
  
## 戻り値  
 現在の VectorIterator が `true` と等しい場合は `other`。それ以外の場合は `false`。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::VectorIterator クラス](../cppcx/platform-collections-vectoriterator-class.md)