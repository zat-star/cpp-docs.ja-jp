---
title: "RuntimeClassBaseT::GetImplementedIIDS メソッド | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetImplementedIIDS メソッド"
ms.assetid: adae54da-521d-4add-87f5-242fbd85f33b
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RuntimeClassBaseT::GetImplementedIIDS メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
template<  
   typename T  
>  
__forceinline static HRESULT GetImplementedIIDS(  
   _In_ T* implements,  
   _Out_ ULONG *iidCount,  
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids  
);  
```  
  
#### パラメーター  
 `T`  
 `implements` パラメーターの型。  
  
 `implements`  
 `T`パラメーターによって指定された型へのポインター。  
  
 `iidCount`  
 取得するようインターフェイス ID の最大数。  
  
 `iids`  
 この操作が正常に完了したら、インターフェイス ID の配列の型は `T`によって実装しました。  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合は、エラーを示す HRESULT を返します。  
  
## 解説  
 指定された型によって実装されるインターフェイス ID の配列を取得します。  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [RuntimeClassBaseT 構造体](../windows/runtimeclassbaset-structure.md)