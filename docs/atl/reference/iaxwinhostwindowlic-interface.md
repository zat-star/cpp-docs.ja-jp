---
title: "IAxWinHostWindowLic インターフェイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAxWinHostWindowLic
dev_langs:
- C++
helpviewer_keywords:
- IAxWinHostWindowLic interface
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: 01ff8a7205418583606cbfdb1c028d7097501e00
ms.lasthandoff: 02/24/2017

---
# <a name="iaxwinhostwindowlic-interface"></a>IAxWinHostWindowLic インターフェイス
このインターフェイスは、ライセンスされたコントロールとそのホスト オブジェクトを操作するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
interface IAxWinHostWindowLic : IAxWinHostWindow
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[CreateControlLic](#createcontrollic)|ライセンスされたコントロールを作成し、そのホスト オブジェクトをアタッチします。|  
|[CreateControlLicEx](#createcontrollicex)|ライセンスされたコントロールを作成、ホスト オブジェクトをアタッチおよび必要に応じて、イベント ハンドラーを設定します。|  
  
## <a name="remarks"></a>コメント  
 `IAxWinHostWindowLic`継承[IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md)し、ライセンスされたコントロールの作成をサポートするメソッドを追加します。  
  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)のこのインターフェイスのメンバーを使用するサンプルです。  
  
## <a name="requirements"></a>要件  
 このインターフェイスの定義は、次のようとして idl ファイルまたは C++ では、使用可能です。  
  
|定義の種類|ファイル|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|ATLIFace.h (ATLBase.h にも含まれます)|  
  
##  <a name="a-namecreatecontrollica--iaxwinhostwindowliccreatecontrollic"></a><a name="createcontrollic"></a>IAxWinHostWindowLic::CreateControlLic  
 ライセンスされたコントロールを作成し、初期化して、し、によって識別されたウィンドウでホスト`hWnd`します。  
  
```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```  
  
### <a name="parameters"></a>パラメーター  
 `bstrLic`  
 [in]コントロールのライセンス キーを含む BSTR です。  
  
### <a name="remarks"></a>コメント  
 参照してください[については](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol)残りのパラメーターと戻り値の詳細についてです。  
  
 このメソッドを呼び出すには、[呼び出し](#createcontrollicex)  
  
### <a name="example"></a>例  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)を使用するサンプルの`IAxWinHostWindowLic::CreateControlLic`です。  
  
##  <a name="a-namecreatecontrollicexa--iaxwinhostwindowliccreatecontrollicex"></a><a name="createcontrollicex"></a>呼び出し  
 ライセンスされた ActiveX コントロールを作成し、初期化して、し、指定したウィンドウでホスト[については](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol)です。  
  
```
STDMETHOD(CreateControlLicEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise,
    BSTR bstrLic);
```  
  
### <a name="parameters"></a>パラメーター  
 `bstrLic`  
 [in]コントロールのライセンス キーを含む BSTR です。  
  
### <a name="remarks"></a>コメント  
 参照してください[詳細](../../atl/reference/iaxwinhostwindow-interface.md#createcontrolex)残りのパラメーターと戻り値の詳細についてです。  
  
### <a name="example"></a>例  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)を使用するサンプルの`IAxWinHostWindowLic::CreateControlLicEx`です。










