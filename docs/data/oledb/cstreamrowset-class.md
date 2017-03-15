---
title: "CStreamRowset クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CStreamRowset<TAccessor>"
  - "ATL::CStreamRowset"
  - "CStreamRowset"
  - "ATL.CStreamRowset<TAccessor>"
  - "ATL.CStreamRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStreamRowset クラス"
ms.assetid: a106e953-a38a-464e-8ea5-28963d9e4811
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# CStreamRowset クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CCommand` または `CTable` の宣言で使用します。  
  
## 構文  
  
```  
template <class TAccessor = CAccessorBase>  
class CStreamRowset  
```  
  
#### パラメーター  
 `TAccessor`  
 アクセサー クラス。  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[CStreamRowset](../../data/oledb/cstreamrowset-cstreamrowset.md)|コンストラクターです。  `CStreamRowset` オブジェクトをインスタンス化し、初期化します。|  
|[&#91;閉じる&#93;](../../data/oledb/cstreamrowset-close.md)|クラスの [ISequentialStream](https://msdn.microsoft.com/en-us/library/ms718035.aspx) インターフェイス ポインターを解放します。|  
  
## 解説  
 `CCommand` または `CTable` の宣言で `CStreamRowset` を使用します \(例:  
  
 [!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/CPP/cstreamrowset-class_1.cpp)]  
  
 または  
  
 [!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/CPP/cstreamrowset-class_2.cpp)]  
  
 `ICommand::Execute` は `m_spStream`に格納されている `ISequentialStream` のポインターを返します。  その後、XML 形式のデータ \(Unicode 文字列\) を取得するために **読み取り** のメソッドを使用します。  たとえば、次のようになります。  
  
 [!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/CPP/cstreamrowset-class_3.cpp)]  
  
 SQL Server 2000 は XML 書式設定を実行し、行セットのすべての列と行をすべてように、1 種類の XML 文字列として返します。  
  
> [!NOTE]
>  この機能は、SQL Server 2000 だけを使用しています。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)