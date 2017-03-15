---
title: "通知のサポート | Microsoft Docs"
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
  - "通知 [C++], OLE DB コンシューマー"
  - "OLE DB コンシューマー, 通知"
  - "OLE DB プロバイダー テンプレート, 通知"
  - "OLE DB プロバイダー, 通知"
  - "行セット, イベント通知"
ms.assetid: 76e875fd-2bfd-4e4e-9f43-dbe5a3fa7382
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 通知のサポート
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## プロバイダーとコンシューマーでのコネクション ポイント インターフェイスの実装  
 通知を実装するには、プロバイダー クラスが [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md) と [IConnectionPointContainer](../Topic/IConnectionPointContainerImpl%20Class.md) を継承する必要があります。  
  
 `IRowsetNotifyCP` は、[IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx)コネクション ポイント インターフェイスのプロバイダー サイトを実装します。  `IRowsetNotifyCP` はブロードキャスト関数を実装して、コネクション ポイント **IID\_IRowsetNotify** 上のリスナーに対し、行セットの内容変更をアドバイズします。  
  
 また、[IRowsetNotifyImpl](../Topic/IRowsetNotifyImpl%20Class.md) を使用して、シンクとも呼ばれるコンシューマーで `IRowsetNotify` を実装および登録し、コンシューマーで通知を処理できるようにします。  コンシューマー側のコネクション ポイント インターフェイスの実装については、「[通知の受信](../../data/oledb/receiving-notifications.md)」を参照してください。  
  
 また、クラスには、次のようにコネクション ポイント エントリを定義するマップも含める必要があります。  
  
```  
BEGIN_CONNECTION_POINT_MAP  
   CONNECTIONPOINT_ENTRY (IID_IRowsetNotify)  
END_CONNECTION_POINT_MAP  
```  
  
## IRowsetNotify の追加  
 `IRowsetNotify` を追加するには、`IConnectionPointContainerImpl<rowset-name>` と `IRowsetNotifyCP<rowset-name>` を継承チェーンに追加する必要があります。  
  
 [UpdatePV](http://msdn.microsoft.com/ja-jp/c8bed873-223c-4a7d-af55-f90138c6f38f) 内の `RUpdateRowset` の継承チェインの例を次に示します。  
  
> [!NOTE]
>  サンプル コードは、ここに記載されているコードと異なる場合がありますが、その場合はサンプル コードの方が最新バージョンであると考えてください。  
  
```  
///////////////////////////////////////////////////////////////////////////  
// class RUpdateRowset (in rowset.h)  
  
class RUpdateRowset :   
public CRowsetImpl< RUpdateRowset, CAgentMan, CUpdateCommand,   
         CAtlArray< CAgentMan, CAtlArray<CAgentMan> >, CSimpleRow,   
         IRowsetScrollImpl< RUpdateRowset, IRowsetScroll > >,  
      public IRowsetUpdateImpl< RUpdateRowset, CAgentMan >,  
      public IConnectionPointContainerImpl<RUpdateRowset>,  
      public IRowsetNotifyCP<RUpdateRowset>  
```  
  
### COM マップ エントリの設定  
 次のエントリを行セットの COM マップに追加する必要もあります。  
  
```  
COM_INTERFACE_ENTRY(IConnectionPointContainer)  
COM_INTERFACE_ENTRY_IMPL(IConnectionPointContainer)  
```  
  
 これらのマクロにより、コネクション ポイント コンテナー \(`IRowsetNotify` の実装側\) に対する `QueryInterface` の任意の呼び出し側が、プロバイダー上の要求されたインターフェイスを検索できるようになります。  コネクション ポイントの使用例については、ATL POLYGON サンプルとチュートリアルを参照してください。  
  
### コネクション ポイント マップのエントリの設定  
 コネクション ポイント マップも追加する必要があります。  たとえば、次のようになります。  
  
```  
BEGIN_CONNECTION_POINT_MAP(rowset-name)  
     CONNECTION_POINT_ENTRY(_uuidof(IRowsetNotify))  
END_CONNECTION_POINT_MAP()  
```  
  
 このコネクション ポイント マップにより、`IRowsetNotify` インターフェイスを検索するコンポーネントが、プロバイダーでこのインターフェイスを見つけることができるようになります。  
  
### プロパティの設定  
 また、以下のプロパティをプロバイダーに追加する必要もあります。  サポートするインターフェイスに基づいたプロパティだけを追加します。  
  
|プロパティ|サポートする内容|  
|-----------|--------------|  
|**DBPROP\_IConnectionPointContainer**|常時|  
|**DBPROP\_NOTIFICATIONGRANULARITY**|常時|  
|**DBPROP\_NOTIFICATIONPHASES**|常時|  
|**DBPROP\_NOTIFYCOLUMNSET**|`IRowsetChange`|  
|**DBPROP\_NOTIFYROWDELETE**|`IRowsetChange`|  
|**DBPROP\_NOTIFYROWINSERT**|`IRowsetChange`|  
|**DBPROP\_NOTIFYROWSETFETCHPOSITIONCHANGE**|常時|  
|**DBPROP\_NOTIFYROWFIRSTCHANGE**|`IRowsetUpdate`|  
|**DBPROP\_NOTIFYROWSETRELEASE**|常時|  
|**DBPROP\_NOTIFYROWUNDOCHANGE**|`IRowsetUpdate`|  
|**DBPROP\_NOTIFYROWUNDODELETE**|`IRowsetUpdate`|  
|**DBPROP\_NOTIFYROWUNDOINSERT**|`IRowsetUpdate`|  
|**DBPROP\_NOTIFYROWUPDATE**|`IRowsetUpdate`|  
  
 通知の実装の大部分は、OLE DB プロバイダー テンプレートに埋め込まれています。  `IRowsetNotifyCP` を継承チェーンに追加しない場合は、Visual C\+\+ .NET のコンパイラ機能により、コンパイルのストリームからそのコードがすべて削除されるため、コード サイズが小さくなります。  
  
## 参照  
 [高度なプロバイダー手法](../Topic/Advanced%20Provider%20Techniques.md)