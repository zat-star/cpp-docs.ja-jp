---
title: "CreatorMap::activationId データ メンバー | Microsoft Docs"
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
  - "module/Microsoft::WRL::Details::CreatorMap::activationId"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "activationId データ メンバー"
ms.assetid: 77518b76-6e6a-4b48-8e2e-a4c7c67769e0
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CreatorMap::activationId データ メンバー
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
union {   
   const IID* clsid;  
   const wchar_t* (*getRuntimeName)();  
} activationId;  
```  
  
## パラメーター  
 `clsid`  
 インターフェイス ID  
  
 `getRuntimeName`  
 オブジェクトの Windows ランタイム名を取得する関数。  
  
## 解説  
 標準的な COM クラス ID または Windows ランタイム名で示されるオブジェクト ID を表します。  
  
## 必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [CreatorMap 構造体](../windows/creatormap-structure.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)