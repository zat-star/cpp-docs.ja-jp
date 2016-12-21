---
title: "ActivateInstance 関数 | Microsoft Docs"
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
  - "client/Windows::Foundation::ActivateInstance"
  - "client/ABI::Windows::Foundation::ActivateInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActivateInstance 関数"
ms.assetid: 8cfd1dd9-5fda-4cc2-acf8-d40e783b3875
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ActivateInstance 関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

レジスタは、指定された ID クラスで定義されている特定の型のインスタンスを取得し、  
  
## 構文  
  
```  
template<  
   typename T  
>  
inline HRESULT ActivateInstance(  
   _In_ HSTRING activatableClassId,  
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> instance  
);  
```  
  
#### パラメーター  
 `T`  
 アクティブにする型。  
  
 `activatableClassId`  
 パラメーター `T`を定義するクラスの ID 名。  
  
 `instance`  
 この操作が完了すると、`T`のインスタンスへの参照。  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合は、エラーの原因を示すエラー HRESULT。  
  
## 必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Windows::Foundation  
  
## 参照  
 [Windows::Foundation 名前空間](../Topic/Windows::Foundation%20Namespace.md)