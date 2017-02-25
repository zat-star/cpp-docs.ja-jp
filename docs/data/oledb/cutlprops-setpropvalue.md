---
title: "CUtlProps::SetPropValue | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SetPropValue"
  - "ATL::CUtlProps<T>::SetPropValue"
  - "ATL.CUtlProps<T>.SetPropValue"
  - "ATL.CUtlProps.SetPropValue"
  - "CUtlProps::SetPropValue"
  - "CUtlProps<T>::SetPropValue"
  - "CUtlProps.SetPropValue"
  - "CUtlProps<T>.SetPropValue"
  - "ATL::CUtlProps::SetPropValue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetPropValue メソッド"
ms.assetid: 69a703c0-f640-4ca3-8850-0c4e75d52429
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CUtlProps::SetPropValue
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロパティ セットのプロパティを設定します。  
  
## 構文  
  
```  
  
      HRESULT SetPropValue(  
   const GUID* pguidPropSet,  
   DBPROPID dwPropId,  
   VARIANT* pvValue   
);  
```  
  
#### パラメーター  
 `pguidPropSet`  
 \[\] PropSet の GUID。  
  
 `dwPropId`  
 \[\]プロパティ インデックス。  
  
 `pvValue`  
 \[\]新しいプロパティ値を含むバリアントへのポインター。  
  
## 戻り値  
 成功した場合、`S_OK` の`Failure`。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [CUtlProps クラス](../../data/oledb/cutlprops-class.md)