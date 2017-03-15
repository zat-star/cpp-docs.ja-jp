---
title: "CD2DBitmapBrush クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DBitmapBrush
- afxrendertarget/CD2DBitmapBrush
dev_langs:
- C++
helpviewer_keywords:
- CD2DBitmapBrush class
ms.assetid: 46ebbe34-66e0-44c8-af1d-d129e851de5e
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
ms.openlocfilehash: a9ab15dcae8715b98cc9f723a710b64e83649bf9
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dbitmapbrush-class"></a>CD2DBitmapBrush クラス
ID2D1BitmapBrush のラッパーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DBitmapBrush : public CD2DBrush;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBitmapBrush::CD2DBitmapBrush](#cd2dbitmapbrush)|オーバーロードされます。 ファイルから CD2DBitmapBrush オブジェクトを構築します。|  
|[CD2DBitmapBrush:: ~ CD2DBitmapBrush](#dtor)|デストラクターです。 D2D ビットマップ ブラシ オブジェクトが破棄されるときに呼び出されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBitmapBrush::Attach](#attach)|オブジェクトにリソース インタ フェースを既存の接続|  
|[CD2DBitmapBrush::Create](#create)|CD2DBitmapBrush を作成します。 (上書き[CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create))。|  
|[CD2DBitmapBrush::Destroy](#destroy)|CD2DBitmapBrush オブジェクトを破棄します。 (上書き[CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy))。|  
|[CD2DBitmapBrush::Detach](#detach)|オブジェクトからリソース インタ フェースをデタッチします。|  
|[CD2DBitmapBrush::Get](#get)|返します。 ID2D1BitmapBrush インターフェイス|  
|[CD2DBitmapBrush::GetBitmap](#getbitmap)|このブラシを使用して描画するビットマップのソースを取得します。|  
|[CD2DBitmapBrush::GetExtendModeX](#getextendmodex)|ブラシ水平方向に並べて表示がそのビットマップにまで及ぶ領域メソッドを取得します|  
|[CD2DBitmapBrush::GetExtendModeY](#getextendmodey)|ブラシ垂直方向に並べて表示がそのビットマップにまで及ぶ領域メソッドを取得します|  
|[CD2DBitmapBrush::GetInterpolationMode](#getinterpolationmode)|ブラシのビットマップを拡大縮小または回転するときに使用する補間メソッドを取得します|  
|[CD2DBitmapBrush::SetBitmap](#setbitmap)|このブラシを使用して描画するビットマップのソースを指定します|  
|[CD2DBitmapBrush::SetExtendModeX](#setextendmodex)|そのビットマップにまで及ぶが領域が水平方向にタイル ブラシ方法を指定します。|  
|[CD2DBitmapBrush::SetExtendModeY](#setextendmodey)|どのようにブラシ垂直方向に並べて表示そのビットマップにまで及ぶが領域を指定します。|  
|[CD2DBitmapBrush::SetInterpolationMode](#setinterpolationmode)|ブラシのビットマップを拡大縮小または回転するときに使用する補間モードを指定します|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBitmapBrush::CommonInit](#commoninit)|オブジェクトを初期化します|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBitmapBrush::operator ID2D1BitmapBrush *](#operator_id2d1bitmapbrush_star)|返します。 ID2D1BitmapBrush インターフェイス|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBitmapBrush::m_pBitmap](#m_pbitmap)|CD2DBitmap オブジェクトへのポインターを格納します。|  
|[CD2DBitmapBrush::m_pBitmapBrush](#m_pbitmapbrush)|ID2D1BitmapBrush オブジェクトへのポインターを格納します。|  
|[CD2DBitmapBrush::m_pBitmapBrushProperties](#m_pbitmapbrushproperties)|ブラシのプロパティをビットマップします。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 `CD2DBitmapBrush`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="a-namedtora--cd2dbitmapbrushcd2dbitmapbrush"></a><a name="dtor"></a>CD2DBitmapBrush:: ~ CD2DBitmapBrush  
 デストラクターです。 D2D ビットマップ ブラシ オブジェクトが破棄されるときに呼び出されます。  
  
```  
virtual ~CD2DBitmapBrush();
```  
  
##  <a name="a-nameattacha--cd2dbitmapbrushattach"></a><a name="attach"></a>CD2DBitmapBrush::Attach  
 オブジェクトにリソース インタ フェースを既存の接続  
  
```  
void Attach(ID2D1BitmapBrush* pResource);
```  
  
### <a name="parameters"></a>パラメーター  
 `pResource`  
 既存のリソースのインターフェイスです。 NULL にすることはできません。  
  
##  <a name="a-namecd2dbitmapbrusha--cd2dbitmapbrushcd2dbitmapbrush"></a><a name="cd2dbitmapbrush"></a>CD2DBitmapBrush::CD2DBitmapBrush  
 CD2DBitmapBrush オブジェクトを構築します。  
  
```  
CD2DBitmapBrush(
    CRenderTarget* pParentTarget,  
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);

 
CD2DBitmapBrush(
    CRenderTarget* pParentTarget,  
    UINT uiResID,  
    LPCTSTR lpszType = NULL,  
    CD2DSizeU sizeDest = CD2DSizeU(0, 0), 
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);

 
CD2DBitmapBrush(
    CRenderTarget* pParentTarget,  
    LPCTSTR lpszImagePath,  
    CD2DSizeU sizeDest = CD2DSizeU(0, 0), 
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentTarget`  
 レンダー ターゲットへのポインター。  
  
 `pBitmapBrushProperties`  
 拡張モードおよびビットマップ ブラシの補間モードへのポインター。  
  
 `pBrushProperties`  
 不透明度とブラシの変換へのポインター。  
  
 `bAutoDestroy`  
 所有者 (pParentTarget) によって、オブジェクトが破棄されることを示します。  
  
 `uiResID`  
 リソースのリソース ID 番号。  
  
 `lpszType`  
 リソースの種類を表す null で終わる文字列へのポインター。  
  
 `sizeDest`  
 コピー先ビットマップのサイズ。  
  
 `lpszImagePath`  
 ファイルの名前を表す null で終わる文字列へのポインター。  
  
##  <a name="a-namecommoninita--cd2dbitmapbrushcommoninit"></a><a name="commoninit"></a>CD2DBitmapBrush::CommonInit  
 オブジェクトを初期化します  
  
```  
void CommonInit(D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties);
```  
  
### <a name="parameters"></a>パラメーター  
 `pBitmapBrushProperties`  
 ビットマップ ブラシのプロパティへのポインター。  
  
##  <a name="a-namecreatea--cd2dbitmapbrushcreate"></a><a name="create"></a>CD2DBitmapBrush::Create  
 CD2DBitmapBrush を作成します。  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `pRenderTarget`  
 レンダー ターゲットへのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
##  <a name="a-namedestroya--cd2dbitmapbrushdestroy"></a><a name="destroy"></a>CD2DBitmapBrush::Destroy  
 CD2DBitmapBrush オブジェクトを破棄します。  
  
```  
virtual void Destroy();
```  
  
##  <a name="a-namedetacha--cd2dbitmapbrushdetach"></a><a name="detach"></a>CD2DBitmapBrush::Detach  
 オブジェクトからリソース インタ フェースをデタッチします。  
  
```  
ID2D1BitmapBrush* Detach();
```  
  
### <a name="return-value"></a>戻り値  
 デタッチされたリソース インタ フェースへのポインター。  
  
##  <a name="a-namegeta--cd2dbitmapbrushget"></a><a name="get"></a>CD2DBitmapBrush::Get  
 返します。 ID2D1BitmapBrush インターフェイス  
  
```  
ID2D1BitmapBrush* Get();
```  
  
### <a name="return-value"></a>戻り値  
 ID2D1BitmapBrush インターフェイスまたはオブジェクトがまだ初期化されていない場合は NULL へのポインター。  
  
##  <a name="a-namegetbitmapa--cd2dbitmapbrushgetbitmap"></a><a name="getbitmap"></a>CD2DBitmapBrush::GetBitmap  
 このブラシを使用して描画するビットマップのソースを取得します。  
  
```  
CD2DBitmap* GetBitmap();
```  
  
### <a name="return-value"></a>戻り値  
 CD2DBitmap オブジェクトまたはオブジェクトがまだ初期化されていない場合は NULL へのポインター。  
  
##  <a name="a-namegetextendmodexa--cd2dbitmapbrushgetextendmodex"></a><a name="getextendmodex"></a>CD2DBitmapBrush::GetExtendModeX  
 ブラシ水平方向に並べて表示がそのビットマップにまで及ぶ領域メソッドを取得します  
  
```  
D2D1_EXTEND_MODE GetExtendModeX() const;  
```  
  
### <a name="return-value"></a>戻り値  
 そのビットマップにまで及ぶが領域が水平方向にタイル ブラシ方法を指定する値  
  
##  <a name="a-namegetextendmodeya--cd2dbitmapbrushgetextendmodey"></a><a name="getextendmodey"></a>CD2DBitmapBrush::GetExtendModeY  
 ブラシ垂直方向に並べて表示がそのビットマップにまで及ぶ領域メソッドを取得します  
  
```  
D2D1_EXTEND_MODE GetExtendModeY() const;  
```  
  
### <a name="return-value"></a>戻り値  
 どのようにブラシ垂直方向に並べて表示そのビットマップにまで及ぶが領域を指定する値  
  
##  <a name="a-namegetinterpolationmodea--cd2dbitmapbrushgetinterpolationmode"></a><a name="getinterpolationmode"></a>CD2DBitmapBrush::GetInterpolationMode  
 ブラシのビットマップを拡大縮小または回転するときに使用する補間メソッドを取得します  
  
```  
D2D1_BITMAP_INTERPOLATION_MODE GetInterpolationMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ブラシのビットマップを拡大縮小または回転するときに使用する補間メソッド  
  
##  <a name="a-namempbitmapa--cd2dbitmapbrushmpbitmap"></a><a name="m_pbitmap"></a>CD2DBitmapBrush::m_pBitmap  
 CD2DBitmap オブジェクトへのポインターを格納します。  
  
```  
CD2DBitmap* m_pBitmap;  
```  
  
##  <a name="a-namempbitmapbrusha--cd2dbitmapbrushmpbitmapbrush"></a><a name="m_pbitmapbrush"></a>CD2DBitmapBrush::m_pBitmapBrush  
 ID2D1BitmapBrush オブジェクトへのポインターを格納します。  
  
```  
ID2D1BitmapBrush* m_pBitmapBrush;  
```  
  
##  <a name="a-namempbitmapbrushpropertiesa--cd2dbitmapbrushmpbitmapbrushproperties"></a><a name="m_pbitmapbrushproperties"></a>CD2DBitmapBrush::m_pBitmapBrushProperties  
 ブラシのプロパティをビットマップします。  
  
```  
D2D1_BITMAP_BRUSH_PROPERTIES* m_pBitmapBrushProperties;  
```  
  
##  <a name="a-nameoperatorid2d1bitmapbrushstara--cd2dbitmapbrushoperator-id2d1bitmapbrush"></a><a name="operator_id2d1bitmapbrush_star"></a>CD2DBitmapBrush::operator ID2D1BitmapBrush *  
 返します。 ID2D1BitmapBrush インターフェイス  
  
```  
operator ID2D1BitmapBrush*();
```   
  
### <a name="return-value"></a>戻り値  
 ID2D1BitmapBrush インターフェイスまたはオブジェクトがまだ初期化されていない場合は NULL へのポインター。  
  
##  <a name="a-namesetbitmapa--cd2dbitmapbrushsetbitmap"></a><a name="setbitmap"></a>CD2DBitmapBrush::SetBitmap  
 このブラシを使用して描画するビットマップのソースを指定します  
  
```  
void SetBitmap(CD2DBitmap* pBitmap);
```  
  
### <a name="parameters"></a>パラメーター  
 `pBitmap`  
 ブラシで使用されるビットマップ ソース  
  
##  <a name="a-namesetextendmodexa--cd2dbitmapbrushsetextendmodex"></a><a name="setextendmodex"></a>CD2DBitmapBrush::SetExtendModeX  
 そのビットマップにまで及ぶが領域が水平方向にタイル ブラシ方法を指定します。  
  
```  
void SetExtendModeX(D2D1_EXTEND_MODE extendModeX);
```  
  
### <a name="parameters"></a>パラメーター  
 `extendModeX`  
 そのビットマップにまで及ぶが領域が水平方向にタイル ブラシ方法を指定する値  
  
##  <a name="a-namesetextendmodeya--cd2dbitmapbrushsetextendmodey"></a><a name="setextendmodey"></a>CD2DBitmapBrush::SetExtendModeY  
 どのようにブラシ垂直方向に並べて表示そのビットマップにまで及ぶが領域を指定します。  
  
```  
void SetExtendModeY(D2D1_EXTEND_MODE extendModeY);
```  
  
### <a name="parameters"></a>パラメーター  
 `extendModeY`  
 どのようにブラシ垂直方向に並べて表示そのビットマップにまで及ぶが領域を指定する値  
  
##  <a name="a-namesetinterpolationmodea--cd2dbitmapbrushsetinterpolationmode"></a><a name="setinterpolationmode"></a>CD2DBitmapBrush::SetInterpolationMode  
 ブラシのビットマップを拡大縮小または回転するときに使用する補間モードを指定します  
  
```  
void SetInterpolationMode(D2D1_BITMAP_INTERPOLATION_MODE interpolationMode);
```  
  
### <a name="parameters"></a>パラメーター  
 `interpolationMode`  
 ブラシのビットマップを拡大縮小または回転するときに使用する補間モード  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

