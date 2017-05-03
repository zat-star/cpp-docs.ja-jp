---
title: "VectorView::GetMany メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView::GetMany"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView::GetMany メソッド"
ms.assetid: 67d9348f-66fe-417e-9e25-5de0a3cd306c
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorView::GetMany メソッド
指定されたインデックスを開始位置として、現在の VectorView から項目のシーケンスを取得します。  
  
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
 この操作が完了するときに、`startIndex` で指定された要素を開始位置とし、VectorView 内の最後の要素を終了位置とする、項目の配列。  
  
## 戻り値  
 取得した項目数。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [VectorView Class](http://msdn.microsoft.com/ja-jp/79697692-ae58-40e0-958f-cf1be6347994)