---
title: "Vector::InsertAt メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::InsertAt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::InsertAt"
ms.assetid: 05b2ca08-234e-4fc0-acfd-cafa148d1577
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::InsertAt メソッド
指定されたインデックスによって識別される要素の後の現在のベクターに、指定された項目を挿入します。  
  
## 構文  
  
```  
  
virtual void InsertAt(  
   unsigned int index,   
   T item)  
```  
  
#### パラメーター  
 `index`  
 ベクター オブジェクト内の特定の要素を指定する、0 から始まる符号なし整数。  
  
 `item`  
 `index` で指定された要素の後のベクターに挿入する項目。`item` の型は *T* 型名によって定義されます。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::Vector クラス](../cppcx/platform-collections-vector-class.md)