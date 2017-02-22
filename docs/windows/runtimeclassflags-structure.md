---
title: "RuntimeClassFlags 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClassFlags"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RuntimeClassFlags 構造体"
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# RuntimeClassFlags 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[RuntimeClass](../windows/runtimeclass-class.md)のインスタンスの型が含まれています。  
  
## 構文  
  
```  
template <  
   unsigned int flags  
>  
struct RuntimeClassFlags;  
```  
  
#### パラメーター  
 `flags`  
 [RuntimeClassType 列挙型](../windows/runtimeclasstype-enumeration.md) 値。  
  
## メンバー  
  
### パブリック定数  
  
|名前|説明|  
|--------|--------|  
|[RuntimeClassFlags::value 定数](../windows/runtimeclassflags-value-constant.md)|[RuntimeClassType 列挙型](../windows/runtimeclasstype-enumeration.md) 値を含みます。|  
  
## 継承階層  
 `RuntimeClassFlags`  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)