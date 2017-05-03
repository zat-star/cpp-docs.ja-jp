---
title: "Array コンストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::Array::Array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Array::Array"
ms.assetid: befb8088-3915-4b5c-b7fd-90f79961412d
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Array コンストラクター
クラス テンプレート パラメーター *T* によって指定された型の、変更可能な 1 次元配列を初期化します。  
  
## 構文  
  
```  
  
Array(unsigned int size);  
Array(T* data, unsigned int size);  
  
```  
  
#### パラメーター  
 `T`  
 クラス テンプレート パラメーター。  
  
 `size`  
 配列の要素数。  
  
 `data`  
 この Array オブジェクトを初期化するために使用する型 `T` のデータ配列へのポインター。  
  
## 解説  
 Platform::Array のインスタンスを作成する方法の詳細については、「[Array と WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)」を参照してください。  
  
## 必要条件  
 **ヘッダー:** vccorlib.h  
  
 **名前空間:** Platform  
  
## 参照  
 [Platform::Array クラス](../cppcx/platform-array-class.md)