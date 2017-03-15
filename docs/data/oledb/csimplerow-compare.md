---
title: "CSimpleRow::Compare | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CSimpleRow.Compare"
  - "CSimpleRow::Compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Compare メソッド"
ms.assetid: 0bb65f09-c7bc-449b-aa4e-c828cac13510
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CSimpleRow::Compare
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

それらが同じ行のインスタンスを参照している 2 行を参照するために比較します。  
  
## 構文  
  
```  
  
      HRESULT Compare(   
   CSimpleRow* pRow    
);  
```  
  
#### パラメーター  
 `pRow`  
 `CSimpleRow` オブジェクトへのポインター。  
  
## 戻り値  
 `HRESULT` 値 \(通常は 2 行を示す `S_OK`は同じ行のインスタンスか、2 行を示す **S\_FALSE**が異なります。  そのほかの有効な戻り値の *OLE DB Programmer's Reference* の [IRowsetIdentity::IsSameRow](https://msdn.microsoft.com/en-us/library/ms719629.aspx) を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [CSimpleRow クラス](../Topic/CSimpleRow%20Class.md)   
 [CSimpleRow::ReleaseRow](../Topic/CSimpleRow::ReleaseRow.md)   
 [IRowsetImpl::RefRows](../../data/oledb/irowsetimpl-refrows.md)