---
title: "VectorView::IndexOf メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView::IndexOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView::IndexOf メソッド"
ms.assetid: 848117ec-ad4a-4a0b-9c1e-9076e5188869
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorView::IndexOf メソッド
現在の VectorView 内で指定された項目を検索し、見つかった場合は項目のインデックスを返します。  
  
## 構文  
  
```  
  
virtual bool IndexOf(  
   T value,  
   unsigned int* index  
);  
```  
  
#### パラメーター  
 `value`  
 検索する項目。  
  
 `index`  
 `value` パラメーターが見つかった場合は、項目の 0 から始まるインデックス。それ以外の場合は 0。  
  
 `index` パラメーターは、項目が VectorView の最初の要素であるか、項目が見つからなかった場合は 0 です。 戻り値が `true` の場合、項目が見つかり、項目は最初の要素です。それ以外の場合は、項目は見つかっていません。  
  
## 戻り値  
 指定した項目が見つかった場合は `true`。それ以外の場合は `false`。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [VectorView Class](http://msdn.microsoft.com/ja-jp/79697692-ae58-40e0-958f-cf1be6347994)