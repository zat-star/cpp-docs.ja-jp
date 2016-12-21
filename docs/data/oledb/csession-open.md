---
title: "CSession::Open | Microsoft Docs"
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
  - "ATL::CSession::Open"
  - "CSession::Open"
  - "CSession.Open"
  - "ATL.CSession.Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open メソッド"
ms.assetid: c2050c2c-9817-4857-be49-189f346968f6
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSession::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

データ ソース オブジェクトの新しいセッションが開きます。  
  
## 構文  
  
```  
  
      HRESULT Open(  
   const CDataSource& ds,  
   DBPROPSET *pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw( );  
```  
  
#### パラメーター  
 `ds`  
 \[\]セッション データ ソースが開きます。  
  
 *pPropSet*  
 \[\]設定するプロパティと値を含む [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 構造体の配列へのポインター。  [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の *OLE DB Programmer's Reference* の [プロパティ セットとプロパティ グループ](https://msdn.microsoft.com/en-us/library/ms713696.aspx) を参照してください。  
  
 `ulPropSets`  
 \[\] *pPropSet の* 引数に渡される [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 構造体の数。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 [CDataSource::Open](../../data/oledb/cdatasource-open.md) を使用して `CSession::Open`に渡す前にデータ ソース オブジェクトを開く必要があります。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CSession クラス](../../data/oledb/csession-class.md)