---
title: "VectorIterator::operator-= 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator-="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator-= 演算子"
ms.assetid: 30bcf93c-4760-410d-b344-09741be10069
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator-= 演算子
指定されたディスプレイスメントだけ現在の VectorIterator をデクリメントします。  
  
## 構文  
  
```  
VectorIterator& operator-=(  
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
 [Platform::Collections::VectorIterator クラス](../cppcx/platform-collections-vectoriterator-class.md)