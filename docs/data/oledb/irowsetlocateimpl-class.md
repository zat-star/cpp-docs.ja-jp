---
title: "IRowsetLocateImpl クラス | Microsoft Docs"
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
  - "IRowsetLocateImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ブックマーク, OLE DB"
  - "IRowsetLocateImpl クラス"
  - "プロバイダー, ブックマーク"
ms.assetid: a8aa3149-7ce8-4976-a680-2da193fd3234
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetLocateImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

行セットの任意の行をフェッチする OLE DB の [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx) インターフェイスを実装します。  
  
## 構文  
  
```  
template <  
   class T,   
   class RowsetInterface,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap < RowClass::KeyType, RowClass* >,   
   class BookmarkKeyType = LONG,   
   class BookmarkType = LONG,   
   class BookmarkMapClass = CAtlMap < RowClass::KeyType, RowClass* >  
>  
class ATL_NO_VTABLE IRowsetLocateImpl : public IRowsetImpl<  
   T,   
   RowsetInterface,   
   RowClass,   
   MapClass  
>  
```  
  
#### パラメーター  
 `T`  
 `IRowsetLocateImpl`から派生したクラスです。  
  
 `RowsetInterface`  
 `IRowsetImpl`から派生したクラスです。  
  
 `RowClass`  
 **HROW**のストレージ ユニット。  
  
 `MapClass`  
 すべての行ハンドルのストレージ ユニットはプロバイダーによって保持される。  
  
 `BookmarkKeyType`  
 LONG や文字列などのブックマークの種類。  通常のブックマークは少なくとも 2 バイト数が必要です。\(バイトの長さは、OLE DB [標準のブックマーク](https://msdn.microsoft.com/en-us/library/ms712954.aspx)**DBBMK\_FIRST**、**DBBMK\_LAST**と **DBBMK\_INVALID**用に予約されます\)。  
  
 `BookmarkType`  
 保持ブックマークにリレーションシップのマッピングの機能。  
  
 `BookmarkMapClass`  
 すべての行ハンドルのストレージ ユニットはブックマークによって保持される。  
  
## メンバー  
  
### インターフェイス メソッド  
  
|||  
|-|-|  
|[Compare](../../data/oledb/irowsetlocateimpl-compare.md)|2 個のブックマークを比較します。|  
|[GetRowsAt](../../data/oledb/irowsetlocateimpl-getrowsat.md)|フェッチはブックマークからのオフセットで指定した行から開始を使用します。|  
|[GetRowsByBookmark](../../data/oledb/irowsetlocateimpl-getrowsbybookmark.md)|指定したブックマークに一致する行をフェッチします。|  
|[ハッシュ](../../data/oledb/irowsetlocateimpl-hash.md)|指定したブックマークのハッシュ値を返します。|  
  
### データ メンバー  
  
|||  
|-|-|  
|[m\_rgBookmarks](../Topic/IRowsetLocateImpl::m_rgBookmarks.md)|ブックマークの配列。|  
  
## 解説  
 `IRowsetLocateImpl` は [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx) インターフェイスの OLE DB テンプレートの実装です。  `IRowsetLocate` が 行セットの任意の行をフェッチするために使用されます。  このインターフェイスを実装しない行セットは `sequential` の行セットです。  `IRowsetLocate` が行セットにと 0 列は行のブックマーク;です この列を読み取ると、同じ行に配置を変更するために使用できるブックマーク値を取得します。  
  
 `IRowsetLocateImpl` が プロバイダーのブックマーク サポートを実装するために使用されます。  ブックマークは、プレースホルダー \(行セットのインデックス\) その行に直ちに制御コンシューマーにデータにすばやくアクセスを許可します。  プロバイダーは、ブックマークが行を識別できるかを判断します。  `IRowsetLocateImpl` のメソッドを使用して、ブックマークを比較し、オフセットによって行をフェッチし、ブックマークに行をフェッチし、ブックマークのハッシュ値を返すことができます。  
  
 行セットの OLE DB のブックマークをサポートするには、このクラスから行セットを継承させます。  
  
 ブックマーク サポートの実装の詳細については、*Visual C\+\+ Programmer's Guide* の [プロバイダーのブックマーク サポート](../../data/oledb/provider-support-for-bookmarks.md) と `Platform``SDK`の *OLE DB Programmer's Reference* の [ブックマーク](https://msdn.microsoft.com/en-us/library/ms709728.aspx) を参照してください。  
  
## 必要条件  
 **ヘッダー**: atldb.h  
  
## 参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [IRowsetLocate:IRowset](https://msdn.microsoft.com/en-us/library/ms721190.aspx)   
 [プロバイダーのブックマーク サポート](../../data/oledb/provider-support-for-bookmarks.md)   
 [Bookmarks](https://msdn.microsoft.com/en-us/library/ms709728.aspx)