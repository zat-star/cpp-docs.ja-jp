---
title: "VectorView::First メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView::First"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView::First メソッド"
ms.assetid: 543a5c5b-8ce3-4be3-9fad-726928de7855
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorView::First メソッド
VectorView 内の最初の要素を指定する反復子を返します。  
  
## 構文  
  
```  
  
virtual Windows::Foundation::Collections::IIterator<T>^   
   First();  
```  
  
## 戻り値  
 VectorView 内の最初の要素を指定する反復子。  
  
## 解説  
 First\(\) によって返される反復子を保持する便利な方法は、[auto](../Topic/auto%20\(C++\).md) 型推論キーワードで宣言された変数に戻り値を代入することです。 たとえば、`auto x = myVectorView->First();` のようにします。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [VectorView Class](http://msdn.microsoft.com/ja-jp/79697692-ae58-40e0-958f-cf1be6347994)