---
title: "VectorViewIterator::operator&lt; 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator<"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator< 演算子"
ms.assetid: 411c9af9-78b1-4b1b-839b-3bec76020184
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator&lt; 演算子
現在の VectorIterator が、指定された VectorIterator より小さいかどうかを示します。  
  
## 構文  
  
```  
bool operator<(  
   const VectorViewIterator& other  
) const;  
```  
  
#### パラメーター  
 `other`  
 別の VectorIterator。  
  
## 戻り値  
 現在の VectorIterator が `true` より小さい場合は `other`。それ以外の場合は `false`。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::VectorViewIterator クラス](../cppcx/platform-collections-vectorviewiterator-class.md)