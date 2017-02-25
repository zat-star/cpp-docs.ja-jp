---
title: "ComPtr::ReleaseAndGetAddressOf メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseAndGetAddressOf メソッド"
ms.assetid: 3751dcb4-d50e-432c-89e4-e736be34d434
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# ComPtr::ReleaseAndGetAddressOf メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

この ComPtr オブジェクトに関連付けられたインターフェイスを解放し、解放されたインターフェイスへのポインターを含む [ptr\_](../windows/comptr-ptr-data-member.md) のデータ メンバーのアドレスを取得します。  
  
## 構文  
  
```  
T** ReleaseAndGetAddressOf();  
```  
  
## 戻り値  
 この ComPtr の [ptr\_](../windows/comptr-ptr-data-member.md) のデータ メンバーのアドレス。  
  
## 必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [ComPtr クラス](../windows/comptr-class.md)   
 [ComPtr::ptr\_ データ メンバー](../windows/comptr-ptr-data-member.md)