---
title: "VectorIterator::operatorOperator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator[]"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator[] 演算子"
ms.assetid: e1ba8101-8c16-4be1-b31b-91099d6e81f3
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operatorOperator
現在の VectorIterator から指定された転置にある要素への参照を取得します。  
  
## 構文  
  
```  
  
reference operator[](difference_type n) const;  
```  
  
#### パラメーター  
 `n`  
 整数のディスプレイスメント。  
  
## 戻り値  
 現在の VectorIterator からの `n` 個の要素によって転置される要素。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::VectorIterator クラス](../cppcx/platform-collections-vectoriterator-class.md)