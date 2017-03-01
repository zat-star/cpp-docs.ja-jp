---
title: "CD2DBitmap クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxrendertarget/CD2DBitmap
- CD2DBitmap
dev_langs:
- C++
helpviewer_keywords:
- CD2DBitmap class
ms.assetid: 2b3686f1-812c-462b-b449-9f0cb6949bf6
caps.latest.revision: 17
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: f88a6376069c07c61311d74faca104e821a259bd
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dbitmap-class"></a>CD2DBitmap クラス
ID2D1Bitmap のラッパーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DBitmap : public CD2DResource;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBitmap::CD2DBitmap](#cd2dbitmap)|オーバーロードされます。 HBITMAP から CD2DBitmap オブジェクトを構築します。|  
|[CD2DBitmap:: ~ CD2DBitmap](#_dtorcd2dbitmap)|デストラクターです。 D2D bitmap オブジェクトが破棄されるときに呼び出されます。|  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBitmap::CD2DBitmap](#cd2dbitmap)|オーバーロードされます。 CD2DBitmap オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBitmap::Attach](#attach)|オブジェクトにリソース インタ フェースを既存の接続|  
|[CD2DBitmap::CopyFromBitmap](#copyfrombitmap)|指定した領域を指定したビットマップから現在のビットマップにコピーします。|  
|[CD2DBitmap::CopyFromMemory](#copyfrommemory)|指定した領域をメモリから現在のビットマップにコピーします。|  
|[CD2DBitmap::CopyFromRenderTarget](#copyfromrendertarget)|現在のビットマップにコピーから、指定した、指定したリージョンのレンダー ターゲット|  
|[CD2DBitmap::Create](#create)|CD2DBitmap を作成します。 (上書き[CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create))。|  
|[CD2DBitmap::Destroy](#destroy)|CD2DBitmap のオブジェクトを破棄します。 (上書き[CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy))。|  
|[CD2DBitmap::Detach](#detach)|オブジェクトからリソース インタ フェースをデタッチします。|  
|[CD2DBitmap::Get](#get)|返します。 ID2D1Bitmap インターフェイス|  
|[CD2DBitmap::GetDPI](#getdpi)|ドット/インチ (DPI) のビットマップを返す|  
|[CD2DBitmap::GetPixelFormat](#getpixelformat)|ビットマップのピクセル形式とアルファ モードを取得します。|  
|[CD2DBitmap::GetPixelSize](#getpixelsize)|ビットマップのサイズ、デバイスに依存しない単位 (ピクセル単位) を返します|  
|[CD2DBitmap::GetSize](#getsize)|ビットマップのサイズをデバイスに依存しないピクセル (Dip) でを返します|  
|[CD2DBitmap::IsValid](#isvalid)|リソースの有効性をチェックする (上書き[CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid))。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBitmap::CommonInit](#commoninit)|オブジェクトを初期化します|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBitmap::operator ID2D1Bitmap *](#operator_id2d1bitmap_star)|返します。 ID2D1Bitmap インターフェイス|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBitmap::m_bAutoDestroyHBMP](#m_bautodestroyhbmp)|TRUE の場合、m_hBmpSrc を破棄する必要があります。それ以外の場合は FALSE。|  
|[CD2DBitmap::m_hBmpSrc](#m_hbmpsrc)|ソース ビットマップ ハンドル。|  
|[CD2DBitmap::m_lpszType](#m_lpsztype)|リソースの種類。|  
|[CD2DBitmap::m_pBitmap](#m_pbitmap)|ID2D1Bitmap オブジェクトへのポインターを格納します。|  
|[CD2DBitmap::m_sizeDest](#m_sizedest)|コピー先のサイズをビットマップします。|  
|[CD2DBitmap::m_strPath](#m_strpath)|Botmap ファイルのパス。|  
|[CD2DBitmap::m_uiResID](#m_uiresid)|ビットマップ リソース id。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DBitmap`
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="a-namedtorcd2dbitmapa--cd2dbitmapcd2dbitmap"></a><a name="_dtorcd2dbitmap"></a>CD2DBitmap:: ~ CD2DBitmap  
 デストラクターです。 D2D bitmap オブジェクトが破棄されるときに呼び出されます。  
  
```  
virtual ~CD2DBitmap();
```  
  
##  <a name="a-nameattacha--cd2dbitmapattach"></a><a name="attach"></a>CD2DBitmap::Attach  
 オブジェクトにリソース インタ フェースを既存の接続  
  
```  
void Attach(ID2D1Bitmap* pResource);
```  
  
### <a name="parameters"></a>パラメーター  
 `pResource`  
 既存のリソースのインターフェイスです。 NULL にすることはできません。  
  
##  <a name="a-namecd2dbitmapa--cd2dbitmapcd2dbitmap"></a><a name="cd2dbitmap"></a>CD2DBitmap::CD2DBitmap  
 リソースから CD2DBitmap オブジェクトを構築します。  
  
```  
CD2DBitmap(
    CRenderTarget* pParentTarget,  
    UINT uiResID,  
    LPCTSTR lpszType = NULL,  
    CD2DSizeU sizeDest = CD2DSizeU(0, 0), 
    BOOL bAutoDestroy = TRUE);

 
CD2DBitmap(
    CRenderTarget* pParentTarget,  
    LPCTSTR lpszPath,  
    CD2DSizeU sizeDest = CD2DSizeU(0, 0), 
    BOOL bAutoDestroy = TRUE);

 
CD2DBitmap(
    CRenderTarget* pParentTarget,  
    HBITMAP hbmpSrc,  
    CD2DSizeU sizeDest = CD2DSizeU(0, 0), 
    BOOL bAutoDestroy = TRUE);

 
CD2DBitmap(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentTarget`  
 レンダー ターゲットへのポインター。  
  
 `uiResID`  
 リソースのリソース ID 番号。  
  
 `lpszType`  
 リソースの種類を表す null で終わる文字列へのポインター。  
  
 `sizeDest`  
 コピー先ビットマップのサイズ。  
  
 `bAutoDestroy`  
 所有者 (pParentTarget) によって、オブジェクトが破棄されることを示します。  
  
 `lpszPath`  
 ファイルの名前を表す null で終わる文字列へのポインター。  
  
 `hbmpSrc`  
 ビットマップへのハンドルします。  
  
##  <a name="a-namecommoninita--cd2dbitmapcommoninit"></a><a name="commoninit"></a>CD2DBitmap::CommonInit  
 オブジェクトを初期化します  
  
```  
void CommonInit();
```  
  
##  <a name="a-namecopyfrombitmapa--cd2dbitmapcopyfrombitmap"></a><a name="copyfrombitmap"></a>CD2DBitmap::CopyFromBitmap  
 指定した領域を指定したビットマップから現在のビットマップにコピーします。  
  
```  
HRESULT CopyFromBitmap(
    const CD2DBitmap* pBitmap,  
    const CD2DPointU* destPoint = NULL,  
    const CD2DRectU* srcRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pBitmap`  
 コピー元ビットマップ  
  
 `destPoint`  
 現在のビットマップ領域が srcRect で指定されている領域の左上隅をコピーします。  
  
 `srcRect`  
 コピーするビットマップの領域  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
##  <a name="a-namecopyfrommemorya--cd2dbitmapcopyfrommemory"></a><a name="copyfrommemory"></a>CD2DBitmap::CopyFromMemory  
 指定した領域をメモリから現在のビットマップにコピーします。  
  
```  
HRESULT CopyFromMemory(
    const void* srcData,  
    UINT32 pitch,  
    const CD2DRectU* destRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `srcData`  
 コピーするデータ  
  
 `pitch`  
 Stride、または srcData に格納されている元のビットマップの高さ。 Stride は、スキャン ライン (メモリ内のピクセルの&1; つの行) のバイト数です。 Stride は、次の数式に基づいて計算されます幅をピクセル単位 * メモリのパディング ピクセルあたりのバイト数。  
  
 `destRect`  
 現在のビットマップ領域が srcRect で指定されている領域の左上隅をコピーします。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
##  <a name="a-namecopyfromrendertargeta--cd2dbitmapcopyfromrendertarget"></a><a name="copyfromrendertarget"></a>CD2DBitmap::CopyFromRenderTarget  
 現在のビットマップにコピーから、指定した、指定したリージョンのレンダー ターゲット  
  
```  
HRESULT CopyFromRenderTarget(
    const CRenderTarget* pRenderTarget,  
    const CD2DPointU* destPoint = NULL,  
    const CD2DRectU* srcRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pRenderTarget`  
 コピーする領域を含むレンダー ターゲット  
  
 `destPoint`  
 現在のビットマップ領域が srcRect で指定されている領域の左上隅をコピーします。  
  
 `srcRect`  
 コピーするレンダリング ターゲットの領域  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
##  <a name="a-namecreatea--cd2dbitmapcreate"></a><a name="create"></a>CD2DBitmap::Create  
 CD2DBitmap を作成します。  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `pRenderTarget`  
 レンダー ターゲットへのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
##  <a name="a-namedestroya--cd2dbitmapdestroy"></a><a name="destroy"></a>CD2DBitmap::Destroy  
 CD2DBitmap のオブジェクトを破棄します。  
  
```  
virtual void Destroy();
```  
  
##  <a name="a-namedetacha--cd2dbitmapdetach"></a><a name="detach"></a>CD2DBitmap::Detach  
 オブジェクトからリソース インタ フェースをデタッチします。  
  
```  
ID2D1Bitmap* Detach();
```  
  
### <a name="return-value"></a>戻り値  
 デタッチされたリソース インタ フェースへのポインター。  
  
##  <a name="a-namegeta--cd2dbitmapget"></a><a name="get"></a>CD2DBitmap::Get  
 返します。 ID2D1Bitmap インターフェイス  
  
```  
ID2D1Bitmap* Get();
```  
  
### <a name="return-value"></a>戻り値  
 ID2D1Bitmap インターフェイスまたはオブジェクトがまだ初期化されていない場合は NULL へのポインター。  
  
##  <a name="a-namegetdpia--cd2dbitmapgetdpi"></a><a name="getdpi"></a>CD2DBitmap::GetDPI  
 ドット/インチ (DPI) のビットマップを返す  
  
```  
CD2DSizeF GetDPI() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ビットマップの水平および垂直 DPI。  
  
##  <a name="a-namegetpixelformata--cd2dbitmapgetpixelformat"></a><a name="getpixelformat"></a>CD2DBitmap::GetPixelFormat  
 ビットマップのピクセル形式とアルファ モードを取得します。  
  
```  
D2D1_PIXEL_FORMAT GetPixelFormat() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ビットマップのピクセル形式とアルファ モードです。  
  
##  <a name="a-namegetpixelsizea--cd2dbitmapgetpixelsize"></a><a name="getpixelsize"></a>CD2DBitmap::GetPixelSize  
 ビットマップのサイズ、デバイスに依存しない単位 (ピクセル単位) を返します  
  
```  
CD2DSizeU GetPixelSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ビットマップのピクセル サイズ.  
  
##  <a name="a-namegetsizea--cd2dbitmapgetsize"></a><a name="getsize"></a>CD2DBitmap::GetSize  
 ビットマップのサイズをデバイスに依存しないピクセル (Dip) でを返します  
  
```  
CD2DSizeF GetSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 Dip は、ビットマップのサイズ。  
  
##  <a name="a-nameisvalida--cd2dbitmapisvalid"></a><a name="isvalid"></a>CD2DBitmap::IsValid  
 リソースの有効性のチェック  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リソースが無効である場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="a-namembautodestroyhbmpa--cd2dbitmapmbautodestroyhbmp"></a><a name="m_bautodestroyhbmp"></a>CD2DBitmap::m_bAutoDestroyHBMP  
 TRUE の場合、m_hBmpSrc を破棄する必要があります。それ以外の場合は FALSE。  
  
```  
BOOL m_bAutoDestroyHBMP;  
```  
  
##  <a name="a-namemhbmpsrca--cd2dbitmapmhbmpsrc"></a><a name="m_hbmpsrc"></a>CD2DBitmap::m_hBmpSrc  
 ソース ビットマップ ハンドル。  
  
```  
HBITMAP m_hBmpSrc;  
```  
  
##  <a name="a-namemlpsztypea--cd2dbitmapmlpsztype"></a><a name="m_lpsztype"></a>CD2DBitmap::m_lpszType  
 リソースの種類。  
  
```  
LPCTSTR m_lpszType;  
```  
  
##  <a name="a-namempbitmapa--cd2dbitmapmpbitmap"></a><a name="m_pbitmap"></a>CD2DBitmap::m_pBitmap  
 ID2D1Bitmap オブジェクトへのポインターを格納します。  
  
```  
ID2D1Bitmap* m_pBitmap;  
```  
  
##  <a name="a-namemsizedesta--cd2dbitmapmsizedest"></a><a name="m_sizedest"></a>CD2DBitmap::m_sizeDest  
 コピー先のサイズをビットマップします。  
  
```  
CD2DSizeU m_sizeDest;  
```  
  
##  <a name="a-namemstrpatha--cd2dbitmapmstrpath"></a><a name="m_strpath"></a>CD2DBitmap::m_strPath  
 Botmap ファイルのパス。  
  
```  
CString m_strPath;  
```  
  
##  <a name="a-namemuiresida--cd2dbitmapmuiresid"></a><a name="m_uiresid"></a>CD2DBitmap::m_uiResID  
 ビットマップ リソース id。  
  
```  
UINT m_uiResID;  
```  
  
##  <a name="a-nameoperatorid2d1bitmapstara--cd2dbitmapoperator-id2d1bitmap"></a><a name="operator_id2d1bitmap_star"></a>CD2DBitmap::operator ID2D1Bitmap *  
 返します。 ID2D1Bitmap インターフェイス  
  
```  
operator ID2D1Bitmap*();
```   
  
### <a name="return-value"></a>戻り値  
 ID2D1Bitmap インターフェイスまたはオブジェクトがまだ初期化されていない場合は NULL へのポインター。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

