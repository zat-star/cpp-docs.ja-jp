---
title: "IDataObjectImpl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IDataObjectImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "データ転送 [C++]"
  - "データ転送 [C++], 汎用データ転送"
  - "IDataObject, ATL の実装"
  - "IDataObjectImpl クラス"
ms.assetid: b680f0f7-7795-40a1-a0f6-f48768201c89
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# IDataObjectImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、汎用データ転送をサポートして接続を管理するためのメソッドが用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template< class   
      T  
      >  
class IDataObjectImpl  
```  
  
#### パラメーター  
 `T`  
 `IDataObjectImpl`から派生したクラス。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IDataObjectImpl::DAdvise](../Topic/IDataObjectImpl::DAdvise.md)|データ オブジェクトとアドバイズ シンク間の接続を確立します。  これは、オブジェクトの変更通知の受信をアドバイズ シンクができます。|  
|[IDataObjectImpl::DUnadvise](../Topic/IDataObjectImpl::DUnadvise.md)|前に `DAdvise`を通じて確立された接続を終了します。|  
|[IDataObjectImpl::EnumDAdvise](../Topic/IDataObjectImpl::EnumDAdvise.md)|現在のアドバイザリ コネクションを反復処理するための列挙子を作成します。|  
|[IDataObjectImpl::EnumFormatEtc](../Topic/IDataObjectImpl::EnumFormatEtc.md)|列挙子をデータ オブジェクトでサポート **FORMATETC** の構造を反復処理するに作成します。  ATL 実装は、**E\_NOTIMPL**を返します。|  
|[IDataObjectImpl::FireDataChange](../Topic/IDataObjectImpl::FireDataChange.md)|各に変更通知をアドバイズ シンクに送り返します。|  
|[IDataObjectImpl::GetCanonicalFormatEtc](../Topic/IDataObjectImpl::GetCanonicalFormatEtc.md)|より複雑な 1 に **FORMATETC** の論理的に等価の構造体を取得します。  ATL 実装は、**E\_NOTIMPL**を返します。|  
|[IDataObjectImpl::GetData](../Topic/IDataObjectImpl::GetData.md)|データ オブジェクトからクライアントにデータを転送します。  データは **FORMATETC** の構造に記述され、**STGMEDIUM** の構造を通じて転送されます。|  
|[IDataObjectImpl::GetDataHere](../Topic/IDataObjectImpl::GetDataHere.md)|クライアントが **STGMEDIUM** の構造を割り当てる必要がある点 `GetData`に似ています。  ATL 実装は、**E\_NOTIMPL**を返します。|  
|[IDataObjectImpl::QueryGetData](../Topic/IDataObjectImpl::QueryGetData.md)|データ オブジェクトが移動のデータの **FORMATETC** の特定の構造をサポートするかどうかを判定します。  ATL 実装は、**E\_NOTIMPL**を返します。|  
|[IDataObjectImpl::SetData](../Topic/IDataObjectImpl::SetData.md)|クライアントからデータ オブジェクトにデータを転送します。  ATL 実装は、**E\_NOTIMPL**を返します。|  
  
## 解説  
 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) のインターフェイスのサポートは均一のデータ転送にメソッドを提供します。  `IDataObject` は、データを取得および格納するために標準書式 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 構造と [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) を使用します。  
  
 `IDataObject` は、データの変更の通知を処理するアドバイズ シンクするように接続を管理する。  データを受け取るクライアントにデータ オブジェクトからの通知を、クライアント アドバイズ シンクと呼ばれるオブジェクトの [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) のインターフェイスを実装する。変更します。  クライアントは、**IDataObject::DAdvise**を呼び出すと、接続は、データ オブジェクトとアドバイズ シンク間に確立されます。  
  
 クラス `IDataObjectImpl` は `IDataObject` の既定の実装を提供し、デバッグ ビルドでダンプ デバイスに情報を送信して **IUnknown** を実装します。  
  
 **関連トピック** [ATL チュートリアル](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)、[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## 継承階層  
 `IDataObject`  
  
 `IDataObjectImpl`  
  
## 必要条件  
 **Header:** atlctl.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)