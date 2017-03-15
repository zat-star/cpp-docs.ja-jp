---
title: "ComPtr::ComPtr コンストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::ComPtr::ComPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ComPtr、コンストラクター"
ms.assetid: eaf70907-beac-458f-a503-2e5e27b0c196
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# ComPtr::ComPtr コンストラクター
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Intializes ComPtr クラスの新しいインスタンス。  オーバーロードは既定を提供し、変換コンストラクター コピーされ、移動します。  
  
## 構文  
  
```  
WRL_NOTHROW ComPtr();  
WRL_NOTHROW ComPtr(  
   decltype(__nullptr)  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   _In_opt_ U *other  
);  
WRL_NOTHROW ComPtr(  
   const ComPtr& other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   const ComPtr<U> &other,  
   typename ENABLE_IF<__is_convertible_to(U*,  
   T*),  
   void *>;  
WRL_NOTHROW ComPtr(  
   _Inout_ ComPtr &&other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   _Inout_ ComPtr<U>&& other,  
   typename ENABLE_IF<__is_convertible_to(U*,  
   T*),  
   void *>;  
```  
  
#### パラメーター  
 `U`  
 `other` パラメーターの型。  
  
 `other`  
 `U` 型のオブジェクト。  
  
## 戻り値  
  
## 解説  
 最初のコンストラクターは、空 implictly オブジェクトを作成するための既定のコンストラクターです。  明示的に空のオブジェクトを作成する 2 番目のコンストラクターは [\_\_nullptr](../windows/nullptr-cpp-component-extensions.md)を指定します。  
  
 3 番目のコンストラクターは、指定されたオブジェクトからオブジェクトを作成します。  
  
 4 つ目と 5 つ目のコンストラクターは、コピー コンストラクターです。  5 番目のコンストラクターは現在の型に変換可能なオブジェクトをコピーします。  
  
 6 つ目と 7 つ目のコンストラクターはムーブ コンストラクターです。  7 番目のコンストラクターは現在の型に変換可能なオブジェクトが移動します。  
  
## 必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [ComPtr クラス](../windows/comptr-class.md)