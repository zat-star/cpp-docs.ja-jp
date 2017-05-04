---
title: "end 関数 | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Windows::Foundation::Collections::end"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "end 関数"
ms.assetid: fb837bff-fc76-4bae-9096-facf0e03041c
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# end 関数
指定されたインターフェイス パラメーターによってアクセスされるコレクションの末尾を越えて指す反復子を返します。  
  
## 構文  
  
```  
  
template <typename T>  
    ::Platform::Collections::VectorIterator<T>   
    end(  
        IVector<T>^ v       );  
  
template <typename T>  
    ::Platform::Collections::VectorViewIterator<T>   
    end(  
        IVectorView<T>^ v  
       );  
template <typename T>   
    ::Platform::Collections::InputIterator<T>   
    end(  
        IIterable<T>^ i  
       );  
  
```  
  
#### パラメーター  
 `T`  
 テンプレート型パラメーター。  
  
 `v`  
 IVector\<T\> または IVectorView\<T\> インターフェイスによりアクセスされる Vector\<T\> または VectorView\<T\> オブジェクトのコレクション。  
  
 `i`  
 IIterable\<T\> インターフェイスによってアクセスされる任意の [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] オブジェクトのコレクション。  
  
## 戻り値  
 コレクションの末尾を越えて指す反復子。  
  
## 解説  
 最初の 2 つのテンプレート関数は反復子を返し、3 番目のテンプレート関数は入力反復子を返します。  
  
 `end` によって返される [Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md) オブジェクトは、`VectorProxy<T>` 型の要素を格納するプロキシ反復子です。 ただし、プロキシ オブジェクトは、ユーザー コードにはほとんどは表示されません。 詳細については、「[Collections \(C\+\+\/CX\) \(コレクション \(C\+\+\/CX\)\)](../cppcx/collections-c-cx.md)」を参照してください。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Windows::Foundation::Collections  
  
## 参照  
 [Windows::Foundation::Collections 名前空間](../cppcx/windows-foundation-collections-namespace-c-cx.md)