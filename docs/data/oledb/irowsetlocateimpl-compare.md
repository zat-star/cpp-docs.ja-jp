---
title: "IRowsetLocateImpl::Compare | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.IRowsetLocateImpl.Compare"
  - "IRowsetLocateImpl::Compare"
  - "IRowsetLocateImpl.Compare"
  - "ATL::IRowsetLocateImpl::Compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Compare メソッド"
ms.assetid: 6f84052c-c68c-480a-982f-03748faa7d5d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetLocateImpl::Compare
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

2 個のブックマークを比較します。  
  
## 構文  
  
```  
  
      STDMETHOD ( Compare )(  
   HCHAPTER /* hReserved */,  
   DBBKMARK cbBookmark1,  
   const BYTE* pBookmark1,  
   DBBKMARK cbBookmark2,  
   const BYTE* pBookmark2,  
   DBCOMPARE* pComparison   
);  
```  
  
#### パラメーター  
 *OLE DB Programmer's Reference*の [IRowsetLocate::Compare](https://msdn.microsoft.com/en-us/library/ms709539.aspx) を参照してください。  
  
## 解説  
 ブックマークのどちらかが標準 OLE DB 定義された [標準のブックマーク](https://msdn.microsoft.com/en-us/library/ms712954.aspx) \(**DBBMK\_FIRST**、**DBBMK\_LAST**、または **DBBMK\_INVALID**\) です。  `pComparison` で返された値は 2 個のブックマーク間の関係が表示:  
  
-   **DBCOMPARE\_LT** \(`cbBookmark1` は `cbBookmark2`の前にあります\)。  
  
-   **DBCOMPARE\_EQ** \(`cbBookmark1` は `cbBookmark2`と同じです\)。  
  
-   **DBCOMPARE\_GT** \(`cbBookmark1` は `cbBookmark2`の後にあります\)。  
  
-   **DBCOMPARE\_NE** \(ブックマークが等しく、順序なし。\)  
  
-   **DBCOMPARE\_NOTCOMPARABLE** \(ブックマークは比較できません\)。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [IRowsetLocateImpl クラス](../../data/oledb/irowsetlocateimpl-class.md)