---
title: "ComPtr::operator= 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::ComPtr::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator= 演算子"
ms.assetid: 1a0c2752-f7d8-4819-9443-07b88b69ef02
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::operator= 演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

現在の ComPtr に値を割り当てます。  
  
## 構文  
  
```  
WRL_NOTHROW ComPtr& operator=(  
   decltype(__nullptr)  
);  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ T *other  
);  
template <  
   typename U  
>  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ U *other  
);  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr &other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr<U>& other  
);  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr &&other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr<U>&& other  
);  
```  
  
#### パラメーター  
 `U`  
 クラス。  
  
 `other`  
 型または他の ComPtr オブジェクトへのポインター、参照、rvalue 参照。  
  
## 戻り値  
 現在の ComPtr オブジェクトへの参照。  
  
## 解説  
 この演算子の一つ目のバージョンは、現在の ComPtr に空の値が代入されます。  
  
 2 番目のバージョンでは、Web インターフェイス ポインターが現在の ComPtr インターフェイス ポインターと同じでない場合は、2 番目のインターフェイス ポインターが現在の ComPtr に割り当てられます。  
  
 3 番目のバージョンでは、Web インターフェイス ポインターが現在の ComPtr に割り当てられます。  
  
 4 番目の形式では、割り当て値のインターフェイス ポインターが現在の ComPtr インターフェイス ポインターと同じでない場合は、2 番目のインターフェイス ポインターが現在の ComPtr に割り当てられます。  
  
 5 番目のバージョンはコピーの;演算子です。ComPtr オブジェクトへの参照が現在の ComPtr に割り当てられます。  
  
 6 番目のバージョンは、移動セマンティクスを使用するコピーの;演算子です。任意の型を静的なキャストと現在の ComPtr オブジェクトに割り当てられた場合 ComPtr への rvalue 参照。  
  
 7 番目のバージョンは、移動セマンティクスを使用するコピーの;演算子です。型 `U` の ComPtr への rvalue 参照は静的なキャストしました、現在の ComPtr オブジェクトに割り当てられたです。  
  
## 必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [ComPtr クラス](../windows/comptr-class.md)