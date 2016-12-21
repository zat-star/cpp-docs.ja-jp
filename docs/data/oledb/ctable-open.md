---
title: "CTable::Open | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CTable.Open"
  - "ATL::CTable::Open"
  - "CTable::Open"
  - "CTable.Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open メソッド"
ms.assetid: 5d006d95-74d7-4e2b-b243-a33bc53b5455
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTable::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

テーブルを開きます。  
  
## 構文  
  
```  
  
      HRESULT Open(  
   const CSession& session,  
   LPCWSTR wszTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw ( );  
HRESULT Open(  
   const CSession& session,  
   LPCSTR szTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw ( );  
HRESULT Open(  
   const CSession& session,  
   DBID& dbid,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw ( );  
```  
  
#### パラメーター  
 `session`  
 \[\]テーブルを開くセッション。  
  
 *wszTableName*  
 \[\] Unicode 文字列として渡す開こうとするテーブルの名前。  
  
 *szTableName*  
 \[\] ANSI 文字列として渡す開こうとするテーブルの名前。  
  
 *dbid*  
 \[\]開こうとするテーブルの **DBID**。  
  
 *pPropSet*  
 \[\]設定するプロパティと値を含む [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 構造体の配列へのポインター。  [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の *OLE DB Programmer's Reference* の [プロパティ セットとプロパティ グループ](https://msdn.microsoft.com/en-us/library/ms713696.aspx) を参照してください。  空白の既定値はプロパティが指定されていません。  
  
 `ulPropSets`  
 \[\] *pPropSet の* 引数に渡される [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 構造体の数。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 詳細については、*OLE DB Programmer's Reference*の [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CTable クラス](../../data/oledb/ctable-class.md)