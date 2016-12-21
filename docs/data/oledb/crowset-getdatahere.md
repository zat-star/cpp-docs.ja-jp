---
title: "CRowset::GetDataHere | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowset<TAccessor>::GetDataHere"
  - "CRowset<TAccessor>.GetDataHere"
  - "CRowset.GetDataHere"
  - "GetDataHere"
  - "CRowset::GetDataHere"
  - "ATL::CRowset::GetDataHere"
  - "ATL::CRowset<TAccessor>::GetDataHere"
  - "ATL.CRowset<TAccessor>.GetDataHere"
  - "ATL.CRowset.GetDataHere"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetDataHere メソッド"
ms.assetid: 2fe2a987-1c4c-4299-876e-0591caf63af4
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::GetDataHere
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定したバッファーに現在の行とその場所からデータを取得します。  
  
## 構文  
  
```  
  
      HRESULT GetDataHere(   
   int nAccessor,   
   void* pBuffer    
) throw( );  
```  
  
#### パラメーター  
 `nAccessor`  
 \[\]データにアクセスするために使用するアクセサーのインデックス番号。  
  
 `pBuffer`  
 \[\]現在のレコードのデータを格納するバッファー。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 この関数を使用する方法の例については [MultiRead サンプル](../../top/visual-cpp-samples.md)を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CRowset クラス](../Topic/CRowset%20Class.md)   
 [CRowset::GetData](../Topic/CRowset::GetData.md)