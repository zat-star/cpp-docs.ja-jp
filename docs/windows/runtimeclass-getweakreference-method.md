---
title: "RuntimeClass::GetWeakReference メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClass::GetWeakReference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetWeakReference メソッド"
ms.assetid: 26656ace-7f20-4364-87c9-4a75dd30912e
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# RuntimeClass::GetWeakReference メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

RuntimeClass の現在のオブジェクトの弱い参照オブジェクトへのポインターを取得します。  
  
## 構文  
  
```  
STDMETHOD(  
   GetWeakReference  
)(_Deref_out_ IWeakReference **weakReference);  
```  
  
#### パラメーター  
 `weakReference`  
 この操作が完了すると、弱い参照オブジェクトへのポインター。  
  
## 戻り値  
 常には S\_OK を返します。  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [RuntimeClass クラス](../windows/runtimeclass-class.md)