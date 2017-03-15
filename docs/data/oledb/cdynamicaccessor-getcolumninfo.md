---
title: "CDynamicAccessor::GetColumnInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetColumnInfo"
  - "ATL.CDynamicAccessor.GetColumnInfo"
  - "ATL::CDynamicAccessor::GetColumnInfo"
  - "CDynamicAccessor.GetColumnInfo"
  - "CDynamicAccessor::GetColumnInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetColumnInfo メソッド"
ms.assetid: 7f2102ea-b7cc-4714-812f-3ca2857f4b9a
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::GetColumnInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ほとんどのコンシューマーが必要とする列のメタデータを返します。  
  
## 構文  
  
```  
  
      HRESULT GetColumnInfo(   
   IRowset* pRowset,   
   DBORDINAL* pColumns,   
   DBCOLUMNINFO** ppColumnInfo,   
   OLECHAR** ppStringsBuffer    
) throw( );  
```  
  
#### パラメーター  
 `pRowset`  
 \[\] [IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx) インターフェイスへのポインター。  
  
 *pColumns*  
 \[\]行セットの列数を返すメモリへのポインター; この数は 1 がある場合、ブックマーク列が含まれます。  
  
 *ppColumnInfo*  
 \[\] **DBCOLUMNINFO** の配列を返すことで構成するメモリへのポインター。  「DBCOLUMNINFO 構成して *OLE DB Programmer's Reference*の [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) 」を参照してください。  
  
 `ppStringsBuffer`  
 \[\]単一の割り当てブロック内のすべての文字列値のストレージへのポインター \(名前は *columnid* 内または *pwszName*で使用される\) を返すメモリへのポインター。  
  
## 戻り値  
 `HRESULT` 標準値のいずれか 1 つが。  
  
## 解説  
 データ型 **DBORDINAL**、**DBCOLUMNINFO**と **OLECHAR**の詳細については、" *OLE DB Programmer's Reference* の [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)