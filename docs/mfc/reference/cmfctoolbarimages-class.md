---
title: "CMFCToolBarImages クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarImages
- AFXTOOLBARIMAGES/CMFCToolBarImages
- AFXTOOLBARIMAGES/CMFCToolBarImages::CMFCToolBarImages
- AFXTOOLBARIMAGES/CMFCToolBarImages::AdaptColors
- AFXTOOLBARIMAGES/CMFCToolBarImages::AddIcon
- AFXTOOLBARIMAGES/CMFCToolBarImages::AddImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::CleanUp
- AFXTOOLBARIMAGES/CMFCToolBarImages::Clear
- AFXTOOLBARIMAGES/CMFCToolBarImages::ConvertTo32Bits
- AFXTOOLBARIMAGES/CMFCToolBarImages::CopyImageToClipboard
- AFXTOOLBARIMAGES/CMFCToolBarImages::CopyTo
- AFXTOOLBARIMAGES/CMFCToolBarImages::CreateFromImageList
- AFXTOOLBARIMAGES/CMFCToolBarImages::CreateRegionFromImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::DeleteImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::Draw
- AFXTOOLBARIMAGES/CMFCToolBarImages::DrawEx
- AFXTOOLBARIMAGES/CMFCToolBarImages::EnableRTL
- AFXTOOLBARIMAGES/CMFCToolBarImages::EndDrawImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::ExtractIcon
- AFXTOOLBARIMAGES/CMFCToolBarImages::FillDitheredRect
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetAlwaysLight
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetBitsPerPixel
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetCount
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetDisabledImageAlpha
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetFadedImageAlpha
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetImageSize
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetImageWell
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetImageWellLight
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetLastImageRect
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetLightPercentage
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetMapTo3DColors
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetMask
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetResourceOffset
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetScale
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetTransparentColor
- AFXTOOLBARIMAGES/CMFCToolBarImages::GrayImages
- AFXTOOLBARIMAGES/CMFCToolBarImages::Is32BitTransparencySupported
- AFXTOOLBARIMAGES/CMFCToolBarImages::IsPreMultiplyAutoCheck
- AFXTOOLBARIMAGES/CMFCToolBarImages::IsRTL
- AFXTOOLBARIMAGES/CMFCToolBarImages::IsReadOnly
- AFXTOOLBARIMAGES/CMFCToolBarImages::IsScaled
- AFXTOOLBARIMAGES/CMFCToolBarImages::IsUserImagesList
- AFXTOOLBARIMAGES/CMFCToolBarImages::IsValid
- AFXTOOLBARIMAGES/CMFCToolBarImages::Load
- AFXTOOLBARIMAGES/CMFCToolBarImages::LoadStr
- AFXTOOLBARIMAGES/CMFCToolBarImages::MapFromSysColor
- AFXTOOLBARIMAGES/CMFCToolBarImages::MapTo3dColors
- AFXTOOLBARIMAGES/CMFCToolBarImages::MapToSysColor
- AFXTOOLBARIMAGES/CMFCToolBarImages::MapToSysColorAlpha
- AFXTOOLBARIMAGES/CMFCToolBarImages::Mirror
- AFXTOOLBARIMAGES/CMFCToolBarImages::MirrorBitmap
- AFXTOOLBARIMAGES/CMFCToolBarImages::MirrorBitmapVert
- AFXTOOLBARIMAGES/CMFCToolBarImages::MirrorVert
- AFXTOOLBARIMAGES/CMFCToolBarImages::OnSysColorChange
- AFXTOOLBARIMAGES/CMFCToolBarImages::PrepareDrawImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::Save
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetAlwaysLight
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetDisabledImageAlpha
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetFadedImageAlpha
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetImageSize
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetLightPercentage
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetMapTo3DColors
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetPreMultiplyAutoCheck
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetSingleImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetTransparentColor
- AFXTOOLBARIMAGES/CMFCToolBarImages::SmoothResize
- AFXTOOLBARIMAGES/CMFCToolBarImages::UpdateImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::PreMultiplyAlpha
- AFXTOOLBARIMAGES/CMFCToolBarImages::m_bDisableTrueColorAlpha
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarImages class
ms.assetid: d4e50518-9ffc-406f-9996-f79e5cd38155
caps.latest.revision: 31
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ff94497108033b17d52b79594fdbe30e8ed7da03
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarimages-class"></a>CMFCToolBarImages クラス
ツールバー上のイメージです。 `CMFCToolBarImages`クラスはアプリケーション リソースまたはファイルから読み込んだツール バー イメージを管理します。  
   [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
## <a name="syntax"></a>構文  
  
```  
class CMFCToolBarImages : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolBarImages::CMFCToolBarImages](#cmfctoolbarimages)|`CMFCToolBarImages` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolBarImages::AdaptColors](#adaptcolors)||  
|[CMFCToolBarImages::AddIcon](#addicon)|ツール バー イメージにアイコンを追加します。|  
|[CMFCToolBarImages::AddImage](#addimage)|ツール バー イメージをビットマップを追加します。|  
|[CMFCToolBarImages::CleanUp](#cleanup)||  
|[CMFCToolBarImages::Clear](#clear)|このオブジェクトに割り当てられたシステム リソースを解放します。|  
|[CMFCToolBarImages::ConvertTo32Bits](#convertto32bits)|変換では、32 ビット/ピクセルの画像にビットマップを下線が付きます。|  
|[CMFCToolBarImages::CopyImageToClipboard](#copyimagetoclipboard)||  
|[CMFCToolBarImages::CopyTo](#copyto)||  
|[CMFCToolBarImages::CreateFromImageList](#createfromimagelist)|イメージ リストのツール バー イメージを初期化します ( [CImageList クラス](../../mfc/reference/cimagelist-class.md))。|  
|[CMFCToolBarImages::CreateRegionFromImage](#createregionfromimage)||  
|[CMFCToolBarImages::DeleteImage](#deleteimage)|このツール バー イメージのセットには、ユーザー定義のイメージが含まれている場合は、ツール バー イメージの指定したインデックスを持つイメージを削除します。|  
|[CMFCToolBarImages::Draw](#draw)|単一のツール バー イメージ (ボタン) を描画します。|  
|[CMFCToolBarImages::DrawEx](#drawex)||  
|[CMFCToolBarImages::EnableRTL](#enablertl)||  
|[CMFCToolBarImages::EndDrawImage](#enddrawimage)|ツール バー イメージを描画した後は、システム リソースを解放します。|  
|[CMFCToolBarImages::ExtractIcon](#extracticon)|ツール バー イメージからイメージを指定したインデックス位置にあるアイコンを返します。|  
|[CMFCToolBarImages::FillDitheredRect](#fillditheredrect)|ツールバーの背景色のブラシを使用して、四角形を格納します。|  
|[CMFCToolBarImages::GetAlwaysLight](#getalwayslight)||  
|[CMFCToolBarImages::GetBitsPerPixel](#getbitsperpixel)|下線付きのイメージの現在の解像度を返します。|  
|[CMFCToolBarImages::GetCount](#getcount)|ツールバーのイメージの数を返します。|  
|[CMFCToolBarImages::GetDisabledImageAlpha](#getdisabledimagealpha)|無効なイメージに使用するアルファ チャネル値を返します。|  
|[CMFCToolBarImages::GetFadedImageAlpha](#getfadedimagealpha)||  
|[CMFCToolBarImages::GetImageSize](#getimagesize)|メモリ (ソース サイズ) に格納されているツール バー イメージのサイズ、または (コピー先のサイズ)、画面上に描画されるツール バー イメージのサイズを取得します。|  
|[CMFCToolBarImages::GetImageWell](#getimagewell)|すべてのツール バー イメージを含むビットマップへのハンドルを返します。|  
|[CMFCToolBarImages::GetImageWellLight](#getimagewelllight)||  
|[CMFCToolBarImages::GetLastImageRect](#getlastimagerect)||  
|[CMFCToolBarImages::GetLightPercentage](#getlightpercentage)||  
|[CMFCToolBarImages::GetMapTo3DColors](#getmapto3dcolors)||  
|[CMFCToolBarImages::GetMask](#getmask)||  
|[CMFCToolBarImages::GetResourceOffset](#getresourceoffset)|特定のリソース ID をイメージのインデックスを返します|  
|[CMFCToolBarImages::GetScale](#getscale)|下線付きのイメージの現在のスケール比を返します。|  
|[CMFCToolBarImages::GetTransparentColor](#gettransparentcolor)||  
|[CMFCToolBarImages::GrayImages](#grayimages)|無効な外観にすることのツール バー イメージを淡色表示されます。|  
|[CMFCToolBarImages::Is32BitTransparencySupported](#is32bittransparencysupported)|オペレーティング システムが 32 ビットのアルファ ブレンドをサポートしているかどうかを決定します。|  
|[CMFCToolBarImages::IsPreMultiplyAutoCheck](#ispremultiplyautocheck)||  
|[CMFCToolBarImages::IsRTL](#isrtl)|右から左 (RTL) のサポートが有効になっているかどうかを判断します。|  
|[CMFCToolBarImages::IsReadOnly](#isreadonly)|ツール バー イメージは読み取り専用であるかどうかを決定します。|  
|[CMFCToolBarImages::IsScaled](#isscaled)|下線付きのイメージをスケーリングするかどうかどうかを指示します。|  
|[CMFCToolBarImages::IsUserImagesList](#isuserimageslist)|このツール バー イメージのセットにユーザー定義のイメージが含まれているかどうかを判断します。|  
|[CMFCToolBarImages::IsValid](#isvalid)|このツール バー イメージのセットが有効なツール バー イメージを含むかどうかを決定します。|  
|[CMFCToolBarImages::Load](#load)|システム リソースまたはファイルからは、ツール バー イメージを読み込みます。|  
|[CMFCToolBarImages::LoadStr](#loadstr)||  
|[CMFCToolBarImages::MapFromSysColor](#mapfromsyscolor)||  
|[CMFCToolBarImages::MapTo3dColors](#mapto3dcolors)||  
|[CMFCToolBarImages::MapToSysColor](#maptosyscolor)||  
|[CMFCToolBarImages::MapToSysColorAlpha](#maptosyscoloralpha)||  
|[CMFCToolBarImages::Mirror](#mirror)|ツール バー イメージのすべてを水平方向に反転します。|  
|[CMFCToolBarImages::MirrorBitmap](#mirrorbitmap)|水平方向にビットマップを反転します。|  
|[CMFCToolBarImages::MirrorBitmapVert](#mirrorbitmapvert)||  
|[CMFCToolBarImages::MirrorVert](#mirrorvert)||  
|[CMFCToolBarImages::OnSysColorChange](#onsyscolorchange)||  
|[CMFCToolBarImages::PrepareDrawImage](#preparedrawimage)|指定されたサイズにツール バー イメージを描画するために必要なリソースが割り当てられます。|  
|[CMFCToolBarImages::Save](#save)|このツール バー イメージのセットには、ユーザー定義のイメージが含まれている場合、ツール バー イメージをファイルに格納します。|  
|[CMFCToolBarImages::SetAlwaysLight](#setalwayslight)||  
|[CMFCToolBarImages::SetDisabledImageAlpha](#setdisabledimagealpha)|無効なイメージに使用するアルファ チャネル値を設定します。|  
|[CMFCToolBarImages::SetFadedImageAlpha](#setfadedimagealpha)||  
|[CMFCToolBarImages::SetImageSize](#setimagesize)|ツール バー イメージ (ソースのサイズ) のサイズを設定します。|  
|[CMFCToolBarImages::SetLightPercentage](#setlightpercentage)||  
|[CMFCToolBarImages::SetMapTo3DColors](#setmapto3dcolors)||  
|[CMFCToolBarImages::SetPreMultiplyAutoCheck](#setpremultiplyautocheck)||  
|[CMFCToolBarImages::SetSingleImage](#setsingleimage)||  
|[CMFCToolBarImages::SetTransparentColor](#settransparentcolor)|ツール バー イメージの透明色を設定します。|  
|[CMFCToolBarImages::SmoothResize](#smoothresize)|スムーズに下線付きのイメージのサイズを変更します。|  
|[CMFCToolBarImages::UpdateImage](#updateimage)|ビットマップからツールバーのユーザー定義のイメージを更新します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolBarImages::PreMultiplyAlpha](#premultiplyalpha)||  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolBarImages::m_bDisableTrueColorAlpha](#m_bdisabletruecoloralpha)|`TRUE`場合は true カラー アルファ ブレンド (32 ビット カラー) は無効です。|  
  
## <a name="remarks"></a>コメント  
 管理のツール バー イメージの完全なビットマップ`CMFCToolbarImages`固定サイズの小さなツール バー イメージ (ボタン) を&1; つまたは複数ので構成されています。  
  
## <a name="example"></a>例  
 次の例では、構成、`CMFCToolBarImages`オブジェクトのさまざまなメソッドを使用して、`CMFCToolBarImages`クラスです。 この例では、ツール バー イメージのサイズを設定し、イメージの読み込み、画像の透明色を設定する方法を示します。 このコード スニペットの一部である、 [Visual Studio のデモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#32;](../../mfc/codesnippet/cpp/cmfctoolbarimages-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo #&33;](../../mfc/codesnippet/cpp/cmfctoolbarimages-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCToolBarImages`   
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxtoolbarimages.h  
  
##  <a name="adaptcolors"></a>CMFCToolBarImages::AdaptColors  

  
```  
void AdaptColors(
    COLORREF clrBase,  
    COLORREF clrTone);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `clrBase`  
 [入力] `clrTone`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="addicon"></a>CMFCToolBarImages::AddIcon  
 ツール バー イメージの一覧にアイコンを追加します。  
  
```  
int AddIcon(
    HICON hIcon,  
    BOOL bAlphaBlend=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hIcon`  
 追加するアイコンへのハンドル。  
  
 [入力] `bAlphaBlend`  
 `TRUE`このアイコンをアルファ ブレンドで使用する場合それ以外の場合`FALSE`します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合に追加されたツール バー イメージの&0; から始まるインデックスそれ以外の場合は-1。  
  
##  <a name="addimage"></a>CMFCToolBarImages::AddImage  
 ツール バー イメージをビットマップを追加します。  
  
```  
int AddImage(
    HBITMAP hbmp,  
    BOOL bSetBitPerPixel=FALSE);

int AddImage(
    const CMFCToolBarImages& imageList,  
    int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hbmp`  
 追加するビットマップへのハンドル。  
  
 [入力] `bSetBitPerPixel`  
 `TRUE`場合、`CMFCToolBarImages`オブジェクトは、新しいイメージの色深度 (ビット/ピクセル) を使用`FALSE`場合、`CMFCToolbarImages`オブジェクトが現在の色深度を保持します。  
  
 [入力] `imageList`  
 参照、`CMFCToolbarImages`を追加するイメージを含むオブジェクト。  
  
 [入力] `nIndex`  
 ソースのインデックス`CMFCToolbarImages`を追加するイメージのオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 イメージのツールバーの数、`CMFCToolBarImages`オブジェクトは、新しいビットマップを正常に追加した後、保持、操作が失敗した場合は-1。  
  
##  <a name="cleanup"></a>CMFCToolBarImages::CleanUp  

  
```  
static void __stdcall CleanUp();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="clear"></a>CMFCToolBarImages::Clear  
 システム リソースを解放する、 [CMFCToolbarImages](../../mfc/reference/cmfctoolbarimages-class.md)に割り当てられたオブジェクト。  
  
```  
void Clear();
```  
  
##  <a name="cmfctoolbarimages"></a>CMFCToolBarImages::CMFCToolBarImages  
 `CMFCToolBarImages` オブジェクトを構築します。  
  
```  
CMFCToolBarImages();
```  
  
### <a name="remarks"></a>コメント  
 構築、`CMFCToolBarImages`オブジェクト、そのレンダリング エンジンを初期化および 16 × 15 ピクセル イメージのサイズをその既定値に設定します。 使用[CMFCToolBarImages::SetImageSize](#setimagesize)イメージを追加する前に、イメージのサイズを変更します。  
  
##  <a name="copyimagetoclipboard"></a>CMFCToolBarImages::CopyImageToClipboard  

  
```  
BOOL CopyImageToClipboard(int iImage);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iImage`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="copyto"></a>CMFCToolBarImages::CopyTo  

  
```  
BOOL CopyTo(CMFCToolBarImages& imageList);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `imageList`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="createfromimagelist"></a>CMFCToolBarImages::CreateFromImageList  
 ツール バー イメージからの初期化、 [CImageList クラス](../../mfc/reference/cimagelist-class.md)オブジェクトです。  
  
```  
BOOL CreateFromImageList(const CImageList& imageList);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `imageList`  
 ツール バー イメージのソースとして使用するイメージのリスト。  
  
### <a name="return-value"></a>戻り値  
 常に `TRUE` を返します。  
  
### <a name="remarks"></a>コメント  
 この関数を使用して、外部イメージの一覧からツールバーのイメージ リストを簡単に初期化します。  
  
##  <a name="createregionfromimage"></a>CMFCToolBarImages::CreateRegionFromImage  

  
```  
static HRGN __stdcall CreateRegionFromImage(
    HBITMAP bmp,  
    COLORREF clrTransparent);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bmp`  
 [入力] `clrTransparent`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="deleteimage"></a>CMFCToolBarImages::DeleteImage  
 ツール バー イメージの指定したインデックスを持つユーザー定義のイメージを削除します。  
  
```  
BOOL DeleteImage(int iImage);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iImage`  
 削除するイメージの&0; から始まるインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`イメージが正常に削除された場合`FALSE`イメージのインデックスが有効でない場合、`CMFCToolbarImages`オブジェクトは、一時的なもの、`CMFCToolbarImages`オブジェクトにユーザー定義のイメージが含まれていないか、エラーが発生するその他の場合。  
  
##  <a name="draw"></a>CMFCToolBarImages::Draw  
 単一のツール バー イメージを描画します。  
  
```  
BOOL Draw(
    CDC* pDC,  
    int x,  
    int y,  
    int iImageIndex,  
    BOOL bHilite=FALSE,  
    BOOL bDisabled=FALSE,  
    BOOL bIndeterminate=FALSE,  
    BOOL bShadow=FALSE,  
    BOOL bInactive=FALSE,  
    BYTE alphaSrc=255);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `x`  
 イメージが描画する四角形の左端の X 座標。  
  
 [入力] `y`  
 イメージが描画する四角形の上端の Y 座標。  
  
 [入力] `iImageIndex`  
 表示するイメージの&0; から始まるインデックス。  
  
 [入力] `bHilite`  
 `TRUE`場合は、イメージが強調表示されます。それ以外の場合`FALSE`します。  
  
 [入力] `bDisabled`  
 `TRUE`イメージが無効なスタイルで描画する場合それ以外の場合`FALSE`します。  
  
 [入力] `bIndeterminate`  
 `TRUE`イメージが中間状態のスタイルで描画する場合それ以外の場合`FALSE`します。  
  
 [入力] `bShadow`  
 `TRUE`イメージが; 影付きで描画する場合それ以外の場合`FALSE`します。  
  
 [入力] `bInactive`  
 `TRUE`イメージが、非アクティブな状態のスタイルで描画する場合それ以外の場合`FALSE`します。  
  
 [入力] `alphaSrc`  
 アルファ チャネル (不透明度) の値。 255 の値が、イメージを描画非透過的です。 値が 0 の場合、イメージ透明を描画します。 この値は、32 ビット カラー イメージと Windows Vista のグラス スタイルを表示イメージのみに使用されます。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`指定したイメージが正常に表示された場合`FALSE`場合は、イメージのインデックスが無効か、その他のエラーが発生しました。  
  
##  <a name="drawex"></a>CMFCToolBarImages::DrawEx  

  
```  
BOOL DrawEx(
    CDC* pDC,  
    CRect rect,  
    int iImageIndex,  
    ImageAlignHorz horzAlign = ImageAlignHorzLeft,  
    ImageAlignVert vertAlign = ImageAlignVertTop,  
    CRect rectSrc = CRect(0,
    0,
    0,
    0),  
    BYTE alphaSrc = 255);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `iImageIndex`  
 [入力] `horzAlign`  
 [入力] `vertAlign`  
 [入力] `rectSrc`  
 [入力] `0`  
 [入力] `0)`  
 [入力] `alphaSrc`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="enablertl"></a>CMFCToolBarImages::EnableRTL  

  
```  
static void __stdcall EnableRTL(BOOL bIsRTL = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bIsRTL`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="enddrawimage"></a>CMFCToolBarImages::EndDrawImage  
 システム リソースを解放する[CMFCToolBarImages::PrepareDrawImage](#preparedrawimage)を呼び出してツール バー イメージを描画した後に割り当てられた[CMFCToolBarImages::Draw](#draw)します。  
  
```  
void EndDrawImage(CAfxDrawState& ds);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `ds`  
 参照、`CAfxDrawState`に渡されたオブジェクト、`PrepareDrawImage`メソッドです。  
  
##  <a name="extracticon"></a>CMFCToolBarImages::ExtractIcon  
 ツール バー イメージからイメージを指定したインデックス位置にあるアイコンを返します。  
  
```  
HICON ExtractIcon(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 イメージ リストには、アイコンとして抽出するイメージが存在する場所の&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 抽出したアイコンへのハンドルまたは`NULL`場合`nIndex`が範囲外です。  
  
##  <a name="fillditheredrect"></a>CMFCToolBarImages::FillDitheredRect  
 ツールバーの背景色で四角形を塗りつぶします。  
  
```  
static void FillDitheredRect(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `rect`  
 塗りつぶす四角形の座標。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、四角形をシステム カラー COLOR_BTNFACE と COLOR_BTNHIGHLIGHT の平均値である色で塗りつぶされます。 システムが 256 色以下を使用している場合、四角形が入力されますそれら 2 つの色のディザー パターン代わりにします。  
  
##  <a name="getalwayslight"></a>CMFCToolBarImages::GetAlwaysLight  

  
```  
BOOL GetAlwaysLight() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getcount"></a>CMFCToolBarImages::GetCount  
 ツール バー イメージの一覧で、イメージの数を返します。  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 イメージの数、`CMFCToolBarImages`オブジェクトです。  
  
##  <a name="getdisabledimagealpha"></a>CMFCToolBarImages::GetDisabledImageAlpha  
 無効なイメージに使用するアルファ チャネル (不透明度) の値を返します。  
  
```  
static BYTE GetDisabledImageAlpha();
```  
  
### <a name="return-value"></a>戻り値  
 現在のアルファ チャネル値。  
  
### <a name="remarks"></a>コメント  
 呼び出すことができます[CMFCToolBarImages::SetDisabledImageAlpha](#setdisabledimagealpha)アルファ チャネル値を変更します。  
  
##  <a name="getfadedimagealpha"></a>CMFCToolBarImages::GetFadedImageAlpha  

  
```  
static BYTE __stdcall GetFadedImageAlpha();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getimagesize"></a>CMFCToolBarImages::GetImageSize  
 メモリ (ソース サイズ) に格納されているツール バー イメージのサイズ、または (コピー先のサイズ)、画面上に描画されるツール バー イメージのサイズを取得します。  
  
```  
SIZE GetImageSize(BOOL bDest=FALSE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bDest`  
 `TRUE`コピー先のサイズを取得するには`FALSE`ソース イメージのサイズを取得します。  
  
### <a name="return-value"></a>戻り値  
 A`SIZE`構造体は、イメージのサイズをピクセル単位で指定します。  
  
### <a name="remarks"></a>コメント  
 ソース イメージのサイズに格納されているイメージのサイズ、 [CMFCToolbarImages](../../mfc/reference/cmfctoolbarimages-class.md)オブジェクトです。 呼び出すことができます[CMFCToolBarImages::SetImageSize](#setimagesize)ソースのサイズを設定します。 既定値は、16 × 15 ピクセルです。  
  
 既定では、送信先のイメージ サイズは、0x0 です。 呼び出したときに、送信先のサイズを指定する[CMFCToolBarImages::PrepareDrawImage](#preparedrawimage)します。 [CMFCToolBarImages::EndDrawImage](#enddrawimage)メソッドでは、送信先のサイズを既定値にリセットします。  
  
##  <a name="getimagewell"></a>CMFCToolBarImages::GetImageWell  
 すべてのツール バー イメージを含むビットマップへのハンドルを返します。  
  
```  
HBITMAP GetImageWell() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ツール バー イメージを含むビットマップへのハンドル。  
  
### <a name="remarks"></a>コメント  
 ツール バー イメージと呼ばれる&1; つのビットマップの行に格納されている、*イメージ ウェル*します。 イメージ ウェル内のツール バー イメージを検索するには、ツール バー イメージの幅をイメージのインデックスを掛けます (を参照してください[CMFCToolBarImages::GetImageSize](#getimagesize)) も、イメージ内のイメージの水平方向のオフセットを取得します。  
  
##  <a name="getimagewelllight"></a>CMFCToolBarImages::GetImageWellLight  

  
```  
HBITMAP GetImageWellLight() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getlastimagerect"></a>CMFCToolBarImages::GetLastImageRect  

  
```  
CRect GetLastImageRect() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getlightpercentage"></a>CMFCToolBarImages::GetLightPercentage  

  
```  
int GetLightPercentage() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getmapto3dcolors"></a>CMFCToolBarImages::GetMapTo3DColors  

  
```  
BOOL GetMapTo3DColors() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getmask"></a>CMFCToolBarImages::GetMask  

  
```  
HBITMAP GetMask(int iImage);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iImage`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getresourceoffset"></a>CMFCToolBarImages::GetResourceOffset  
 特定のリソース ID をイメージのインデックスを返します  
  
```  
int GetResourceOffset(UINT uiResId) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiResId`  
 イメージのリソース ID  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、イメージのインデックス指定されたリソース ID を使用してイメージが存在しない場合は-1 を返します。  
  
##  <a name="gettransparentcolor"></a>CMFCToolBarImages::GetTransparentColor  

  
```  
COLORREF GetTransparentColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="grayimages"></a>CMFCToolBarImages::GrayImages  
 無効な外観にすることのツール バー イメージを淡色表示されます。  
  
```  
BOOL GrayImages(int nGrayImageLuminancePercentage);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nGrayImageLuminancePercentage`  
 輝度の割合。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`コレクション内のイメージが正常に淡色表示された場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、各ピクセルの赤、緑、および青のコンポーネントの平均を計算して、結果の乗算で、ツール バー イメージを変更`nGrayImageLuminancePercentage`100 で除算します。 場合`nGrayImageLuminancePercentage`がゼロまたは負の場合、130 の既定値は、代わりに使用します。  
  
> [!NOTE]
>  変更を元に戻す場合は、元のイメージを再読み込みする必要があります。 呼び出すことによってこれを行う[CMFCToolBarImages::Load](#load)または[CMFCToolBarImages::UpdateImage](#updateimage) (だけのユーザー定義のイメージ)、またはを呼び出して[CMFCToolBarImages::Clear](#clear)を呼び出して、イメージをもう一度追加[CMFCToolBarImages::AddIcon](#addicon)または[CMFCToolBarImages::AddImage](#addimage)します。  
  
##  <a name="is32bittransparencysupported"></a>CMFCToolBarImages::Is32BitTransparencySupported  
 オペレーティング システムが 32 ビットのアルファ ブレンドをサポートしているかどうかを指定します。  
  
```  
static BOOL Is32BitTransparencySupported();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`32 ビットのアルファ ブレンドがサポートされている場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 この静的メソッドを使用して、実行時に、オペレーティング システムが 32 ビットのアルファ ブレンドをサポートしているかどうかを決定します。 この機能はサポート[!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)]以降のバージョン。  
  
##  <a name="ispremultiplyautocheck"></a>CMFCToolBarImages::IsPreMultiplyAutoCheck  

  
```  
BOOL IsPreMultiplyAutoCheck() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isreadonly"></a>CMFCToolBarImages::IsReadOnly  
 ツール バー イメージは読み取り専用であるかどうかを指定します。  
  
```  
BOOL IsReadOnly() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ツール バー イメージか読み取り専用、それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 `CMFCToolbarImages`ツール バー イメージのビットマップが読み取り専用のファイルから読み込まれたとき、またはを使用して、ビットマップがコピーされたオブジェクトは読み取り専用、`CMFCToolBarImages::CopyTemp`メソッドです。  
  
##  <a name="isrtl"></a>CMFCToolBarImages::IsRTL  
 右から左 (RTL) のサポートが有効になっているかどうかを指定します。  
  
```  
static BOOL IsRTL();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`RTL のサポートが有効の場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 RTL のサポートは、アプリケーションを右から左、アラビア語、ヘブライ語、ペルシア語、またはウルドゥ語などに読まれる言語にローカライズするときに使用されます。  
  
##  <a name="isuserimageslist"></a>CMFCToolBarImages::IsUserImagesList  
 このツール バー イメージのセットがユーザー定義のイメージを含むかどうかを指定します。  
  
```  
BOOL IsUserImagesList() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合、`CMFCToolBarImages`オブジェクトには、ユーザー定義のツール バー イメージが含まれています。 そうしないと`FALSE`です。  
  
##  <a name="isvalid"></a>CMFCToolBarImages::IsValid  
 このツール バー イメージのセットが有効なツール バー イメージを含むかどうかを示します。  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合、`CMFCToolBarImages`オブジェクトが有効な`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 `CMFCToolBarImages`オブジェクトがツール バー イメージのビットマップへのハンドルが無効`NULL`します。  
  
##  <a name="load"></a>CMFCToolBarImages::Load  
 システム リソースまたはファイルからは、ツール バー イメージを読み込みます。  
  
```  
BOOL Load(
    UINT uiResID,  
    HINSTANCE hinstRes=NULL,  
    BOOL bAdd=FALSE);

BOOL Load(
    LPCTSTR lpszBmpFileName,   
    DWORD nMaxFileSize = 819200);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiResID`  
 ビットマップ リソースの ID です。  
  
 [入力] `hinstRes`  
 リソース DLL のインスタンス。  
  
 [入力] `bAdd`  
 `TRUE`既存のビットマップに読み込まれたビットマップを追加するまたは`FALSE`を既存のビットマップを置き換えます。  
  
 [入力] `lpszBmpFileName`  
 ビットマップの読み込み元のディスク ファイルへのパス。  
  
 [入力] `nMaxFileSize`  
 ビットマップ ファイル内のバイトの最大数または、ファイル サイズに関係なく、ビットマップを読み込む場合は 0 です。 メソッドが戻るかどうかは、ファイルのサイズは、この最大サイズを超えている`FALSE`ビットマップは読み込まれません。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ビットマップが正常に読み込まれている場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 ファイルに読み取り専用属性がある場合、イメージ リストは読み取り専用とマークされます。  
  
##  <a name="loadstr"></a>CMFCToolBarImages::LoadStr  

  
```  
BOOL LoadStr(
    LPCTSTR lpszResourceName,  
    HINSTANCE hinstRes = NULL,  
    BOOL bAdd = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszResourceName`  
 [入力] `hinstRes`  
 [入力] `bAdd`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="mapfromsyscolor"></a>CMFCToolBarImages::MapFromSysColor  

  
```  
static COLORREF __stdcall MapFromSysColor(
    COLORREF color,  
    BOOL bUseRGBQUAD = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `color`  
 [入力] `bUseRGBQUAD`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="mapto3dcolors"></a>CMFCToolBarImages::MapTo3dColors  

  
```  
BOOL MapTo3dColors(
    BOOL bUseRGBQUAD = TRUE,  
    COLORREF clrSrc = (COLORREF)-1,  
    COLORREF clrDest = (COLORREF)-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bUseRGBQUAD`  
 [入力] `clrSrc`  
 [入力] `clrDest`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="maptosyscolor"></a>CMFCToolBarImages::MapToSysColor  

  
```  
static COLORREF __stdcall MapToSysColor(
    COLORREF color,  
    BOOL bUseRGBQUAD = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `color`  
 [入力] `bUseRGBQUAD`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="maptosyscoloralpha"></a>CMFCToolBarImages::MapToSysColorAlpha  

  
```  
static COLORREF __stdcall MapToSysColorAlpha(COLORREF color);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `color`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="mirror"></a>CMFCToolBarImages::Mirror  
 ツール バー イメージを水平方向のミラー イメージで置き換えます。  
  
```  
BOOL Mirror();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`イメージが正常にミラー化された場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、右から左へ記述するシステムをサポートするために使用されます。  
  
##  <a name="mirrorbitmap"></a>CMFCToolBarImages::MirrorBitmap  
 ビットマップを水平方向のミラー イメージに置き換えます。  
  
```  
static BOOL MirrorBitmap(
    HBITMAP& hbmp,  
    int cxImage);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力] `hbmp`  
 ミラー化するビットマップへのハンドル。  
  
 [入力] `cxImage`  
 ピクセル単位でイメージの幅。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`イメージが正常にミラー化された場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 この関数は、右から左へ記述するシステムをサポートするために使用されます。  
  
##  <a name="mirrorbitmapvert"></a>CMFCToolBarImages::MirrorBitmapVert  

  
```  
static BOOL __stdcall MirrorBitmapVert(
    HBITMAP& hbmp,  
    int cyImage);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hbmp`  
 [入力] `cyImage`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="mirrorvert"></a>CMFCToolBarImages::MirrorVert  

  
```  
BOOL MirrorVert();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onsyscolorchange"></a>CMFCToolBarImages::OnSysColorChange  

  
```  
void OnSysColorChange();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="premultiplyalpha"></a>CMFCToolBarImages::PreMultiplyAlpha  

  
```  
static BOOL __stdcall PreMultiplyAlpha(
    HBITMAP hbmp,  
    BOOL bAutoCheckPremlt);

BOOL PreMultiplyAlpha(HBITMAP hbmp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hbmp`  
 [入力] `bAutoCheckPremlt`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="m_bdisabletruecoloralpha"></a>CMFCToolBarImages::m_bDisableTrueColorAlpha  
 `TRUE`場合は true カラー アルファ ブレンド (32 ビット カラー) は無効です。  
  
```  
static BOOL m_bDisableTrueColorAlpha;  
```  
  
### <a name="remarks"></a>コメント  
 このメンバー変数を設定`FALSE`true カラー ツール バー イメージのアルファ ブレンドを有効にします。  
  
 既定値は`TRUE`旧バージョンとの互換性のためです。  
  
##  <a name="preparedrawimage"></a>CMFCToolBarImages::PrepareDrawImage  
 指定されたサイズにツール バー イメージを描画するために必要なリソースが割り当てられます。  
  
```  
BOOL PrepareDrawImage(
    CAfxDrawState& ds,  
    CSize sizeImageDest=CSize(0,
    0)  
    BOOL bFadeInactive=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `ds`  
 参照を`CAfxDrawState`イメージ レンダリング ステージ間で割り当てられたリソースを格納する構造体。  
  
 [入力] `sizeImageDest`  
 コピー先の画像のサイズを指定します。  
  
 [入力] `bFadeInactive`  
 `TRUE`アクティブでない場合、描画されるイメージがフェードします。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ツール バー イメージを描画するために必要なリソースそれ以外の場合、正常に割り当てられた場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出した後は、呼び出す[CMFCToolBarImages::Draw](#draw)何回でも。 描画が完了した後に呼び出す必要があります[CMFCToolBarImages::EndDrawImage](#enddrawimage)によって割り当てられたリソースを解放する`PrepareDrawImage`です。  
  
##  <a name="save"></a>CMFCToolBarImages::Save  
 このツール バー イメージのセットには、ユーザー定義のイメージが含まれている場合、ツール バー イメージをファイルに格納します。  
  
```  
BOOL Save(LPCTSTR lpszBmpFileName=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszBmpFileName`  
 ディスク ファイルへのパス。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ツール バー イメージが正常に保存されている場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 ユーザー定義のイメージをディスク ファイルに保存するには、このメソッドを呼び出します。 場合`lpszBmpFileName`は`NULL`、メソッドでは、ビットマップを格納して、ビットマップの読み込み元ファイルに、 [CMFCToolBarImages::Load](#load)メソッドです。  
  
##  <a name="setalwayslight"></a>CMFCToolBarImages::SetAlwaysLight  

  
```  
void SetAlwaysLight(BOOL bAlwaysLight = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bAlwaysLight`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setdisabledimagealpha"></a>CMFCToolBarImages::SetDisabledImageAlpha  
 無効なイメージに使用するアルファ チャネル (不透明度) の値を設定します。  
  
```  
static void SetDisabledImageAlpha(BYTE nValue);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nValue`  
 アルファ チャネルの新しい値。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、無効なイメージのカスタムのアルファ値を設定できます。 既定値は、127 はそれが原因で無効にされたボタンの画像を半透明にします。 値 0 を設定した場合、無効なイメージは完全に透過的になります。 255 の値を設定した場合、無効なイメージは完全に不透明になります。  
  
##  <a name="setfadedimagealpha"></a>CMFCToolBarImages::SetFadedImageAlpha  

  
```  
static void __stdcall SetFadedImageAlpha(BYTE nValue);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nValue`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setimagesize"></a>CMFCToolBarImages::SetImageSize  
 ツール バー イメージ (ソースのサイズ) のサイズを設定します。  
  
```  
void SetImageSize(
    SIZE sizeImage,  
    BOOL bUpdateCount=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `sizeImage`  
 ツール バー イメージの新しいサイズ。  
  
### <a name="remarks"></a>コメント  
 既定では、ツール バー イメージのサイズは 16 × 15 ピクセルです。 異なるサイズのツール バー イメージを使用する場合は、このメソッドを呼び出します。  
  
##  <a name="setlightpercentage"></a>CMFCToolBarImages::SetLightPercentage  

  
```  
void SetLightPercentage(int nValue);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nValue`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setmapto3dcolors"></a>CMFCToolBarImages::SetMapTo3DColors  

  
```  
void SetMapTo3DColors(BOOL bMapTo3DColors);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bMapTo3DColors`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setpremultiplyautocheck"></a>CMFCToolBarImages::SetPreMultiplyAutoCheck  

  
```  
void SetPreMultiplyAutoCheck(BOOL bAuto = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bAuto`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setsingleimage"></a>CMFCToolBarImages::SetSingleImage  

  
```  
void SetSingleImage();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="settransparentcolor"></a>CMFCToolBarImages::SetTransparentColor  
 ツール バー イメージの透明色を設定します。  
  
```  
COLORREF SetTransparentColor(COLORREF clrTransparent);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `clrTransparent`  
 RGB 値。  
  
### <a name="return-value"></a>戻り値  
 前の透明色。  
  
### <a name="remarks"></a>コメント  
 またはフレームワークが呼び出す場合[CMFCToolBarImages::Draw](#draw)、メソッドがによって指定された色に一致する任意のピクセルを描画しない`clrTransparent`します。  
  
##  <a name="updateimage"></a>CMFCToolBarImages::UpdateImage  
 ビットマップからツールバーのユーザー定義のイメージを更新します。  
  
```  
BOOL UpdateImage(
    int iImage,  
    HBITMAP hbmp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iImage`  
 更新するイメージの&0; から始まるインデックス。  
  
 [入力] `hbmp`  
 元のイメージを更新するビットマップへのハンドル。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`イメージが正常に更新された場合`FALSE`イメージの一覧にある、またはユーザー定義の一時的な場合です。  
  
##  <a name="convertto32bits"></a>CMFCToolBarImages::ConvertTo32Bits  
 変換では、32 ビット/ピクセルの画像にビットマップを下線が付きます。  
  
```  
BOOL ConvertTo32Bits(COLORREF clrTransparent = (COLORREF)-1);
```  
  
### <a name="parameters"></a>パラメーター  
 `clrTransparent`  
 下線付きのビットマップの透明色を指定します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getbitsperpixel"></a>CMFCToolBarImages::GetBitsPerPixel  
 下線付きのイメージの現在の解像度を返します。  
  
```  
int GetBitsPerPixel() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ビット/ピクセル (bpp) 内の下線付きのイメージの現在の解像度を表す整数値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getscale"></a>CMFCToolBarImages::GetScale  
 下線付きのイメージの現在のスケール比を返します。  
  
```  
double GetScale() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のスケール比を表す値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isscaled"></a>CMFCToolBarImages::IsScaled  
 下線付きのイメージをスケーリングするかどうかどうかを指示します。  
  
```  
BOOL IsScaled () const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`下線付きのイメージがスケーリングされる場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="smoothresize"></a>CMFCToolBarImages::SmoothResize  
 スムーズに下線付きのイメージのサイズを変更します。  
  
```  
BOOL SmoothResize(double dblImageScale);
```  
  
### <a name="parameters"></a>パラメーター  
 `dblImageScale`  
 スケールの比率です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`サイズ変更が成功した場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)

