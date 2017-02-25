---
title: "RuntimeClassBaseT::AsIID メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsIID メソッド"
ms.assetid: 90d7df8a-cf9e-4eef-8837-bc1a25f3fa1a
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# RuntimeClassBaseT::AsIID メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
template<  
   typename T  
>  
__forceinline static HRESULT AsIID(  
   _In_ T* implements,  
   REFIID riid,  
   _Deref_out_ void **ppvObject  
);  
```  
  
#### パラメーター  
 `T`  
 インターフェイス ID を実装する型には、パラメーター `riid`で指定します。  
  
 `implements`  
 テンプレート パラメーター `T`で指定されている型の変数。  
  
 `riid`  
 取得するインターフェイスの ID。  
  
 `ppvObject`  
 この操作が正常に終了した場合、インターフェイスへのポインターへのポインターは `riid`パラメーターで指定します。  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合は、エラーを示す HRESULT を返します。  
  
## 解説  
 指定されたインターフェイス ID へのポインターを取得します  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [RuntimeClassBaseT 構造体](../windows/runtimeclassbaset-structure.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)