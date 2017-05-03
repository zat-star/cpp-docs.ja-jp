---
title: "BackInsertIterator::operator= 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::BackInsertIterator::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BackInsertIterator::operator= 演算子"
ms.assetid: 509c9b4c-14fb-4318-bf65-b8926cc72f4f
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# BackInsertIterator::operator= 演算子
指定されたオブジェクトを、現在のシーケンシャル コレクションの末尾に追加します。  
  
## 構文  
  
```  
  
BackInsertIterator& operator=(  
   const T& t  
);  
```  
  
#### パラメーター  
 `t`  
 現在のコレクションに追加するオブジェクト。  
  
## 戻り値  
 現在の BackInsertIterator への参照。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::BackInsertIterator クラス](../cppcx/platform-collections-backinsertiterator-class.md)