---
title: "IRowsetNotifyCP クラス | Microsoft Docs"
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
  - "IRowsetNotifyCP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetNotifyCP クラス"
ms.assetid: ccef402b-94a0-4c2e-9a13-7e854ef82390
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetNotifyCP クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コネクション ポイント インターフェイス [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx)のプロバイダー サイトを実装します。  
  
## 構文  
  
```  
template <  
   class T,   
   class ReentrantEventSync = CComSharedMutex   
>  
class IRowsetNotifyCP :   
   public IConnectionPointImpl<  
      T,   
      piid = &__uuidof(IRowsetNotify),   
      CComDynamicUnkArray DynamicUnkArray  
   >,  
   public ReentrantEventSync  
```  
  
#### パラメーター  
 `T`  
 `IRowsetNotifyCP`から派生したクラスです。  
  
 `ReentrantEventSync`  
 再入 \(既定サポートするミューテックス クラスは **CComSharedMutex**です\)。  ミューテックスは、同期オブジェクトとしてリソースに 1 スレッド同時に指定できないアクセスです。  
  
 `piid`  
 **IRowsetNotify** のコネクション ポイント インターフェイスのインターフェイス ID ポインター \(**IID\***\)。  既定値は **&\_\_uuidof\(IRowsetNotify\)**です。  
  
 `DynamicUnkArray`  
 クライアント シンク インターフェイスへのポインター **IUnknown** の動的に割り当てられた配列である型 [CComDynamicUnkArray](../Topic/CComDynamicUnkArray%20Class.md)の配列。  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[Fire\_OnFieldChange](../../data/oledb/irowsetnotifycp-fire-onfieldchange.md)|列の値を変更しているときにコンシューマーに通知します。|  
|[Fire\_OnRowChange](../../data/oledb/irowsetnotifycp-fire-onrowchange.md)|行に影響を与える変更にコンシューマーに通知します。|  
|[Fire\_OnRowsetChange](../../data/oledb/irowsetnotifycp-fire-onrowsetchange.md)|行全体の設定に影響を与える変更にコンシューマーに通知します。|  
  
## 解説  
 `IRowsetNotifyCP` はブロードキャスト関数を実装して、コネクション ポイント **IID\_IRowsetNotify** 上のリスナーに対し、行セットの内容変更をアドバイズします。  
  
 コンシューマーに通知を処理できるように、[IRowsetNotifyImpl](../Topic/IRowsetNotifyImpl%20Class.md) を使用してコンシューマー \(別名「シンク」\) `IRowsetNotify` を実装し、登録する必要があります。  コンシューマーのコネクション ポイント インターフェイスの実装に関する [通知の受信](../../data/oledb/receiving-notifications.md) を参照してください。  
  
 通知の実装の詳細については、「 [更新可能なプロバイダーの作成](../../data/oledb/creating-an-updatable-provider.md)のサポートの通知」を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Notifications \(COM\)](http://msdn.microsoft.com/library/windows/desktop/ms678433)   
 [Overview of Notifications \(OLE DB\)](https://msdn.microsoft.com/en-us/library/ms725406.aspx)   
 [BEGIN\_CONNECTION\_POINT\_MAP](../Topic/BEGIN_CONNECTION_POINT_MAP.md)   
 [END\_CONNECTION\_POINT\_MAP](../Topic/END_CONNECTION_POINT_MAP.md)   
 [CONNECTION\_POINT\_ENTRY](../Topic/CONNECTION_POINT_ENTRY.md)   
 [更新可能なプロバイダーの作成](../../data/oledb/creating-an-updatable-provider.md)