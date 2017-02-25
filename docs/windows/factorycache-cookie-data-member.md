---
title: "FactoryCache::cookie データ メンバー | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::FactoryCache::cookie"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "クッキー データ メンバー"
ms.assetid: b1bc79af-a896-4e3b-8afa-64733022eddf
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# FactoryCache::cookie データ メンバー
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] インフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
union {   
   WINRT_REGISTRATION_COOKIE winrt;  
   DWORD com;   
} cookie;  
```  
  
## 解説  
 登録された [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] または COM クラス オブジェクトを識別し、オブジェクトの登録を解除するために後で使用します。値を生成します。  
  
## 必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [FactoryCache 構造体](../Topic/FactoryCache%20Structure.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)