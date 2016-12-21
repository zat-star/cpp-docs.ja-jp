---
title: "CMyProviderSession (MyProviderSess.H) | Microsoft Docs"
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
  - "cmyprovidersession"
  - ""myprovidersess.h""
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMyProviderSession クラス MyProviderSess.H"
  - "OLE DB プロバイダー, ウィザードが生成したファイル"
ms.assetid: d37ad471-cf05-49c5-aa47-cd10824d777f
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMyProviderSession (MyProviderSess.H)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MyProviderSess.H には、OLE DB セッション オブジェクトのための宣言と実装が含まれています。  データ ソース オブジェクトは、セッション オブジェクトを作成し、コンシューマーとプロバイダー間の対話を表します。  セッションは 1 つのデータ ソースに対して同時に複数開くことができます。  次のコードは、`CMyProviderSession` の継承リストです。  
  
```  
/////////////////////////////////////////////////////////////////////////  
// CMyProviderSession  
class ATL_NO_VTABLE CMyProviderSession :   
   public CComObjectRootEx<CComSingleThreadModel>,  
   public IGetDataSourceImpl<CMyProviderSession>,  
   public IOpenRowsetImpl<CMyProviderSession>,  
   public ISessionPropertiesImpl<CMyProviderSession>,  
   public IObjectWithSiteSessionImpl<CMyProviderSession>,  
   public IDBSchemaRowsetImpl<CMyProviderSession>,  
   public IDBCreateCommandImpl<CMyProviderSession, CMyProviderCommand>  
```  
  
 セッション オブジェクトは、**IGetDataSource**、`IOpenRowset`、**ISessionProperties**、および **IDBCreateCommand** から継承されます。  **IGetDataSource** インターフェイスによって、セッションはそのセッションを作成するデータ ソースを取得できるようになります。  これは、作成したデータ ソースからプロパティを取得したり、そのデータ ソースが提供できるその他の情報を取得したりする必要があるときに利用できます。  **ISessionProperties** インターフェイスは、そのセッションで使用されるすべてのプロパティを処理します。  `IOpenRowset` インターフェイスと **IDBCreateCommand** インターフェイスは、データベース操作を行うためのインターフェイスです。  プロバイダーがコマンドをサポートする場合、そのプロバイダーは **IDBCreateCommand** インターフェイスを実装します。  このインターフェイスを使用すると、コマンドを実行できるコマンド オブジェクトを作成できます。  `IOpenRowset` オブジェクトは常にプロバイダーによって実装されます。  IOpenRowset オブジェクトは、プロバイダーから単一の行セットを生成するために使用されます。  これは、プロバイダーからの既定の行セット \(`"select * from mytable"` など\) になります。  
  
 ウィザードは、`CMyProviderSessionColSchema`、`CMyProviderSessionPTSchema`、および `CMyProviderSessionTRSchema` の 3 つのセッション クラスも生成します。  これらのセッションは、スキーマ行セットに使用されます。  スキーマ行セットを使用して、プロバイダーは、コンシューマーにデータのクエリやフェッチを実行させずに、コンシューマーにメタデータを返すことができます。  メタデータのフェッチは、プロバイダー機能を検出するよりもはるかに高速に実行できます。  
  
 OLE DB 仕様では、**IDBSchemaRowset** インターフェイスを実装するプロバイダーが、**DBSCHEMA\_COLUMNS**、**DBSCHEMA\_PROVIDER\_TYPES**、および `DBSCHEMA_TABLES` の 3 種類のスキーマ行セットをサポートする必要があります。  ウィザードは、各スキーマ行セットの実装を生成します。  ウィザードにより生成された各クラスには、`Execute` メソッドが含まれます。  この `Execute` メソッドでは、サポートするテーブル、列、データ型などのデータをプロバイダーに返すことができます。  このデータは、通常はコンパイル時に明らかになっています。  
  
## 参照  
 [プロバイダー ウィザードで生成されたファイル](../../data/oledb/provider-wizard-generated-files.md)