---
title: "ComPtrRefBase::operator IInspectable** 演算子 | Microsoft Docs"
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
  - "client/Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable**"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator IInspectable** 演算子"
ms.assetid: 06ac1051-606c-449b-a566-cac78ca53762
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtrRefBase::operator IInspectable** 演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
operator IInspectable**() const;  
```  
  
## 解説  
 IInspectable インターフェイス ポインターへのポインター上には [ptr\_](../windows/comptrrefbase-ptr-data-member.md) の現在のデータ メンバーをキャストします。  
  
 エラーは、現在の ComPtrRefBase が IInspectable から派生しなければ表示されます。  
  
 これはキャストされる **\_\_WRL\_CLASSIC\_COM\_\_** が定義されている場合にのみ使用できます。  
  
## 必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [ComPtrRefBase クラス](../windows/comptrrefbase-class.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)