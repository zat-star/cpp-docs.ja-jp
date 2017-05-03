---
title: "Vector::IndexOf メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::IndexOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::IndexOf メソッド"
ms.assetid: 4a965992-3858-4e3f-992a-b94c0580b2f7
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::IndexOf メソッド
現在のベクター内で指定された項目を検索し、見つかった場合は項目のインデックスを返します。  
  
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
  
 項目が Vector の最初の要素であるか、項目が見つからなかった場合、`index` パラメーターは 0 です。 戻り値が `true` の場合、項目が見つかり、項目は最初の要素です。それ以外の場合は、項目は見つかっていません。  
  
## 戻り値  
 指定した項目が見つかった場合は `true`。それ以外の場合は `false`。  
  
## 解説  
 IndexOf は、std::find\_if を使用して項目を検索します。 このため、find\_if が必要とする等価比較を有効にするために、カスタム要素の種類で \=\= および \!\= 演算子をオーバーロードする必要があります。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::Vector クラス](../cppcx/platform-collections-vector-class.md)