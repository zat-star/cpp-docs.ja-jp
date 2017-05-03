---
title: "Array::get メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::Array::get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Array::get メソッド"
ms.assetid: 3bbcd829-35e7-4912-99ba-6ab9de407287
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Array::get メソッド
指定されたインデックス位置にある配列要素への参照を取得します。  
  
## 構文  
  
```  
  
T& get(  
unsigned int index  
)  const;  
```  
  
#### パラメーター  
 `index`  
 配列の要素を識別する 0 から始まるインデックス。 最小インデックスは 0、最大インデックスは[配列コンストラクター](../cppcx/array-constructors.md)の `size` パラメーターで指定された値です。  
  
## 戻り値  
 `index` パラメーターで指定された配列要素。  
  
## 必要条件  
 **ヘッダー:** vccorlib.h  
  
 **名前空間:** Platform  
  
## 参照  
 [Platform::Array クラス](../cppcx/platform-array-class.md)