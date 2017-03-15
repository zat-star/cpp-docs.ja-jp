---
title: "IDBSchemaRowsetImpl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDBSchemaRowsetImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDBSchemaRowsetImpl クラス"
ms.assetid: bd7bf0d7-a1c6-4afa-88e3-cfdbdf560703
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IDBSchemaRowsetImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

スキーマ行セットの実装を提供します。  
  
## 構文  
  
```  
template <class SessionClass>  
class ATL_NO_VTABLE IDBSchemaRowsetImpl : public IDBSchemaRowset  
```  
  
#### パラメーター  
 `SessionClass`  
 `IDBSchemaRowsetImpl` が継承されるクラス。 通常、このクラスは、ユーザーのセッション クラスです。  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[CheckRestrictions](../../data/oledb/idbschemarowsetimpl-checkrestrictions.md)|スキーマ行セットに対して制限の妥当性をチェックします。|  
|[CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md)|テンプレート パラメーターで指定されたオブジェクトの COM オブジェクトの作成関数を実装します。|  
|[SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md)|特定のスキーマ行セットでサポートする制限を指定します。|  
  
### インターフェイス メソッド  
  
|||  
|-|-|  
|[GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)|スキーマ行セットを返します。|  
|[GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md)|[IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) でアクセスできるスキーマ行セットの一覧を返します。|  
  
## 解説  
 このクラスは、[IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) インターフェイスと、テンプレート化された作成関数 [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md) を実装します。  
  
 OLE DB はスキーマ行セットを使用して、プロバイダーのデータに関するデータを返します。 このようなデータは、多くの場合、"メタデータ" と呼ばれます。*OLE DB プログラマーズ リファレンス*の「[IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx)」で説明されているように、既定では、プロバイダーは常に `DBSCHEMA_TABLES`、**DBSCHEMA\_COLUMNS**、および **DBSCHEMA\_PROVIDER\_TYPES** をサポートする必要があります。 スキーマ行セットはスキーマ マップで指定します。 スキーマ マップ エントリの詳細については、「[SCHEMA\_ENTRY](../../data/oledb/schema-entry.md)」を参照してください。  
  
 ATL オブジェクト ウィザードの OLE DB プロバイダー ウィザードでは、プロジェクトのスキーマ行セットのコードが自動的に生成されます  \(既定では、ウィザードは、以前説明した必須のスキーマ行セットをサポートしています\)。 ATL オブジェクト ウィザードでコンシューマーを作成すると、スキーマ行セットで正しいデータがプロバイダーにバインドされます。 正しいメタデータを提供するようにスキーマ行セットを実装していないと、正しいデータがバインドされません。  
  
 プロバイダーでスキーマ行セットをサポートする方法については、「[スキーマ行セットのサポート](../../data/oledb/supporting-schema-rowsets.md)」を参照してください。  
  
 スキーマ行セットの詳細については、*OLE DB プログラマーズ リファレンス*の[スキーマ行セット](https://msdn.microsoft.com/en-us/library/ms712921.aspx)に関するセクションを参照してください。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [IDBSchemaRowsetImpl Class Members](http://msdn.microsoft.com/ja-jp/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [スキーマ行セット クラスと Typedef クラス](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md)   
 [スキーマ行セットのサポート](../../data/oledb/supporting-schema-rowsets.md)