---
title: "RoInitializeWrapper::RoInitializeWrapper コンストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper"
dev_langs: 
  - "C++"
ms.assetid: c6f7fb07-14af-4574-9135-cea164607f30
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# RoInitializeWrapper::RoInitializeWrapper コンストラクター
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

RoInitializeWrapper クラスの新しいインスタンスを初期化します。  
  
## 構文  
  
```cpp  
RoInitializeWrapper(  
   RO_INIT_TYPE flags)  
  
```  
  
#### パラメーター  
 `flags`  
 サポートを指定する RO\_INIT\_TYPE の列挙体の 1 つが [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]に用意されています。  
  
## 解説  
 RoInitializeWrapper クラスは Windows::Foundation::Initialize \(*flags*\) を呼び出します。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## 参照  
 [HandleT クラス](../Topic/HandleT%20Class.md)