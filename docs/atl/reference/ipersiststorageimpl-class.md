---
title: "IPersistStorageImpl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::IPersistStorageImpl"
  - "ATL::IPersistStorageImpl<T>"
  - "ATL.IPersistStorageImpl<T>"
  - "IPersistStorageImpl"
  - "ATL.IPersistStorageImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPersistStorageImpl クラス"
  - "ストレージ, ATL"
ms.assetid: d652f02c-239c-47c7-9a50-3e9fc3014fff
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IPersistStorageImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、[IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) インターフェイスを実装します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template <  
class T  
>  
class ATL_NO_VTABLE IPersistStorageImpl :  
public IPersistStorage  
```  
  
#### パラメーター  
 `T`  
 `IPersistStorageImpl`から派生したクラス。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IPersistStorageImpl::GetClassID](../Topic/IPersistStorageImpl::GetClassID.md)|オブジェクトの CLSID を取得します。|  
|[IPersistStorageImpl::HandsOffStorage](../Topic/IPersistStorageImpl::HandsOffStorage.md)|オブジェクトにすべてのストレージ オブジェクトを解放し、HandsOff モードに変更します。  ATL 実装は、`S_OK`を返します。|  
|[IPersistStorageImpl::InitNew](../Topic/IPersistStorageImpl::InitNew.md)|新しいストレージを初期化します。|  
|[IPersistStorageImpl::IsDirty](../Topic/IPersistStorageImpl::IsDirty.md)|最後に保存されてからオブジェクトのデータが変更されたかどうかを確認します。|  
|[IPersistStorageImpl::Load](../Topic/IPersistStorageImpl::Load.md)|指定されたストレージからオブジェクトのプロパティを読み込みます。|  
|[IPersistStorageImpl::Save](../Topic/IPersistStorageImpl::Save.md)|指定されたストレージにオブジェクトのプロパティを保存します。|  
|[IPersistStorageImpl::SaveCompleted](../Topic/IPersistStorageImpl::SaveCompleted.md)|ストレージ オブジェクトに書き込み、通常モードに戻ることができるオブジェクトに通知します。  ATL 実装は、`S_OK`を返します。|  
  
## 解説  
 `IPersistStorageImpl` は、クライアントがオブジェクトの読み込み要求し、ストレージを使用して永続データを保存 [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) のインターフェイスを実装します。  
  
 このクラスの実装は、クラス `T` が `QueryInterface`によって `IPersistStreamInit` のインターフェイスの実装を用意する必要があります。  通常、これはクラス `T` が [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)から派生し、[COM マップします。](../Topic/BEGIN_COM_MAP.md)の `IPersistStreamInit` を紹介し、クラスの永続データを記述するために [プロパティ マップ](../Topic/BEGIN_PROP_MAP.md) を使用する必要があることを意味します。  
  
 **関連トピック** [ATL チュートリアル](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)、[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## 継承階層  
 `IPersistStorage`  
  
 `IPersistStorageImpl`  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 参照  
 [Storages and Streams](http://msdn.microsoft.com/library/windows/desktop/aa380352)   
 [IPersistStreamInitImpl クラス](../../atl/reference/ipersiststreaminitimpl-class.md)   
 [IPersistPropertyBagImpl クラス](../../atl/reference/ipersistpropertybagimpl-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)