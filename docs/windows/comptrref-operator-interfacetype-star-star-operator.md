---
title: "ComPtrRef::operator InterfaceType** 演算子 | Microsoft Docs"
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
  - "client/Microsoft::WRL::Details::ComPtrRef::operator InterfaceType**"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator InterfaceType** 演算子"
ms.assetid: b32e3240-a4f0-4998-a55f-d4e35dc9a15a
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtrRef::operator InterfaceType** 演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
operator InterfaceType**();  
```  
  
## 解説  
 ComPtrRef の現在のオブジェクトを削除し、ComPtrRef オブジェクトによって表されるインターフェイスへのポインターへのポインターを返します。  
  
## 必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [ComPtrRef クラス](../Topic/ComPtrRef%20Class.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)