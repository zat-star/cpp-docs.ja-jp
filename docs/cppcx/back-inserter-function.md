---
title: "back_inserter 関数 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Windows::Foundation::Collections::back_inserter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "back_inserter 関数"
ms.assetid: 91476338-5548-44b7-bc7e-2150f4fbe31a
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# back_inserter 関数
指定されたコレクションの末尾に要素を挿入するために使用される反復子を返します。  
  
## 構文  
  
```  
  
template <  
   typename T  
   >  
   ::Platform::BackInsertIterator<T>   
    back_inserter(  
                  IVector<T>^ v  
                 );  
  
template <  
   typename T  
   >  
   ::Platform::BackInsertIterator<T>   
   back_inserter(  
                IObservableVector<T>^ v  
                );  
```  
  
#### パラメーター  
 `T`  
 テンプレート型パラメーター。  
  
 `v`  
 基になるコレクションへのアクセスを提供するインターフェイス ポインター。  
  
## 戻り値  
 反復子。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Windows::Foundation::Collections  
  
## 参照  
 [Windows::Foundation::Collections 名前空間](../cppcx/windows-foundation-collections-namespace-c-cx.md)