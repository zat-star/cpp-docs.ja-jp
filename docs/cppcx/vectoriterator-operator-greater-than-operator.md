---
title: "VectorIterator::operator&gt; 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator> 演算子"
ms.assetid: a9a323a4-d28a-4080-a48c-ed4c8ef2eafb
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator&gt; 演算子
現在の VectorIterator が、指定された VectorIterator より大きいかどうかを示します。  
  
## 構文  
  
```cpp  
  
bool operator>(  
   const VectorIterator& other  
) const   
```  
  
#### パラメーター  
 `other`  
 別の VectorIterator。  
  
## 戻り値  
 現在の VectorIterator が `other` より大きい場合は `true`。それ以外の場合は `false`。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::VectorIterator クラス](../cppcx/platform-collections-vectoriterator-class.md)