---
title: "ComPtrRef::operator== 演算子 | Microsoft Docs"
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
  - "client/Microsoft::WRL::Details::ComPtrRef::operator=="
dev_langs: 
  - "C++"
ms.assetid: 95fcf781-b473-4317-88cd-e938778d3c3e
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtrRef::operator== 演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```cpp  
  
bool operator==(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   const Details::ComPtrRef<ComPtr<U>>& b  
);  
  
bool operator==(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   decltype(__nullptr)  
);  
  
bool operator==(  
   decltype(__nullptr),  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
  
bool operator==(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   void* b  
);  
  
bool operator==(  
   void* b,  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
```  
  
#### パラメーター  
 `a`  
 ComPtrRef オブジェクトへの参照。  
  
 `b`  
 匿名型`void*` \(\) への ComPtrRef の別のオブジェクトへの参照、またはポインター。  
  
## 戻り値  
 一つ目の演算子は `b`にオブジェクトへ `a` オブジェクトが等しい `true` ;を説明します。それ以外の場合は `false`。  
  
 2 番目と 3 番目の演算子は、オブジェクトが `a``nullptr`と等しい `true` ;を説明します。それ以外の場合は `false`。  
  
 4 番目と 5 番目の演算子は `b`にオブジェクトへ `a` オブジェクトが等しい `true` ;を説明します。それ以外の場合は `false`。  
  
## 解説  
 ComPtrRef 2 の二つのオブジェクトが等しいかどうかを示します。  
  
## 必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtrRef クラス](../Topic/ComPtrRef%20Class.md)