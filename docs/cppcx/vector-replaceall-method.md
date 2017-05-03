---
title: "Vector::ReplaceAll メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::ReplaceAll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::ReplaceAll"
ms.assetid: dec905f9-80fc-4aa0-ad04-bbab10feb0b2
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::ReplaceAll メソッド
現在のベクターの要素を削除し、指定された配列の要素を挿入します。  
  
## 構文  
  
```  
  
virtual void ReplaceAll(  
   const ::Platform::Array<T>^ arr  
);  
```  
  
#### パラメーター  
 `arr`  
 *T* 型名によって定義される型を持つ、オブジェクトの配列。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::Vector クラス](../cppcx/platform-collections-vector-class.md)