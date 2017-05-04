---
title: "Vector::GetMany メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::GetMany"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::GetMany メソッド"
ms.assetid: e2d5ccf4-101a-47e5-a0d8-56f65a7ff28d
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::GetMany メソッド
指定されたインデックスを開始位置として、現在の Vector から項目のシーケンスを取得し、呼び出し元が割り当てた配列にコピーします。  
  
## 構文  
  
```  
  
virtual unsigned int GetMany(  
   unsigned int startIndex,   
   ::Platform::WriteOnlyArray<T>^ dest  
);  
```  
  
#### パラメーター  
 `startIndex`  
 取得する項目の 0 から始まるインデックス。  
  
 `dest`  
 `startIndex` で指定された要素を開始位置とし、Vector の最後の要素を終了位置とする、呼び出し元が割り当てた項目の配列。  
  
## 戻り値  
 取得した項目数。  
  
## 解説  
 この関数は、直接クライアント コードで使用することを目的としたものではありません。 Platform::Vector インスタンスを std::vector インスタンスに効率的に変換できるようにするため、[関数 to\_vector](../cppcx/to-vector-function.md) で内部使用されます。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::Vector クラス](../cppcx/platform-collections-vector-class.md)