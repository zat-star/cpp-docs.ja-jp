---
title: "VectorIterator::operator+ 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator+"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator+ 演算子"
ms.assetid: 5e907537-7d10-4766-a412-e7ea08b3456a
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator+ 演算子
指定された VectorIterator から指定された転置にある要素を参照する VectorIterator を返します。  
  
## 構文  
  
```  
  
VectorIterator operator+(  
   difference_type n) ;  
  
template <  
   typename T  
>  
inline VectorIterator<T> operator+(  
   ptrdiff_t n,  
   const VectorIterator<T>& i  
);  
  
```  
  
#### パラメーター  
 `T`  
 2 番目の構文では、VectorIterator の型名。  
  
 `n`  
 整数のディスプレイスメント。  
  
 `i`  
 2 番目の構文では、VectorIterator。  
  
## 戻り値  
 最初の構文では、現在の VectorIterator から指定された転置にある要素を参照する VectorIterator。  
  
 2 番目の構文では、`i` パラメーターの先頭から指定された転置にある要素を参照する VectorIterator。  
  
## 解説  
 最初の構文例  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [\(NOTINBUILD\) プラットフォーム名前空間](http://msdn.microsoft.com/ja-jp/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)