---
title: "to_vector 関数 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Windows::Foundation::Collections::to_vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "to_vector 関数"
ms.assetid: 9cdd5123-7243-4def-a1d3-162e0bf6219e
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 3
---
# to_vector 関数
値が、指定された IVector または IVectorView パラメーターの基になるコレクションと同じである `std::vector` を返します。  
  
## 構文  
  
```  
template <  
   typename T  
>  
inline ::std::vector<T> to_vector(  
   IVector<T>^ v  
);  
template <  
   typename T  
>  
inline ::std::vector<T> to_vector(  
   IVectorView<T>^ v  
);  
```  
  
#### パラメーター  
 `T`  
 テンプレート型パラメーター。  
  
 `v`  
 基になる Vector または VectorView オブジェクトへのアクセスを提供する IVector または IVectorView インターフェイス。  
  
## 戻り値  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Windows::Foundation::Collections  
  
## 参照  
 [Windows::Foundation::Collections 名前空間](../cppcx/windows-foundation-collections-namespace-c-cx.md)