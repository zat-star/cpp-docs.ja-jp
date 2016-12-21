---
title: "CRowsetImpl::NameFromDBID | Microsoft Docs"
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
  - "CRowsetImpl.NameFromDBID"
  - "CRowsetImpl::NameFromDBID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NameFromDBID メソッド"
ms.assetid: 6aa5b074-90c7-4434-adfd-c64c13e76c78
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowsetImpl::NameFromDBID
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

渡された `bstr` に **DBID** とコピーから文字列を格納します。  
  
## 構文  
  
```  
  
      HRESULT CRowsetBaseImpl::NameFromDBID(  
   DBID* pDBID,  
   CComBSTR& bstr,  
   bool bIndex   
);  
```  
  
#### パラメーター  
 *pDBID*  
 \[\]文字列を取得 **DBID** へのポインター。  
  
 `bstr`  
 \[\] **DBID** の文字列のコピーを配置 [CComBSTR](../../atl/reference/ccombstr-class.md) A の参照。  
  
 `bIndex`  
 \[\] **true** インデックス **DBID**; **false** テーブル **DBID**。  
  
## 戻り値  
 標準の `HRESULT` を返します。  によって **DBID** がテーブルの場合、またはインデックスかどうか \(`bIndex`で表示される\)、メソッドは **DB\_E\_NOINDEX** または **DB\_E\_NOTABLE**を返します。  
  
## 解説  
 このメソッドは [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) と [GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md)の `CRowsetImpl` の実装によって呼び出されます。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [CRowsetImpl クラス](../../data/oledb/crowsetimpl-class.md)