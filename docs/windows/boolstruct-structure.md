---
title: "BoolStruct 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "internal/Microsoft::WRL::Details::BoolStruct"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BoolStruct 構造体"
ms.assetid: 666eae78-e81d-4fb7-a9e4-1ba617d6d4cd
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# BoolStruct 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
struct BoolStruct;  
```  
  
## 解説  
 BoolStruct 構造体でインターフェイスの ComPtr オブジェクトの有効期間を管理しているかどうかを定義します。  BoolStruct は [BoolType \(\)](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md) の演算子によって内部的に使用されます。  
  
## メンバー  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[BoolStruct::Member データ メンバー](../Topic/BoolStruct::Member%20Data%20Member.md)|、[ComPtr](../windows/comptr-class.md) を指定し、あることをインターフェイスのオブジェクトの有効期間を管理します。|  
  
## 継承階層  
 `BoolStruct`  
  
## 必要条件  
 **ヘッダー:** internal.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtr::operator Microsoft::WRL::Details::BoolType 演算子](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)