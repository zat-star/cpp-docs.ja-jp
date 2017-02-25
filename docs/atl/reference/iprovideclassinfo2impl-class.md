---
title: "IProvideClassInfo2Impl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IProvideClassInfo2"
  - "ATL.IProvideClassInfo2Impl"
  - "IProvideClassInfo2Impl"
  - "ATL::IProvideClassInfo2Impl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "クラス情報, ATL"
  - "IProvideClassInfo2 ATL の実装"
  - "IProvideClassInfo2Impl クラス"
ms.assetid: d74956e8-9c69-4cba-b99d-ca1ac031bb9d
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# IProvideClassInfo2Impl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、[IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303) メソッドと [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764) メソッドの既定の実装を提供します。  
  
## 構文  
  
```  
  
      template <  
   const CLSID* pcoclsid,  
   const IID* psrcid,  
   const GUID* plibid = &CAtlModule::m_libid,  
   WORD wMajor = 1,  
   WORD wMinor = 0,  
   class tihclass = CComTypeInfoHolder   
>  
class ATL_NO_VTABLE IProvideClassInfo2Impl :  
   public IProvideClassInfo2  
```  
  
#### パラメーター  
 *pcoclsid*  
 コクラスの識別子へのポインター。  
  
 *psrcid*  
 コクラスの既定のアウトゴーイング ディスパッチ インターフェイスの識別子へのポインター。  
  
 `plibid`  
 インターフェイスに関する情報を保持するタイプ ライブラリの LIBID へのポインター。  既定では、サーバーレベルのタイプ ライブラリが渡されます。  
  
 `wMajor`  
 タイプ ライブラリのメジャー バージョン。  既定値は 1 です。  
  
 `wMinor`  
 タイプ ライブラリのマイナー バージョン。  既定値は 0 です。  
  
 `tihclass`  
 コクラスの型情報を管理するために使用されるクラス。  既定値 `CComTypeInfoHolder` です。  
  
## メンバー  
  
### コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](../Topic/IProvideClassInfo2Impl::IProvideClassInfo2Impl.md)|コンストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IProvideClassInfo2Impl::GetClassInfo](../Topic/IProvideClassInfo2Impl::GetClassInfo.md)|コクラスの型情報に **ITypeInfo** のポインターを取得します。|  
|[IProvideClassInfo2Impl::GetGUID](../Topic/IProvideClassInfo2Impl::GetGUID.md)|オブジェクトのアウトゴーイング ディスパッチ インターフェイスの GUID を取得します。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[IProvideClassInfo2Impl::\_tih](../Topic/IProvideClassInfo2Impl::_tih.md)|コクラスの型情報を管理します。|  
  
## 解説  
 [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764) のインターフェイスは `GetGUID` のメソッドを追加することによって [IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303) を拡張します。  このメソッドは、クライアントが既定のイベント セットのオブジェクトのアウトゴーイング インターフェイスの IID を取得できるようになります。  クラス `IProvideClassInfo2Impl` は **IProvideClassInfo** と `IProvideClassInfo2` のメソッドの既定の実装を提供します。  
  
 `IProvideClassInfo2Impl` は、コクラスの型情報を管理する型 `CComTypeInfoHolder` の静的メンバーが含まれます。  
  
## 継承階層  
 `IProvideClassInfo2`  
  
 `IProvideClassInfo2Impl`  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)