---
title: "IPersistStreamInitImpl クラス | Microsoft Docs"
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
  - "ATL::IPersistStreamInitImpl"
  - "ATL::IPersistStreamInitImpl<T>"
  - "ATL.IPersistStreamInitImpl<T>"
  - "IPersistStreamInitImpl"
  - "ATL.IPersistStreamInitImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPersistStreamInit ATL の実装"
  - "IPersistStreamInitImpl クラス"
  - "ストリーム, ATL"
ms.assetid: ef217c3c-020f-4cf8-871e-ef68e57865b8
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IPersistStreamInitImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、**IUnknown** を実装し、[IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) インターフェイスの既定の実装を提供します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template<  
class T   
>  
class ATL_NO_VTABLE IPersistStreamInitImpl :  
public IPersistStreamInit  
```  
  
#### パラメーター  
 `T`  
 `IPersistStreamInitImpl`から派生したクラス。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IPersistStreamInitImpl::GetClassID](../Topic/IPersistStreamInitImpl::GetClassID.md)|オブジェクトの CLSID を取得します。|  
|[IPersistStreamInitImpl::GetSizeMax](../Topic/IPersistStreamInitImpl::GetSizeMax.md)|オブジェクトのデータを保存するために必要なストリームのサイズを取得します。  ATL 実装は、**E\_NOTIMPL**を返します。|  
|[IPersistStreamInitImpl::InitNew](../Topic/IPersistStreamInitImpl::InitNew.md)|新しく作成されたオブジェクトを初期化します。|  
|[IPersistStreamInitImpl::IsDirty](../Topic/IPersistStreamInitImpl::IsDirty.md)|最後に保存されてからオブジェクトのデータが変更されたかどうかを確認します。|  
|[IPersistStreamInitImpl::Load](../Topic/IPersistStreamInitImpl::Load.md)|指定したストリームからオブジェクトのプロパティを読み込みます。|  
|[IPersistStreamInitImpl::Save](../Topic/IPersistStreamInitImpl::Save.md)|指定したストリームにオブジェクトのプロパティを保存します。|  
  
## 解説  
 [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) のインターフェイスは、クライアントがオブジェクトが単一のストリームに永続データを読み込み、保存するように要求できるようにします。  クラス `IPersistStreamInitImpl` は、このインターフェイスの既定の実装を提供し、デバッグ ビルドでダンプ デバイスに情報を送信して **IUnknown** を実装します。  
  
 **関連トピック** [ATL チュートリアル](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)、[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## 継承階層  
 `IPersistStreamInit`  
  
 `IPersistStreamInitImpl`  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 参照  
 [Storages and Streams](http://msdn.microsoft.com/library/windows/desktop/aa380352)   
 [クラスの概要](../../atl/atl-class-overview.md)