---
title: "VectorViewIterator::operator- 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator-"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator- 演算子"
ms.assetid: 03935872-8acc-4919-ae14-f375ca738aac
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator- 演算子
現在の反復子から指定した数の要素を減算して新しい反復子を生成するか、現在の反復子から指定した反復子を減算して反復子間の要素数を生成します。  
  
## 構文  
  
```  
  
VectorViewIterator operator-(  
   difference_type n  
) const;  
  
difference_type operator-(  
   const VectorViewIterator& other  
) const;  
```  
  
#### パラメーター  
 `n`  
 要素の数。  
  
 `other`  
 別の VectorViewIterator。  
  
## 戻り値  
 最初の演算子構文は、現在の VectorViewIterator より `n` 要素少ない VectorViewIterator オブジェクトを返します。 2 番目の演算子構文は、現在の VectorViewIterator と `other` VectorViewIterator の間の要素の数を返します。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::VectorViewIterator クラス](../cppcx/platform-collections-vectorviewiterator-class.md)