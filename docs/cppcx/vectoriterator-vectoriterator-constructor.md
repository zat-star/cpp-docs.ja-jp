---
title: "VectorIterator::VectorIterator コンストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::VectorIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::VectorIterator コンストラクター"
ms.assetid: 93286731-9499-4bfb-a24b-b302479c38cc
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::VectorIterator コンストラクター
VectorIterator クラスの新しいインスタンスを初期化します。  
  
## 構文  
  
```  
  
VectorIterator();  
  
explicit VectorIterator(  
   Windows::Foundation::Collections::IVector<T>^ v  
);  
```  
  
#### パラメーター  
 `v`  
 IVector\<T\> オブジェクト。  
  
## 解説  
 最初の構文例は既定のコンストラクターです。 2 番目の構文例は、IVector\<T\> オブジェクトから VectorIterator を構築するために使用される明示的なコンストラクターです。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::VectorIterator クラス](../cppcx/platform-collections-vectoriterator-class.md)