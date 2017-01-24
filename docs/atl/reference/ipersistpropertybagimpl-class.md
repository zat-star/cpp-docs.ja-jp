---
title: "IPersistPropertyBagImpl クラス | Microsoft Docs"
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
  - "IPersistPropertyBagImpl"
  - "ATL.IPersistPropertyBagImpl<T>"
  - "ATL::IPersistPropertyBagImpl"
  - "ATL::IPersistPropertyBagImpl<T>"
  - "ATL.IPersistPropertyBagImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPersistPropertyBagImpl クラス"
ms.assetid: 712af24d-99f8-40f2-9811-53b3ff6e5b19
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IPersistPropertyBagImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは **IUnknown** を実装します。オブジェクトは、そのプロパティをクライアントが提供するプロパティ バッグに保存できます。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template <   
class T   
>  
class ATL_NO_VTABLE IPersistPropertyBagImpl :  
public IPersistPropertyBag  
```  
  
#### パラメーター  
 `T`  
 `IPersistPropertyBagImpl`から派生したクラス。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IPersistPropertyBagImpl::GetClassID](../Topic/IPersistPropertyBagImpl::GetClassID.md)|オブジェクトの CLSID を取得します。|  
|[IPersistPropertyBagImpl::InitNew](../Topic/IPersistPropertyBagImpl::InitNew.md)|新しく作成されたオブジェクトを初期化します。  ATL 実装は、`S_OK`を返します。|  
|[IPersistPropertyBagImpl::Load](../Topic/IPersistPropertyBagImpl::Load.md)|クライアントが提供するプロパティ バッグからオブジェクトのプロパティを読み込みます。|  
|[IPersistPropertyBagImpl::Save](../Topic/IPersistPropertyBagImpl::Save.md)|クライアントが提供するプロパティ バッグにオブジェクトのプロパティを保存します。|  
  
## 解説  
 [IPersistPropertyBag](https://msdn.microsoft.com/en-us/library/aa768205.aspx) のインターフェイスは、オブジェクトがクライアントが提供するプロパティ バッグにプロパティを保存できます。  クラス `IPersistPropertyBagImpl` は、このインターフェイスの既定の実装を提供し、デバッグ ビルドでダンプ デバイスに情報を送信して **IUnknown** を実装します。  
  
 **IPersistPropertyBag** は [IPropertyBag](https://msdn.microsoft.com/en-us/library/aa768196.aspx) と [IErrorLog](https://msdn.microsoft.com/en-us/library/aa768231.aspx)と連携して動作します。  これらの後の 2 種類のクライアントがインターフェイスを実装する必要があります。  `IPropertyBag`すると、クライアントはオブジェクトの個々のプロパティを保存し、読み込みます。  **IErrorLog**によって、オブジェクトとクライアントの両方が発生したエラーを報告できます。  
  
 **関連トピック** [ATL チュートリアル](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)、[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## 継承階層  
 `IPersistPropertyBag`  
  
 `IPersistPropertyBagImpl`  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 参照  
 [BEGIN\_PROP\_MAP](../Topic/BEGIN_PROP_MAP.md)   
 [クラスの概要](../../atl/atl-class-overview.md)