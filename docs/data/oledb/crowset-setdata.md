---
title: "CRowset::SetData | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CRowset<TAccessor>.SetData"
  - "SetData"
  - "ATL::CRowset::SetData"
  - "CRowset<TAccessor>.SetData"
  - "CRowset::SetData"
  - "ATL.CRowset.SetData"
  - "CRowset.SetData"
  - "CRowset<TAccessor>::SetData"
  - "ATL::CRowset<TAccessor>::SetData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetData メソッド"
ms.assetid: 68125142-8510-4132-9393-e39efd39c784
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowset::SetData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

行の一つ以上の列にデータ値を設定します。  
  
## 構文  
  
```  
  
      HRESULT SetData( ) const throw( );   
HRESULT SetData(  
   int nAccessor   
) const throw( );  
```  
  
#### パラメーター  
 `nAccessor`  
 \[\]データにアクセスするために使用するアクセサーの数。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 引数を取らない `SetData` のフォームでは、すべてのアクセサーは更新に使用されます。  通常、データ列の値を設定するに **SetData** And をその変更を送信するために [更新](../Topic/CRowset::Update.md) を呼び出します。  
  
 このメソッドは、すべてのプロバイダーでサポートされない省略可能なインターフェイス `IRowsetChange`が必要ですが、; この場合、メソッドの戻り **E\_NOINTERFACE**。  また `VARIANT_TRUE` にテーブルの **開く** を呼び出す前に **DBPROP\_IRowsetChange** を設定または命じなければ、行セットが含まれます。  
  
 一連の操作は、一つ以上の列が書き込み可能でない場合に失敗する場合があります。  これを修正するにはカーソル マップを変更します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CRowset クラス](../Topic/CRowset%20Class.md)   
 [CRowset::Update](../Topic/CRowset::Update.md)