---
title: "クラスを使って |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPictureHolder
- AFXCTL/CPictureHolder
- AFXCTL/CPictureHolder::CPictureHolder
- AFXCTL/CPictureHolder::CreateEmpty
- AFXCTL/CPictureHolder::CreateFromBitmap
- AFXCTL/CPictureHolder::CreateFromIcon
- AFXCTL/CPictureHolder::CreateFromMetafile
- AFXCTL/CPictureHolder::GetDisplayString
- AFXCTL/CPictureHolder::GetPictureDispatch
- AFXCTL/CPictureHolder::GetType
- AFXCTL/CPictureHolder::Render
- AFXCTL/CPictureHolder::SetPictureDispatch
- AFXCTL/CPictureHolder::m_pPict
dev_langs:
- C++
helpviewer_keywords:
- Picture property
- controls [MFC], OLE
- OLE controls, image
- CPictureHolder class
ms.assetid: a4f59775-704a-41dd-b5bd-2e531c95127a
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 14a774e3edc8b5e160b287612d3709c3424503be
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cpictureholder-class"></a>使ってクラス
ユーザーは、コントロールにピクチャを表示できるように、[ピクチャ] プロパティを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CPictureHolder  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CPictureHolder::CPictureHolder](#cpictureholder)|`CPictureHolder` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPictureHolder::CreateEmpty](#createempty)|空の `CPictureHolder` オブジェクトを作成します。|  
|[CPictureHolder::CreateFromBitmap](#createfrombitmap)|作成、`CPictureHolder`ビットマップからのオブジェクト。|  
|[CPictureHolder::CreateFromIcon](#createfromicon)|作成、`CPictureHolder`アイコンからのオブジェクト。|  
|[CPictureHolder::CreateFromMetafile](#createfrommetafile)|作成、`CPictureHolder`メタファイルからのオブジェクト。|  
|[CPictureHolder::GetDisplayString](#getdisplaystring)|コントロール コンテナーのプロパティ ブラウザーに表示される文字列を取得します。|  
|[CPictureHolder::GetPictureDispatch](#getpicturedispatch)|返します。、`CPictureHolder`オブジェクトの`IDispatch`インターフェイスです。|  
|[CPictureHolder::GetType](#gettype)|通知するかどうか、`CPictureHolder`オブジェクトは、ビットマップ、アイコン、または、メタファイルです。|  
|[CPictureHolder::Render](#render)|画像をレンダリングします。|  
|[CPictureHolder::SetPictureDispatch](#setpicturedispatch)|セット、`CPictureHolder`オブジェクトの`IDispatch`インターフェイスです。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPictureHolder::m_pPict](#m_ppict)|ピクチャ オブジェクトへのポインター。|  
  
## <a name="remarks"></a>コメント  
 `CPictureHolder`基本クラスはありません。  
  
 ストックの画像のプロパティを使用して、開発者は、ビットマップ、アイコン、または表示するためのメタファイルを指定できます。  
  
 ユーザー設定の画像のプロパティを作成する方法の詳細については、記事を参照してください。 [MFC ActiveX コントロール: ActiveX コントロールにおけるピクチャの使用](../../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CPictureHolder`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxctl.h  
  
##  <a name="cpictureholder"></a>CPictureHolder::CPictureHolder  
 `CPictureHolder` オブジェクトを構築します。  
  
```  
CPictureHolder();
```  
  
##  <a name="createempty"></a>CPictureHolder::CreateEmpty  
 空の作成`CPictureHolder`オブジェクトし、それに接続、`IPicture`インターフェイスです。  
  
```  
BOOL CreateEmpty();
```  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが正常に作成された場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="createfrombitmap"></a>CPictureHolder::CreateFromBitmap  
 オブジェクトを初期化するために、ビットマップを使用して、`CPictureHolder`です。  
  
```  
BOOL CreateFromBitmap(
    UINT idResource);

 
BOOL CreateFromBitmap(
    CBitmap* pBitmap,  
    CPalette* pPal = NULL,  
    BOOL bTransferOwnership = TRUE);

 
BOOL CreateFromBitmap(
    HBITMAP hbm,  
    HPALETTE hpal = NULL,  
    BOOL bTransferOwnership = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `idResource`  
 ビットマップ リソースのリソース ID です。  
  
 `pBitmap`  
 ポインター、 [CBitmap](../../mfc/reference/cbitmap-class.md)オブジェクトです。  
  
 *pPal*  
 ポインター、 [CPalette](../../mfc/reference/cpalette-class.md)オブジェクトです。  
  
 `bTransferOwnership`  
 ピクチャ オブジェクトがビットマップとパレット オブジェクトの所有権を持つかどうかを示します。  
  
 `hbm`  
 元のビットマップへのハンドル、`CPictureHolder`オブジェクトを作成します。  
  
 `hpal`  
 ビットマップの描画に使用するパレットへのハンドルします。  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが正常に作成された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 場合`bTransferOwnership`は**TRUE**呼び出し元は、ビットマップを使用しないでください、または、この呼び出しの後の任意の方法でパレット オブジェクトを返します。 場合`bTransferOwnership`は**FALSE**、ピクチャ オブジェクトの有効期間のビットマップとパレット オブジェクトが効力を確保するため、呼び出し元ができます。  
  
##  <a name="createfromicon"></a>CPictureHolder::CreateFromIcon  
 オブジェクトを初期化するために、アイコンを使用して、`CPictureHolder`です。  
  
```  
BOOL CreateFromIcon(
    UINT idResource);

 
BOOL CreateFromIcon(
    HICON hIcon,  
    BOOL bTransferOwnership = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `idResource`  
 ビットマップ リソースのリソース ID です。  
  
 `hIcon`  
 元のアイコンへのハンドル、`CPictureHolder`オブジェクトを作成します。  
  
 `bTransferOwnership`  
 ピクチャ オブジェクトがアイコン オブジェクトの所有権を持つかどうかを示します。  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが正常に作成された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 場合`bTransferOwnership`は**TRUE**、呼び出し元は、いない、この呼び出しが戻った後まったくアイコン オブジェクトを使用する必要があります。 場合`bTransferOwnership`は**FALSE**、呼び出し元がそのアイコン オブジェクトは有効な画像オブジェクトの有効期間のことを保証します。  
  
##  <a name="createfrommetafile"></a>CPictureHolder::CreateFromMetafile  
 オブジェクトを初期化するために、メタファイルを使用して、`CPictureHolder`です。  
  
```  
BOOL CreateFromMetafile(
    HMETAFILE hmf,  
    int xExt,  
    int yExt,  
    BOOL bTransferOwnership = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `hmf`  
 作成するために使用するメタファイルのハンドル、`CPictureHolder`オブジェクトです。  
  
 *xExt*  
 画像のエクステント x。  
  
 *yExt*  
 画像の Y の範囲。  
  
 `bTransferOwnership`  
 ピクチャ オブジェクトがメタファイル オブジェクトの所有権を持つかどうかを示します。  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが正常に作成された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 場合`bTransferOwnership`は**TRUE**、呼び出し元は、いない、この呼び出しが戻った後まったくメタファイル オブジェクトを使用する必要があります。 場合`bTransferOwnership`は**FALSE**、呼び出し元がそのメタファイル オブジェクトは有効な画像オブジェクトの有効期間のことを保証します。  
  
##  <a name="getdisplaystring"></a>CPictureHolder::GetDisplayString  
 コンテナーのプロパティ ブラウザーに表示される文字列を取得します。  
  
```  
BOOL GetDisplayString(CString& strValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `strValue`  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)表示文字列を保持します。  
  
### <a name="return-value"></a>戻り値  
 文字列が取得できた場合は 0 以外それ以外の場合 0 を返します。  
  
##  <a name="getpicturedispatch"></a>CPictureHolder::GetPictureDispatch  
 この関数へのポインターを返し、`CPictureHolder`オブジェクトの`IPictureDisp`インターフェイスです。  
  
```  
LPPICTUREDISP GetPictureDispatch();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CPictureHolder`オブジェクトの`IPictureDisp`インターフェイスです。  
  
### <a name="remarks"></a>コメント  
 呼び出し元が呼び出す必要があります**リリース**を使い終わったら、このポインターです。  
  
##  <a name="gettype"></a>CPictureHolder::GetType  
 画像がビットマップ、メタファイル、またはアイコンがあるかどうかを示します。  
  
```  
short GetType();
```  
  
### <a name="return-value"></a>戻り値  
 画像の種類を示す値。 使用可能な値とその意味は次のとおりです。  
  
|値|説明|  
|-----------|-------------|  
|**PICTYPE_UNINITIALIZED**|`CPictureHolder`オブジェクトが unititialized です。|  
|**PICTYPE_NONE**|`CPictureHolder`オブジェクトが空です。|  
|**PICTYPE_BITMAP**|画像は、ビットマップです。|  
|**PICTYPE_METAFILE**|画像は、メタファイルです。|  
|**PICTYPE_ICON**|画像は、アイコンです。|  
  
##  <a name="m_ppict"></a>CPictureHolder::m_pPict  
 ポインター、`CPictureHolder`オブジェクトの`IPicture`インターフェイスです。  
  
```  
LPPICTURE m_pPict;  
```  
  
##  <a name="render"></a>CPictureHolder::Render  
 によって参照される四角形に画像をレンダリング`rcRender`します。  
  
```  
void Render(
    CDC* pDC,  
    const CRect& rcRender,  
    const CRect& rcWBounds);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 画像がレンダリングされるディスプレイ コンテキストへのポインター。  
  
 `rcRender`  
 画像のレンダリングの四角形。  
  
 *rcWBounds*  
 画像が描画されるオブジェクトの外接する四角形を表す四角形。 コントロールの場合は、この四角形は、`rcBounds`のオーバーライドに渡されるパラメーター[オーバライド](../../mfc/reference/colecontrol-class.md#ondraw)します。  
  
##  <a name="setpicturedispatch"></a>CPictureHolder::SetPictureDispatch  
 接続、`CPictureHolder`オブジェクトを`IPictureDisp`インターフェイスです。  
  
```  
void SetPictureDispatch(LPPICTUREDISP pDisp);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDisp`  
 新しいポインター`IPictureDisp`インターフェイスです。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFontHolder クラス](../../mfc/reference/cfontholder-class.md)

