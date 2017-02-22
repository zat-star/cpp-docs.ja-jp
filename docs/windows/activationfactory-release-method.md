---
title: "ActivationFactory::Release メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ActivationFactory::Release"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Release メソッド"
ms.assetid: 5bc25ff0-ee3c-4a2d-a9b6-2d8f158033ad
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ActivationFactory::Release メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ActivationFactory の現在のオブジェクトの参照カウントをデクリメントします。  
  
## 構文  
  
```  
STDMETHOD_(  
   ULONG,  
   Release  
)();  
```  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合は失敗を示す HRESULT を返します。  
  
## 必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [ActivationFactory クラス](../windows/activationfactory-class.md)