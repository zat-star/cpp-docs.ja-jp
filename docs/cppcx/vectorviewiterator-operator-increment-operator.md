---
title: "VectorViewIterator::operator++ 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator++"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator++ 演算子"
ms.assetid: 5391e6e2-a7ee-4dab-8cee-b2237894246f
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator++ 演算子
現在の VectorViewIterator をインクリメントします。  
  
## 構文  
  
```  
  
VectorViewIterator& operator++();  
VectorViewIterator operator++(  
   int  
);  
```  
  
## 戻り値  
 最初の構文は、現在の VectorViewIterator をインクリメントしてから返します。 2 番目の構文は、現在の VectorViewIterator のコピーを返し、現在の VectorViewIterator をインクリメントします。  
  
## 解説  
 最初の VectorViewIterator 構文は、現在の VectorViewIterator の前置インクリメントを実行します。  
  
 2 番目の構文は、現在の VectorViewIterator の後置インクリメントを実行します。 2 つ目の構文の `int` 型は、実際の整数オペランドではなく後置インクリメント演算を示します。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::VectorViewIterator クラス](../cppcx/platform-collections-vectorviewiterator-class.md)