---
title: "ClassFactory::Release メソッド | Microsoft Docs"
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
  - "module/Microsoft::WRL::ClassFactory::Release"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Release メソッド"
ms.assetid: 49da2002-f9d6-4d7f-8a65-48c20b1bf99f
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ClassFactory::Release メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ClassFactory の現在のオブジェクトの参照カウントをデクリメントします。  
  
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
 [ClassFactory クラス](../windows/classfactory-class.md)