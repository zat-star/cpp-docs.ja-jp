---
title: "InterfaceTraits::CastToUnknown メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::InterfaceTraits::CastToUnknown"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CastToUnknown メソッド"
ms.assetid: aca47fa0-3c60-47f2-a73c-258f7160adff
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# InterfaceTraits::CastToUnknown メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
template<  
   typename T  
>  
static __forceinline IUnknown* CastToUnknown(  
   _In_ T* ptr  
);  
```  
  
#### パラメーター  
 `T`  
 `ptr`パラメーターの型。  
  
 `ptr`  
 `T`を入力するポインター。  
  
## 戻り値  
 `Base` が派生である IUnknown へのポインター。  
  
## 解説  
 IUnknown へのポインターに指定したポインターをキャストします。  
  
 `Base`に関する詳細については、[InterfaceTraits 構造体](../windows/interfacetraits-structure.md)のパブリックな Typedef セクションを参照します。  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [InterfaceTraits 構造体](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)