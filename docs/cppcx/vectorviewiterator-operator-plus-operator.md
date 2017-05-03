---
title: "VectorViewIterator::operator+ 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator+"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator+ 演算子"
ms.assetid: 8206de2f-61b3-49cd-9715-d57695d880b3
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator+ 演算子
指定された VectorViewIterator から指定された転置にある要素を参照する VectorViewIterator を返します。  
  
## 構文  
  
```  
  
VectorViewIterator operator+(  
   difference_type n  
) const;  
  
template <  
   typename T  
>   
inline VectorViewIterator<T> operator+  
   (ptrdiff_t n,   
   const VectorViewIterator<T>& i  
);  
  
```  
  
#### パラメーター  
 `T`  
 2 番目の構文では、VectorViewIterator の型名。  
  
 `n`  
 整数のディスプレイスメント。  
  
 `i`  
 2 番目の構文では、VectorViewIterator。  
  
## 戻り値  
 最初の構文では、現在の VectorViewIterator から指定された転置にある要素を参照する VectorViewIterator。  
  
 2 番目の構文では、`i` パラメーターの先頭から指定された転置にある要素を参照する VectorViewIterator。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::VectorViewIterator クラス](../cppcx/platform-collections-vectorviewiterator-class.md)