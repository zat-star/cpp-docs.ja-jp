---
title: "BackInsertIterator::operator++ 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::BackInsertIterator::operator++"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BackInsertIterator::operator++ 演算子"
ms.assetid: 08324574-db2b-4d95-825e-a93a56f327da
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# BackInsertIterator::operator++ 演算子
現在の BackInsertIterator への参照を返します。 反復子は変更されません。  
  
## 構文  
  
```  
  
BackInsertIterator& operator++();  
  
BackInsertIterator operator++(  
   int  
);  
```  
  
## 戻り値  
 現在の BackInsertIterator への参照。  
  
## 解説  
 仕様では、最初の構文は現在の BackInsertIterator に前置インクリメント演算を行い、2 つ目の構文は現在の BackInsertIterator に後置インクリメント演算を行います。 2 つ目の構文の `int` 型は、実際の整数オペランドではなく後置インクリメント演算を示します。  
  
 ただし、この演算子は実際には BackInsertIterator を変更しません。 代わりに、この演算子は変更されていない現在の反復子への参照を返します。 これは、[operator\*](../cppcx/backinsertiterator-operator-dereference-operator.md) と同じ動作です。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::BackInsertIterator クラス](../cppcx/platform-collections-backinsertiterator-class.md)