---
title: "IRowsetChangeImpl クラス | Microsoft Docs"
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
  - "ATL::IRowsetChangeImpl"
  - "IRowsetChangeImpl"
  - "ATL.IRowsetChangeImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetChangeImpl クラス"
  - "プロバイダー, 更新可能な"
  - "更新可能なプロバイダー, 直前の更新"
ms.assetid: 1e9fee15-ed9e-4387-af8f-215569beca6c
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetChangeImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB 仕様の [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) インターフェイスの OLE DB テンプレートの実装。  
  
## 構文  
  
```  
template <  
   class T,   
   class Storage,   
   class BaseInterface = IRowsetChange,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap < RowClass::KeyType, RowClass* >   
>  
class ATL_NO_VTABLE IRowsetChangeImpl : public BaseInterface  
```  
  
#### パラメーター  
 `T`  
 `IRowsetChangeImpl`から派生したクラスです。  
  
 `Storage`  
 ユーザー レコード。  
  
 `BaseInterface`  
 `IRowsetChange`などのインターフェイスの基本クラス。  
  
 `RowClass`  
 行ハンドルのストレージ ユニット。  
  
 `MapClass`  
 すべての行ハンドルのストレージ ユニットはプロバイダーによって保持される。  
  
## メンバー  
  
### インターフェイス メソッド \(IRowsetChange で使用される\)  
  
|||  
|-|-|  
|[DeleteRows](../Topic/IRowsetChangeImpl::DeleteRows.md)|行セットからの行の削除。|  
|[InsertRow](../../data/oledb/irowsetchangeimpl-insertrow.md)|行セットの行を挿入します。|  
|[SetData](../Topic/IRowsetChangeImpl::SetData.md)|一つ以上の列にデータ値を設定します。|  
  
### 実装のメソッド \(コールバック\)  
  
|||  
|-|-|  
|[FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md)|データ ストアにコミットをプロバイダーによって Overidden。|  
  
## 解説  
 このインターフェイスは、データ ストアの直接の書き込み操作を行います。「エンド ユーザー \(コンシューマーを使ったユーザー\) に変更を加えると、その変更はデータ ストアにすぐに送信することを」、意味します \(および取り消しできません\)。  
  
 `IRowsetChangeImpl` は 既存の行内の列の値を更新し、行を削除し、新しい行の挿入を有効にする `IRowsetChange` の OLE DB インターフェイスを実装します。  
  
 OLE DB テンプレートの実装はすべての基本メソッド \(`SetData`、`InsertRow`と `DeleteRows`\) をサポートします。  
  
> [!IMPORTANT]
>  プロバイダーを実装するように前に次のドキュメントを読み込むことを強くお勧めします:  
  
-   [更新可能なプロバイダーの作成](../../data/oledb/creating-an-updatable-provider.md)  
  
-   *OLE DB Programmer's Reference*の第 6 章  
  
-   また `RUpdateRowset` クラスは UpdatePV サンプルでどのように使用されるかを参照してください。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)