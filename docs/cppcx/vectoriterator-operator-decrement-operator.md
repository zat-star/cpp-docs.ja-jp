---
title: "VectorIterator::operator-- 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator--"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator-- 演算子"
ms.assetid: 650a3037-2984-4110-9d7c-cd3756e5f4b9
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator-- 演算子
現在の VectorIterator をデクリメントします。  
  
## 構文  
  
```  
  
VectorIterator& operator--();  
VectorIterator operator--(  
   int  
);  
```  
  
## 戻り値  
 最初の構文は、現在の VectorIterator をデクリメントしてから返します。 2 番目の構文は、現在の VectorIterator のコピーを返し、現在の VectorIterator をデクリメントします。  
  
## 解説  
 最初の VectorIterator 構文は、現在の VectorIterator の前置デクリメントを実行します。  
  
 2 番目の構文は、現在の VectorIterator に後置デクリメントを実行します。 2 つ目の構文の `int` 型は、実際の整数オペランドではなく後置デクリメント演算を示します。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::VectorIterator クラス](../cppcx/platform-collections-vectoriterator-class.md)