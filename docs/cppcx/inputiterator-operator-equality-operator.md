---
title: "InputIterator::operator== 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::InputIterator::operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InputIterator::operator== 演算子"
ms.assetid: 84f1b69a-77b9-467c-ad1a-2fe8a7c3009e
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# InputIterator::operator== 演算子
現在の InputIterator が、指定された InputIterator と等しいかどうかを示します。  
  
## 構文  
  
```  
bool operator==(  
   const InputIterator& other  
) const;  
```  
  
#### パラメーター  
 `other`  
 別の InputIterator。  
  
## 戻り値  
 現在の InputIterator が `true` と等しい場合は `other`。それ以外の場合は `false`。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::InputIterator クラス](../cppcx/platform-collections-inputiterator-class.md)