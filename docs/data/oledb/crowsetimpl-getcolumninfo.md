---
title: "CRowsetImpl::GetColumnInfo | Microsoft Docs"
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
  - "CRowsetImpl.GetColumnInfo"
  - "CRowsetImpl::GetColumnInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetColumnInfo メソッド"
ms.assetid: 9ef76525-f996-4c6f-81b9-68eb260350ef
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# CRowsetImpl::GetColumnInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

特定のクライアント要求の列情報を取得します。  
  
## 構文  
  
```  
  
      static ATLCOLUMNINFO* CRowsetBaseImpl::GetColumnInfo(  
   T* pv,  
   ULONG* pcCols   
);  
```  
  
#### パラメーター  
 `pv`  
 \[\]ユーザーの `CRowsetImpl` の派生クラスへのポインター。  
  
 `pcCols`  
 \[\]列数へのポインター。出力\) が返されました。  
  
## 戻り値  
 **ATLCOLUMNINFO** の静的な構造体へのポインター。  
  
## 解説  
 このメソッドは高度なオーバーライドです。  
  
 このメソッドは基本クラスによって実装されたクライアント要求の列情報を取得するために呼び出されます。  通常、このメソッドは `IColumnsInfoImpl`によって呼び出されます。  このメソッドをオーバーライドする場合は、`CRowsetImpl`に\-派生クラス メソッドのバージョンを配置する必要があります。  メソッドが非テンプレート化されますクラスに配置される可能性があるため、適切な `CRowsetImpl`に\-派生クラス `pv` を変更する必要があります。  
  
 次の例では **GetColumnInfo's** の使い方を示しています。  この例では、**CMyRowset** は `CRowsetImpl`\-派生クラスです。  このクラスのすべてのインスタンスの `GetColumnInfo` をオーバーライドするには、**CMyRowset** クラス定義内に次のメソッドを追加する:  
  
 [!CODE [NVC_OLEDB_Provider#1](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Provider#1)]  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [CRowsetImpl クラス](../../data/oledb/crowsetimpl-class.md)