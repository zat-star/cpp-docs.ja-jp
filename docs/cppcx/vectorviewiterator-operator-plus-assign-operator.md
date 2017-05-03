---
title: "VectorViewIterator::operator+= 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator+="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator+= 演算子"
ms.assetid: 2009e54e-a4f2-444a-b729-a1b6b8b707bb
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator+= 演算子
指定された転置数だけ現在の VectorViewIterator をインクリメントします。  
  
## 構文  
  
```  
VectorViewIterator& operator+=(  
   difference_type n  
);  
```  
  
#### パラメーター  
 `n`  
 整数の転置。  
  
## 戻り値  
 更新された VectorViewIterator。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::VectorViewIterator クラス](../cppcx/platform-collections-vectorviewiterator-class.md)