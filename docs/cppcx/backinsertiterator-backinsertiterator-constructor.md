---
title: "BackInsertIterator::BackInsertIterator コンストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::BackInsertIterator::BackInsertIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BackInsertIterator::BackInsertIterator コンストラクター"
ms.assetid: ae6f0213-a7bb-43b8-9a5e-7a8dad7c76f8
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# BackInsertIterator::BackInsertIterator コンストラクター
`BackInsertIterator` クラスの新しいインスタンスを初期化します。  
  
## 構文  
  
```  
  
explicit BackInsertIterator(  
   Windows::Foundation::Collections::IVector<T>^ v  
);  
```  
  
#### パラメーター  
 `v`  
 IVector\<T\> オブジェクト。  
  
## 解説  
 `BackInsertIterator` は、`v` パラメーターで指定されたオブジェクトの最後の要素の後に要素を挿入します。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::BackInsertIterator クラス](../cppcx/platform-collections-backinsertiterator-class.md)