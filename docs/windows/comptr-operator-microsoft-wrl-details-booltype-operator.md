---
title: "ComPtr::operator Microsoft::WRL::Details::BoolType 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: cfba6521-fb30-4fb8-afb2-cfab1cb5e0b8
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::operator Microsoft::WRL::Details::BoolType 演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ComPtr オブジェクトがインターフェイスのオブジェクトの有効期間を管理しているかどうかを示します。  
  
## 構文  
  
```  
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;  
```  
  
## 戻り値  
 インターフェイスがこの ComPtr オブジェクトに関連付けられている場合は、[BoolStruct::Member](../Topic/BoolStruct::Member%20Data%20Member.md) のデータ メンバーのアドレス; それ以外の場合は `nullptr`。  
  
## 必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [ComPtr クラス](../windows/comptr-class.md)   
 [ComPtr::Get メソッド](../windows/comptr-get-method.md)