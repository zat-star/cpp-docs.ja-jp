---
title: "VectorIterator::operator-&gt; 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator->"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator-> 演算子"
ms.assetid: d6caed5c-4899-45f8-95a2-687eafeeb8e1
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator-&gt; 演算子
現在の VectorIterator により参照される要素のアドレスを取得します。  
  
## 構文  
  
```  
Detail::ArrowProxy<T> operator->() const;  
```  
  
## 戻り値  
 現在の VectorIterator により参照される要素の値。  
  
 戻り値の型は、この演算子の実装に必要な、指定されていない内部型です。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::VectorIterator クラス](../cppcx/platform-collections-vectoriterator-class.md)