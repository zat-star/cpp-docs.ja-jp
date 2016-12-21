---
title: "ComPtr::operator!= 演算子 | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::operator!="
dev_langs: 
  - "C++"
ms.assetid: 63647240-dec7-4eb9-9272-96c07d01493c
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::operator!= 演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ComPtr の 2 種類のオブジェクトが異なるかどうかを示します。  
  
## 構文  
  
```cpp  
bool operator!=(  
   const ComPtr<T>& a,  
   const ComPtr<U>& b  
);  
  
bool operator!=(  
   const ComPtr<T>& a,  
   decltype(__nullptr)  
);  
  
bool operator!=(  
   decltype(__nullptr),  
   const ComPtr<T>& a  
);  
  
```  
  
#### パラメーター  
 `a`  
 ComPtr オブジェクトへの参照。  
  
 `b`  
 別の ComPtr オブジェクトへの参照。  
  
## 戻り値  
 一つ目の演算子は `b`に対応するオブジェクト `a` 等しくない場合があります `true` ; それ以外の場合は `false`。  
  
 2 番目と 3 番目の演算子は、オブジェクトが `a``nullptr`と等しく `true` ;を説明します。それ以外の場合は `false`。  
  
## 必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)   
 [ComPtr クラス](../windows/comptr-class.md)