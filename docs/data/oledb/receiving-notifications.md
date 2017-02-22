---
title: "通知の受信 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "イベント [C++], 通知 (OLE DB での)"
  - "通知 [C++], イベント"
  - "通知 [C++], OLE DB コンシューマー"
  - "OLE DB コンシューマー, 通知"
  - "OLE DB プロバイダー, 通知"
  - "受信 (OLE DB で通知を)"
  - "行セット, イベント通知"
ms.assetid: 305a1103-0c87-40c8-94bc-7fbbdd52ae32
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 通知の受信
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB では、イベント発生時に通知を受信するためのインターフェイスを用意しています。  これらのインターフェイスについては、『OLE DB Programmer's Reference』の「[Chapter 12: OLE DB Object Notifications](https://msdn.microsoft.com/en-us/library/ms725406.aspx)」を参照してください。  これらのイベントのセットアップでは、標準の COM コネクション ポイント機構を使用します。  たとえば、`IRowsetNotify` を通じてイベントを取得する ATL オブジェクトは、クラスから派生した一覧に `IRowsetNotify` を追加し、これを **COM\_INTERFACE\_ENTRY** マクロを通じて公開することで、`IRowsetNotify` インターフェイスを実装します。  
  
 `IRowsetNotify` には、さまざまな時点で呼び出すことができる 3 つのメソッドがあります。  これらのメソッドの 1 つに対してだけ応答する場合は、[IRowsetNotifyImpl](../Topic/IRowsetNotifyImpl%20Class.md) クラスを使用します。このクラスは、関係のないメソッドに対しては **E\_NOTIMPL** を返します。  
  
 行セットを作成するときは、返された行セット オブジェクトで **IConnectionPointContainer** をサポートすることをプロバイダーに通知する必要があります。これは通知のセットアップに必要です。  
  
 ATL オブジェクトから行セットを開き、`AtlAdvise` 関数を使用して通知シンクをセットアップする方法を次のコード例に示します。  `AtlAdvise` は、`AtlUnadvise` を呼び出したときに使用されるクッキーを返します。  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  
propset.AddProperty(DBPROP_IConnectionPointContainer, true);  
  
product.Open(session, _T("Products"), &propset);  
  
AtlAdvise(product.m_spRowset, GetUnknown(), IID_IRowsetNotify, &m_dwCookie);  
```  
  
## 参照  
 [アクセサーの使用](../../data/oledb/using-accessors.md)