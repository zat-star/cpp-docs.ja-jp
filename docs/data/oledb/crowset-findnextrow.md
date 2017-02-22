---
title: "CRowset::FindNextRow | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CRowset.FindNextRow"
  - "CRowset<TAccessor>.FindNextRow"
  - "ATL::CRowset::FindNextRow"
  - "CRowset::FindNextRow"
  - "CRowset<TAccessor>::FindNextRow"
  - "CRowset.FindNextRow"
  - "ATL.CRowset<TAccessor>.FindNextRow"
  - "ATL::CRowset<TAccessor>::FindNextRow"
  - "FindNextRow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FindNextRow メソッド"
ms.assetid: 36484df9-3625-4f15-bf69-db73a8d91c55
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CRowset::FindNextRow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定したブックマークの後に次の一致する行を検索します。  
  
## 構文  
  
```  
  
      HRESULT FindNextRow(   
   DBCOMPAREOP op,   
   BYTE* pData,   
   DBTYPE wType,   
   DBLENGTH nLength,   
   BYTE bPrecision,   
   BYTE bScale,   
   BOOL bSkipCurrent = TRUE,   
   CBookmarkBase* pBookmark = NULL    
) throw( );  
```  
  
#### パラメーター  
 `op`  
 \[\]行の値の比較に使用するアクション。  値については、[IRowsetFind::FindNextRow](https://msdn.microsoft.com/en-us/library/ms723091.aspx)を参照してください。  
  
 `pData`  
 \[\]一致する値へのポインター。  
  
 `wType`  
 \[\]バッファーの値の一部のデータ型を示します。  型インジケーターの詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の *OLE DB Programmer's Reference* の [データ型](https://msdn.microsoft.com/en-us/library/ms723969.aspx) を参照してください。  
  
 `nLength`  
 \[\]期間、データ値に対して割り当てられたコンシューマーのデータ構造体のサイズ \(バイト単位\)。  詳細については、*OLE DB Programmer's Reference*の [DBBINDING 構造体](https://msdn.microsoft.com/en-us/library/ms716845.aspx) の **cbMaxLen** の説明を参照してください。  
  
 `bPrecision`  
 \[\]データを取得するときに使用する最大の精度。  `wType` が `DBTYPE_NUMERIC`の場合にのみ使用されます。  詳細については、*OLE DB Programmer's Reference*の [DBTYPE\_NUMERIC または DBTYPE\_DECIMAL を伴う変換](https://msdn.microsoft.com/en-us/library/ms719714.aspx) を参照します。  
  
 `bScale`  
 \[\]データを取得するときに使用します。  `wType` が `DBTYPE_NUMERIC` または **DBTYPE\_DECIMAL**の場合にのみ使用されます。  詳細については、*OLE DB Programmer's Reference*の [DBTYPE\_NUMERIC または DBTYPE\_DECIMAL を伴う変換](https://msdn.microsoft.com/en-us/library/ms719714.aspx) を参照します。  
  
 *bSkipCurrent*  
 \[\]検索を開始するブックマークの行数。  
  
 `pBookmark`  
 \[\]検索を開始する位置のブックマークを設定します。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 このメソッドは、すべてのプロバイダーでサポートされない省略可能なインターフェイス **IRowsetFind**が必要ですが、; この場合、メソッドの戻り **E\_NOINTERFACE**。  また `VARIANT_TRUE` にテーブルの **開く** を呼び出す前に **DBPROP\_IRowsetFind** を設定または命じなければ、行セットが含まれます。  
  
 使用方法の詳細については、コンシューマーで、[ブックマークを使用する](../../data/oledb/using-bookmarks.md)ブックマークを参照します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CRowset クラス](../Topic/CRowset%20Class.md)   
 [DBBINDING Structures](https://msdn.microsoft.com/en-us/library/ms716845.aspx)