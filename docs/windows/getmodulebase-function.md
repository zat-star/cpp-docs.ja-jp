---
title: "GetModuleBase 関数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::GetModuleBase"
dev_langs: 
  - "C++"
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# GetModuleBase 関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[RuntimeClass](../windows/runtimeclass-class.md) オブジェクトの参照カウントをインクリメントするとデクリメントするように [ModuleBase](../windows/modulebase-class.md) のポインターを取得します。  
  
## 構文  
  
```cpp  
inline Details::ModuleBase* GetModuleBase() throw()  
```  
  
## 戻り値  
 `ModuleBase` オブジェクトへのポインター。  
  
## 解説  
 この関数は、オブジェクトの参照カウントをインクリメントし、デクリメントするために内部的に使用されます。  
  
 [ModuleBase::IncrementObjectCount](../windows/modulebase-incrementobjectcount-method.md) と [ModuleBase::DecrementObjectCount](../Topic/ModuleBase::DecrementObjectCount%20Method.md)を呼び出して参照カウントを制御するために使用できます。  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)