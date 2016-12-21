---
title: "IRowsetImpl::GetData | Microsoft Docs"
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
  - "ATL.IRowsetImpl.GetData"
  - "ATL::IRowsetImpl::GetData"
  - "IRowsetImpl::GetData"
  - "IRowsetImpl.GetData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetData メソッド [OLE DB]"
ms.assetid: cb15f1cc-bd25-4b74-93c3-db71aa93829c
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetImpl::GetData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

行セットの行のコピーからデータを取得します。  
  
## 構文  
  
```  
  
      STDMETHOD( GetData )(  
   HROW hRow,  
   HACCESSOR hAccessor,  
   void* pDstData   
);  
```  
  
#### パラメーター  
 *OLE DB Programmer's Reference*の [IRowset::GetData](https://msdn.microsoft.com/en-us/library/ms716988.aspx) を参照してください。  
  
 一部のパラメーターは **IRowset::GetData**で説明されている異なる名前で *OLE DB の Programmer's Reference* パラメーターに対応します:  
  
|OLE DB テンプレート パラメーター|*OLE DB の Programmer's Reference* パラメーター|  
|--------------------------|----------------------------------------------|  
|*pDstData*|`pData`|  
  
## 解説  
 、OLE DB データ変換の DLL を使用してデータ変換を処理します。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [IRowsetImpl クラス](../Topic/IRowsetImpl%20Class.md)