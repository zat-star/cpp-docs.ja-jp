---
title: "VectorViewIterator::operator-= 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator-="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator-= 演算子"
ms.assetid: fc4d5f19-a001-44fd-aabe-972d8b54ca2f
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator-= 演算子
指定されたディスプレイスメントだけ現在の VectorIterator をデクリメントします。  
  
## 構文  
  
```  
VectorViewIterator& operator-=(  
   difference_type n  
);  
```  
  
#### パラメーター  
 `n`  
 整数のディスプレイスメント。  
  
## 戻り値  
 更新された VectorIterator。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::VectorViewIterator クラス](../cppcx/platform-collections-vectorviewiterator-class.md)