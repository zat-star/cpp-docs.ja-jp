---
title: "VectorIterator::operator+= 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator+="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator+= 演算子"
ms.assetid: 9fd0d8a9-29ae-439a-b6ee-39e8fcf225ec
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator+= 演算子
指定されたディスプレイスメントだけ現在の VectorIterator をインクリメントします。  
  
## 構文  
  
```  
VectorIterator& operator+=(  
   difference_type n  
);  
```  
  
#### パラメーター  
 `n`  
 整数の転置。  
  
## 戻り値  
 更新された VectorIterator。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::VectorIterator クラス](../cppcx/platform-collections-vectoriterator-class.md)