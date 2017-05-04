---
title: "VectorView::GetAt メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView::GetAt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView::GetAt メソッド"
ms.assetid: 01c5feda-2a97-4429-ae15-4aced96ce332
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorView::GetAt メソッド
指定されたインデックスで示される現在の VectorView の要素を取得します。  
  
## 構文  
  
```  
  
T GetAt(  
   UInt32 index  
);  
```  
  
#### パラメーター  
 `index`  
 VectorView オブジェクト内の特定の要素を指定する、0 から始まる符号なし整数。  
  
## 戻り値  
 `index` パラメーターで指定された要素。 要素の型は、VectorView テンプレート パラメーター *T* によって指定されます。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [VectorView Class](http://msdn.microsoft.com/ja-jp/79697692-ae58-40e0-958f-cf1be6347994)