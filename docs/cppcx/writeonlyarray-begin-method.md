---
title: "WriteOnlyArray::begin メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::WriteOnlyArray::begin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WriteOnlyArray::begin メソッド"
ms.assetid: 25025fa0-8f55-4abf-93ad-71db45ddfae3
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WriteOnlyArray::begin メソッド
配列内の最初の要素へのポインターを返します。  
  
## 構文  
  
```cpp  
T* begin() const;  
```  
  
## 戻り値  
 配列内の最初の要素へのポインター。  
  
## 解説  
 この反復子は、配列の要素を操作するために `std::sort` などの STL アルゴリズムと共に使用できます。  
  
## 必要条件  
 **ヘッダー:** vccorlib.h  
  
 **名前空間:** Platform  
  
## 参照  
 [Platform::WriteOnlyArray クラス](../cppcx/platform-writeonlyarray-class.md)   
 [Array と WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)