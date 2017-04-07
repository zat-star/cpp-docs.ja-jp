---
title: "CImage クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CImage
- ATLIMAGE/ATL::CImage
- ATLIMAGE/ATL::CImage::CImage
- ATLIMAGE/ATL::CImage::AlphaBlend
- ATLIMAGE/ATL::CImage::Attach
- ATLIMAGE/ATL::CImage::BitBlt
- ATLIMAGE/ATL::CImage::Create
- ATLIMAGE/ATL::CImage::CreateEx
- ATLIMAGE/ATL::CImage::Destroy
- ATLIMAGE/ATL::CImage::Detach
- ATLIMAGE/ATL::CImage::Draw
- ATLIMAGE/ATL::CImage::GetBits
- ATLIMAGE/ATL::CImage::GetBPP
- ATLIMAGE/ATL::CImage::GetColorTable
- ATLIMAGE/ATL::CImage::GetDC
- ATLIMAGE/ATL::CImage::GetExporterFilterString
- ATLIMAGE/ATL::CImage::GetHeight
- ATLIMAGE/ATL::CImage::GetImporterFilterString
- ATLIMAGE/ATL::CImage::GetMaxColorTableEntries
- ATLIMAGE/ATL::CImage::GetPitch
- ATLIMAGE/ATL::CImage::GetPixel
- ATLIMAGE/ATL::CImage::GetPixelAddress
- ATLIMAGE/ATL::CImage::GetTransparentColor
- ATLIMAGE/ATL::CImage::GetWidth
- ATLIMAGE/ATL::CImage::IsDIBSection
- ATLIMAGE/ATL::CImage::IsIndexed
- ATLIMAGE/ATL::CImage::IsNull
- ATLIMAGE/ATL::CImage::IsTransparencySupported
- ATLIMAGE/ATL::CImage::Load
- ATLIMAGE/ATL::CImage::LoadFromResource
- ATLIMAGE/ATL::CImage::MaskBlt
- ATLIMAGE/ATL::CImage::PlgBlt
- ATLIMAGE/ATL::CImage::ReleaseDC
- ATLIMAGE/ATL::CImage::ReleaseGDIPlus
- ATLIMAGE/ATL::CImage::Save
- ATLIMAGE/ATL::CImage::SetColorTable
- ATLIMAGE/ATL::CImage::SetPixel
- ATLIMAGE/ATL::CImage::SetPixelIndexed
- ATLIMAGE/ATL::CImage::SetPixelRGB
- ATLIMAGE/ATL::CImage::SetTransparentColor
- ATLIMAGE/ATL::CImage::StretchBlt
- ATLIMAGE/ATL::CImage::TransparentBlt
dev_langs:
- C++
helpviewer_keywords:
- jpeg files
- bitmaps [C++], ATL and MFC support for
- images [C++], ATL and MFC support for
- gif files, ATL and MFC support
- .gif files, ATL and MFC support
- PNG files, ATL and MFC support
- CImage class
- transparent color
ms.assetid: 52861e3d-bf7e-481f-a240-90e88f76c490
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: f74e5952401d6f9608425681cd91120b648e7b13
ms.lasthandoff: 02/24/2017

---
# <a name="cimage-class"></a>CImage クラス
`CImage`読み込んで、画像を JPEG、GIF、BMP、およびポータブル ネットワーク グラフィックス (PNG) 形式で保存する機能など、ビットマップの拡張サポートを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CImage
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CImage::CImage](#cimage)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CImage::AlphaBlend](#alphablend)|透明または半透明ピクセルのビットマップを表示します。|  
|[CImage::Attach](#attach)|アタッチ、`HBITMAP`に、`CImage`オブジェクトです。 非 DIB セクション ビットマップまたは DIB セクション ビットマップのいずれかで使用できます。|  
|[CImage::BitBlt](#bitblt)|コピー元デバイス コンテキストから現在のデバイス コンテキストにビットマップをコピーします。|  
|[CImage::Create](#create)|DIB セクション ビットマップを作成し、構築済みにアタッチします。`CImage`オブジェクトです。|  
|[CImage::CreateEx](#createex)|(追加のパラメーター) の DIB セクション ビットマップを作成し、構築済みにアタッチします。`CImage`オブジェクトです。|  
|[CImage::Destroy](#destroy)|ビットマップからのデタッチ、`CImage`オブジェクトし、ビットマップを破棄します。|  
|[CImage::Detach](#detach)|ビットマップからのデタッチ、`CImage`オブジェクトです。|  
|[:Draw](#draw)|コピー先の四角形に、元の四角形からビットマップをコピーします。 **描画**拡大または変換先の四角形の大きさに合わせて必要に応じて、ビットマップを圧縮し、アルファ ブレンドと透明色を処理します。|  
|[CImage::GetBits](#getbits)|ビットマップの実際のピクセル値へのポインターを取得します。|  
|[CImage::GetBPP](#getbpp)|ピクセルごとのビットを取得します。|  
|[CImage::GetColorTable](#getcolortable)|カラー テーブル内のエントリの範囲から、赤、緑、青 (RGB) の色の値を取得します。|  
|[CImage::GetDC](#getdc)|現在のビットマップが選択されているデバイス コンテキストを取得します。|  
|[CImage::GetExporterFilterString](#getexporterfilterstring)|使用可能なイメージ形式とその説明を検索します。|  
|[CImage::GetHeight](#getheight)|ピクセル単位で現在のイメージの高さを取得します。|  
|[CImage::GetImporterFilterString](#getimporterfilterstring)|使用可能なイメージ形式とその説明を検索します。|  
|[CImage::GetMaxColorTableEntries](#getmaxcolortableentries)|カラー テーブル内のエントリの最大数を取得します。|  
|[CImage::GetPitch](#getpitch)|バイト単位で、現在のイメージの音の高さを取得します。|  
|[CImage::GetPixel](#getpixel)|指定されたピクセルの色を取得*x*と*y*します。|  
|[CImage::GetPixelAddress](#getpixeladdress)|特定のピクセルのアドレスを取得します。|  
|[CImage::GetTransparentColor](#gettransparentcolor)|透明色のカラー テーブル内の位置を取得します。|  
|[CImage::GetWidth](#getwidth)|ピクセル単位で現在のイメージの幅を取得します。|  
|[CImage::IsDIBSection](#isdibsection)|割り当てられているビットマップが DIB セクションであるかどうかを判断します。|  
|[CImage::IsIndexed](#isindexed)|インデックス付きのパレットにビットマップの色がマップされていることを示します。|  
|[CImage::IsNull](#isnull)|元のビットマップが現在読み込まれているかどうかを示します。|  
|[CImage::IsTransparencySupported](#istransparencysupported)|アプリケーションが透明なビットマップをサポートし、Windows 2000 またはそれ以降にコンパイルされたかどうかを示します。|  
|[CImage::Load](#load)|指定したファイルからイメージを読み込みます。|  
|[CImage::LoadFromResource](#loadfromresource)|指定したリソースからイメージを読み込みます。|  
|[CImage::MaskBlt](#maskblt)|指定したマスクとラスター オペレーションを使用する元とコピー先のビットマップの色のデータを結合します。|  
|[CImage::PlgBlt](#plgblt)|転送元デバイス コンテキスト内の四角形からコピー先デバイス コンテキストで指定した平行四辺形にビット ブロック転送を実行します。|  
|[CImage::ReleaseDC](#releasedc)|取得したデバイス コンテキストを解放[CImage::GetDC](#getdc)します。|  
|[CImage::ReleaseGDIPlus](#releasegdiplus)|GDI + で使用されているリソースを解放します。 グローバル カタログ サーバーによって作成された無償のリソースを呼び出す必要があります`CImage`オブジェクトです。|  
|[CImage::Save](#save)|指定した型と、イメージを保存します。 **保存**イメージのオプションを指定することはできません。|  
|[CImage::SetColorTable](#setcolortable)|赤、緑、青の RGB の設定) DIB セクションのカラー テーブル内のエントリの範囲の値の色します。|  
|[CImage::SetPixel](#setpixel)|指定した色の指定した座標にあるピクセルに設定します。|  
|[CImage::SetPixelIndexed](#setpixelindexed)|カラー パレットの指定したインデックス位置に指定した座標にあるピクセルに設定します。|  
|[CImage::SetPixelRGB](#setpixelrgb)|指定された赤、緑、青 (RGB) の値の指定した座標にあるピクセルに設定します。|  
|[CImage::SetTransparentColor](#settransparentcolor)|透明色として扱われ、色のインデックスを設定します。 パレットの&1; つだけの色を透明になることができます。|  
|[CImage::StretchBlt](#stretchblt)|先の四角形を拡大または変換先の四角形の寸法に合わせてビットマップを圧縮すると、必要な場合に、元の四角形からビットマップをコピーします。|  
|[CImage::TransparentBlt](#transparentblt)|現在のデバイス コンテキストを元デバイス コンテキストからの透明色を持つビットマップをコピーします。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CImage::operator HBITMAP](#operator_hbitmap)|接続されている Windows ハンドルを返す、`CImage`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 `CImage`ありません。 またはデバイスに依存しないビットマップ (DIB) のセクションではどちらになっているビットマップは、します。ただし、使用することができます[作成](#create)または[CImage::Load](#load) DIB セクションのみを使用します。 非 DIB セクション ビットマップを割り当てることができます、`CImage`オブジェクトを使用して[アタッチ](#attach)、以下を使用することはできませんが、 `CImage` DIB セクション ビットマップだけをサポートするメソッドで。  
  
- [GetBits](#getbits)  
  
- [GetColorTable](#getcolortable)  
  
- [GetMaxColorTableEntries](#getmaxcolortableentries)  
  
- [GetPitch](#getpitch)  
  
- [GetPixelAddress](#getpixeladdress)  
  
- [IsIndexed](#isindexed)  
  
- [SetColorTable](#setcolortable)  
  
 割り当てられているビットマップが DIB セクションを確認するには、呼び出す[IsDibSection](#isdibsection)**します。**  
  
> [!NOTE]
> **注**Visual Studio .NET 2003 で、このクラスは、数のカウントを保持`CImage`オブジェクトを作成します。 カウントが 0 になったときに**オブジェクト**は GDI + で使用されるリソースを解放する自動的に呼び出されます。 これにより、いずれかの`CImage`Dll によって直接的または間接的に作成されたオブジェクトが正しく破棄される常に、**オブジェクト**からは呼び出されません`DllMain`します。  
  
> [!NOTE]
>  グローバル`CImage`DLL 内のオブジェクトはお勧めしません。 グローバル カタログ サーバーを使用する必要がある場合`CImage`呼び出し、DLL 内のオブジェクト[CImage::ReleaseGDIPlus](#releasegdiplus)を明示的に GDI + で使用されているリソースを解放します。  
  
 `CImage`新しい選択できない[CDC](../../mfc/reference/cdc-class.md)します。 `CImage`独自に作成**HDC**イメージにします。 `HBITMAP`いずれかにのみ選択可能**HDC** 、時に、`HBITMAP`に関連付けられている、`CImage`別に選択することはできません**HDC**します。 必要がある場合、 `CDC`、取得、 **HDC**から、`CImage`し [CDC::FromHandle] (../../mfc/reference/cdc-class.md#cdc__fromhandle します。  
  
## <a name="example"></a>例  
```cpp  
// Get a CDC for the image
CDC* pDC = CDC::FromHandle(m_myImage.GetDC());

// Use pDC here
pDC->Rectangle(0, 40, 100, 50);
m_myImage.ReleaseDC();
```  
  
 使用すると`CImage`MFC プロジェクトで、プロジェクトのメンバー関数へのポインターの期待に注意してください、 [CBitmap](../../mfc/reference/cbitmap-class.md)オブジェクトです。 使用する場合`CImage`でこのような関数の場合のような[CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu)を使用して[CBitmap::FromHandle](../../mfc/reference/cbitmap-class.md#fromhandle)、渡すこと、 `CImage` `HBITMAP`、して返された`CBitmap*`です。  

  
## <a name="example"></a>例  
```cpp  
void CMyDlg::OnRButtonDown(UINT nFlags, CPoint point)
{
  UNREFERENCED_PARAMETER(nFlags);

  CBitmap* pBitmap = CBitmap::FromHandle(m_myImage);
  m_pmenuPop->AppendMenu(0, ID_BMPCOMMAND, pBitmap);
  ClientToScreen(&point);
  m_pmenuPop->TrackPopupMenu(TPM_RIGHTBUTTON | TPM_LEFTALIGN, point.x, 
  point.y, this);
}
```  

  
 を通じて`CImage`、DIB セクションの実際のビットへのアクセス権があります。 使用することができます、 `CImage` Win32 HBITMAP または DIB のセクションを使用していたオブジェクトの任意の場所。  
  
> [!NOTE]
>  次`CImage`方法、使用に関する制限があります。  
  
|メソッド|制限|  
|------------|----------------|  
|[PlgBlt](#plgblt)|Windows NT 4.0 のみおよびそれ以降は動作します。 Windows 95/98 以降が実行されるアプリケーションでは機能しません。|  
|[MaskBlt](#maskblt)|Windows NT 4.0 のみおよびそれ以降は動作します。 Windows 95/98 以降が実行されるアプリケーションでは機能しません。|  
|[AlphaBlend](#alphablend)|Windows 2000、Windows 98、およびそれ以降のシステムで機能します。|  
|[TransparentBlt](#transparentblt)|Windows 2000、Windows 98、およびそれ以降のシステムで機能します。|  
|[描画](#draw)|Windows 2000、Windows 98、およびそれ以降のシステムの透過性をサポートしています。|  
  
 使用する`CImage`MFC または ATL のいずれかから  
  
> [!NOTE]
>  使用してプロジェクトを作成すると`CImage`を定義する必要があります`CString`インクルードする前に`atlimage.h`します。 プロジェクトでは、MFC を使わない ATL を使用する場合は含める`atlstr.h`インクルードする前に`atlimage.h`します。 プロジェクトでは、MFC (MFC サポートを ATL プロジェクトのかどうか) を使用する場合は含める`afxstr.h`インクルードする前に`atlimage.h`します。  
>   
>  同様に、含める必要があります`atlimage.h`インクルードする前に`atlimpl.cpp`します。 これを実現する簡単に含める`atlimage.h`で、`stdafx.h`です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlimage.h  
  
##  <a name="alphablend"></a>CImage::AlphaBlend  
 透明または半透明ピクセルのビットマップを表示します。  
  
```
BOOL AlphaBlend(
 HDC hDestDC,
 int xDest,
 int yDest,
 BYTE bSrcAlpha = 0xff,
 BYTE bBlendOp = AC_SRC_OVER) const throw();

BOOL AlphaBlend(
 HDC hDestDC,
 const POINT& pointDest,
 BYTE bSrcAlpha = 0xff,
 BYTE bBlendOp = AC_SRC_OVER) const throw();

BOOL AlphaBlend(
 HDC hDestDC,
 int xDest,
 int yDest,
 int nDestWidth,
 int nDestHeight,
 int xSrc,
 int ySrc,
 int nSrcWidth,
 int nSrcHeight,
 BYTE bSrcAlpha = 0xff,
 BYTE bBlendOp = AC_SRC_OVER);

BOOL AlphaBlend(
 HDC hDestDC,
 const RECT& rectDest,
 const RECT& rectSrc,
 BYTE bSrcAlpha = 0xff,
 BYTE bBlendOp = AC_SRC_OVER);
```  
  
### <a name="parameters"></a>パラメーター  
 `hDestDC`  
 コピー先デバイス コンテキストへのハンドルします。  
  
 `xDest`  
 X 座標、コピー先の四角形の左上隅の論理単位です。  
  
 `yDest`  
 Y 座標、コピー先の四角形の左上隅の論理単位です。  
  
 *bSrcAlpha*  
 元のビットマップ全体で使用するアルファ透明度値。 既定値 0 xff (255) には、イメージが不透明であると、ピクセルごとのアルファ値のみを使用することが想定しています。  
  
 `bBlendOp`  
 ソースとコピー先ビットマップ、ソース全体のビットマップ、および元のビットマップの書式情報に適用されるグローバルなアルファ値のアルファ ブレンド関数。 送信元と送信先の blend 関数は、現時点**ビットマップ**します。  
  
 `pointDest`  
 参照、[ポイント](http://msdn.microsoft.com/library/windows/desktop/dd162805)論理単位で、移行先の四角形の左上隅を識別する構造体。  
  
 `nDestWidth`  
 論理ユニットは、コピー先の四角形の幅。  
  
 `nDestHeight`  
 論理ユニットは、コピー先の四角形の高さ。  
  
 `xSrc`  
 元の四角形の左上隅の論理 x 座標。  
  
 `ySrc`  
 元の四角形の左上隅の論理 y 座標。  
  
 `nSrcWidth`  
 論理ユニットは、元の四角形の幅。  
  
 `nSrcHeight`  
 論理ユニットは、元の四角形の高さ。  
  
 `rectDest`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体、送信先を識別します。  
  
 `rectSrc`  
 参照、`RECT`構造のソースを特定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 アルファ ブレンド ビットマップの色が、ピクセル単位でブレンドをサポートしています。  
  
 `bBlendOp`の既定値に設定されている**ビットマップ**、ソース ピクセルのアルファ値に基づいて、コピー先ビットマップにコピー元のビットマップを配置します。  

##  <a name="attach"></a>CImage::Attach  
 アタッチ`hBitmap`に、`CImage`オブジェクトです。  
  
```
void Attach(HBITMAP hBitmap, DIBOrientation eOrientation = DIBOR_DEFAULT) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hBitmap`  
 ハンドル、`HBITMAP`です。  
  
 *eOrientation*  
 ビットマップの向きを指定します。 次のいずれかの値を指定します。  
  
- **DIBOR_DEFAULT**ビットマップの向きは、オペレーティング システムによって決定されます。 ただし、このことはできません常に想定される結果をすべてのオペレーティング システム。 これに関する詳細については、次のサポート技術情報記事を参照してください ( **Q186586**): [prb]: 概念常に返します正高さの DIB セクションです。  
  
- **DIBOR_BOTTOMUP**ビットマップの行は逆の順序で。 これにより、 [CImage::GetBits](#getbits)ビットマップ バッファーの末尾付近のポインターを返すと[CImage::GetPitch](#getpitch)負の数を取得します。  
  
- **DIBOR_TOPDOWN**上下からに、ビットマップの行ができます。 これにより、 [CImage::GetBits](#getbits)をビットマップ バッファーの最初のバイトへのポインターを返すと[CImage::GetPitch](#getpitch)正の数を取得します。  
  
### <a name="remarks"></a>コメント  
 ビットマップには、非 DIB セクション ビットマップまたは DIB セクション ビットマップのいずれかを指定できます。 参照してください[IsDIBSection](#isdibsection) DIB でのみ使用できるメソッドの一覧については、ビットマップをセクションです。  
  
##  <a name="bitblt"></a>CImage::BitBlt  
 コピー元デバイス コンテキストから現在のデバイス コンテキストにビットマップをコピーします。  
  
```
BOOL BitBlt(
 HDC hDestDC,
 int xDest,
 int yDest,
 DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
 HDC hDestDC,
 const POINT& pointDest,
 DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
 HDC hDestDC,
 int xDest,
 int yDest,
 int nDestWidth,
 int nDestHeight,
 int xSrc,
 int ySrc,
 DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
 HDC hDestDC,
 const RECT& rectDest,
 const POINT& pointSrc,
 DWORD dwROP = SRCCOPY) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hDestDC`  
 宛先**HDC**します。  
  
 `xDest`  
 コピー先の四角形の左上隅の論理 x 座標。  
  
 `yDest`  
 コピー先の四角形の左上隅の論理 y 座標。  
  
 `dwROP`  
 実行するラスター オペレーションです。 ラスター オペレーション コードは、変換先を形成する、ソース、変換先、およびパターンのビットで定義された、現在選択されているブラシ) を組み合わせる方法を定義します。 参照してください[BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370)で、[!INCLUDE[winSDK](./includes/winsdk_md.md)]の他のラスター オペレーション コードとその説明の一覧です。  
  
 `pointDest`  
 A[ポイント](http://msdn.microsoft.com/library/windows/desktop/dd162805)コピー先の四角形の左上隅を示す構造体。  
  
 `nDestWidth`  
 論理ユニットは、コピー先の四角形の幅。  
  
 `nDestHeight`  
 論理ユニットは、コピー先の四角形の高さ。  
  
 `xSrc`  
 元の四角形の左上隅の論理 x 座標。  
  
 `ySrc`  
 元の四角形の左上隅の論理 y 座標。  
  
 `rectDest`  
 A [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)コピー先の四角形を示す構造体。  
  
 `pointSrc`  
 A**ポイント**元の四角形の左上隅を示す構造体。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370)で、[!INCLUDE[winSDK](./includes/winsdk_md.md)]です。  
  
##  <a name="cimage"></a>CImage::CImage  
 `CImage` オブジェクトを構築します。  
  
```
CImage() throw();
```  
  
### <a name="remarks"></a>コメント  
 オブジェクトを作成した後で呼び出す[作成](#create)、[ロード](#load)、 [LoadFromResource](#loadfromresource)、または[アタッチ](#attach)ビットマップをオブジェクトにアタッチします。  
  
 **注**Visual Studio では、このクラスは、数のカウントを保持`CImage`オブジェクトを作成します。 カウントが 0 になったときに**オブジェクト**は GDI + で使用されるリソースを解放する自動的に呼び出されます。 これにより、いずれかの`CImage`Dll によって直接的または間接的に作成されたオブジェクトが正しく破棄される常に、**オブジェクト**DllMain からは呼び出されません。  
  
 グローバル`CImage`DLL 内のオブジェクトはお勧めしません。 グローバル カタログ サーバーを使用する必要がある場合`CImage`呼び出し、DLL 内のオブジェクト[CImage::ReleaseGDIPlus](#releasegdiplus)を明示的に GDI + で使用されているリソースを解放します。  
  
##  <a name="create"></a>CImage::Create  
 作成、`CImage`ビットマップし、構築済みにアタッチ`CImage`オブジェクトです。  
  
```
BOOL Create(
 int nWidth,
 int nHeight,
 int nBPP,
 DWORD dwFlags = 0) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nWidth`  
 幅、`CImage`ピクセルのビットマップです。  
  
 `nHeight`  
 高さ、`CImage`ピクセルのビットマップです。 場合`nHeight`が正の場合、ビットマップはボトムアップ DIB と原点は左下隅です。 場合`nHeight`は負の場合、ビットマップはトップダウンの DIB を起点と左上隅です。  
  
 `nBPP`  
 ビットマップのピクセルごとのビット数が表示されます。 通常、4、8、16、24、または 32 です。 モノクロ ビットマップやマスクの 1 にすることができます。  
  
 `dwFlags`  
 Bitmap オブジェクトがアルファ チャネル構成を指定します。 次の値の&0; 個以上の組み合わせになります。  
  
- **createAlphaChannel**場合にのみ使用できます`nBPP`32、および`eCompression`は**値**です。 指定した場合、(英数字以外の 32 ビット イメージで使用されていない) の各ピクセルの第 4 バイトに格納されている、各ピクセルのアルファ (透明度) 値を作成したイメージがあります。 呼び出すときに自動的に、このアルファ チャネルが使用[CImage::AlphaBlend](#alphablend)します。  
  
> [!NOTE]
>  呼び出しで[:draw](#draw)、アルファ チャネルを持つイメージは自動的にアルファ、変換先にブレンドします。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="createex"></a>CImage::CreateEx  
 作成、`CImage`ビットマップし、構築済みにアタッチ`CImage`オブジェクトです。  
  
```
BOOL CreateEx(
 int nWidth,
 int nHeight,
 int nBPP,
 DWORD eCompression,
 const DWORD* pdwBitmasks = NULL,
 DWORD dwFlags = 0) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nWidth`  
 幅、`CImage`ピクセルのビットマップです。  
  
 `nHeight`  
 高さ、`CImage`ピクセルのビットマップです。 場合`nHeight`が正の場合、ビットマップはボトムアップ DIB と原点は左下隅です。 場合`nHeight`は負の場合、ビットマップはトップダウンの DIB を起点と左上隅です。  
  
 `nBPP`  
 ビットマップのピクセルごとのビット数が表示されます。 通常、4、8、16、24、または 32 です。 モノクロ ビットマップやマスクの 1 にすることができます。  
  
 `eCompression`  
 (上から下の Dib を圧縮することはできません)、圧縮されたボトムアップのビットマップの圧縮の種類を指定します。 次のいずれかの値になります。  
  
- **値**形式は圧縮されていません。 呼び出すときに、この値を指定する`CImage::CreateEx`は呼び出すことと同じ`CImage::Create`します。  
  
- **BI_BITFIELDS**形式は圧縮されていないと、カラー テーブルから成る&3;`DWORD`赤を指定するカラー マスクを選択し、緑、青のコンポーネントがそれぞれ、各ピクセルのです。 これは、16、32 bpp のビットマップを使用すると有効です。  
  
 *pdwBitfields*  
 場合にのみ使用`eCompression`に設定されている**BI_BITFIELDS**、それ以外の場合があります**NULL**します。 3 つの配列へのポインター`DWORD`のどのビットごとのピクセルは、赤の使用を指定するビットマスクが緑、および青の色のコンポーネントがそれぞれします。 ビット フィールドの制限については、次を参照してください。 [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376)で、[!INCLUDE[winSDK](./includes/winsdk_md.md)]です。  
  
 `dwFlags`  
 Bitmap オブジェクトがアルファ チャネル構成を指定します。 次の値の&0; 個以上の組み合わせになります。  
  
- **createAlphaChannel**場合にのみ使用できます`nBPP`32、および`eCompression`は**値**です。 指定した場合、(英数字以外の 32 ビット イメージで使用されていない) の各ピクセルの第 4 バイトに格納されている、各ピクセルのアルファ (透明度) 値を作成したイメージがあります。 呼び出すときに自動的に、このアルファ チャネルが使用[CImage::AlphaBlend](#alphablend)します。  
  
    > [!NOTE]
    >  呼び出しで[:draw](#draw)、アルファ チャネルを持つイメージは自動的にアルファ、変換先にブレンドします。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**正常終了した場合。 それ以外の場合**FALSE**します。  
  
### <a name="example"></a>例  
 次の例では、ピクセルごとに 16 ビットを使用して、100 x 100 ピクセルのビットマップを作成します。 指定した 16 ビットのピクセル ビット 0 ~ 3 は赤の要素をエンコード、4 ~ 7 ビット エンコード緑、および 8 ~ 11 ビットは青をエンコードします。 残りの 4 ビットは、使用されません。  

```cpp  
DWORD adwBitmasks[3] = { 0x0000000f, 0x000000f0, 0x00000f00 };
m_myImage.CreateEx(100, 100, 16, BI_BITFIELDS, adwBitmasks, 0);
```


##  <a name="destroy"></a>CImage::Destroy  
 ビットマップからのデタッチ、`CImage`オブジェクトし、ビットマップを破棄します。  
  
```
void Destroy() throw();
```  
  
##  <a name="detach"></a>CImage::Detach  
 ビットマップからのデタッチ、`CImage`オブジェクトです。  
  
```
HBITMAP Detach() throw();
```  
  
### <a name="return-value"></a>戻り値  
 デタッチするには、ビットマップを識別するハンドルまたは**NULL**ビットマップがアタッチされていない場合。  
  
##  <a name="draw"></a>:Draw  
 コピー元デバイス コンテキストから現在のデバイス コンテキストにビットマップをコピーします。  
  
```
BOOL Draw(
 HDC hDestDC,
 int xDest,
 int yDest,
 int nDestWidth,
 int nDestHeight,
 int xSrc,
 int ySrc,
 int nSrcWidth,
 int nSrcHeight) const throw();

BOOL Draw(
 HDC hDestDC,
 const RECT& rectDest,
 const RECT& rectSrc) const throw();

BOOL Draw(
 HDC hDestDC,
 int xDest,
 int yDest) const throw();

BOOL Draw(
 HDC hDestDC,
 const POINT& pointDest) const throw();

BOOL Draw(
 HDC hDestDC,
 int xDest,
 int yDest,
 int nDestWidth,
 int nDestHeight) const throw();

BOOL Draw(
 HDC hDestDC,
 const RECT& rectDest) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hDestDC`  
 コピー先デバイス コンテキストへのハンドル。  
  
 `xDest`  
 X 座標、コピー先の四角形の左上隅の論理単位です。  
  
 `yDest`  
 Y 座標、コピー先の四角形の左上隅の論理単位です。  
  
 `nDestWidth`  
 論理ユニットは、コピー先の四角形の幅。  
  
 `nDestHeight`  
 論理ユニットは、コピー先の四角形の高さ。  
  
 `xSrc`  
 X 座標、元の四角形の左上隅の論理単位です。  
  
 `ySrc`  
 Y 座標、元の四角形の左上隅の論理単位です。  
  
 `nSrcWidth`  
 論理ユニットは、元の四角形の幅。  
  
 `nSrcHeight`  
 論理ユニットは、元の四角形の高さ。  
  
 `rectDest`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体、送信先を識別します。  
  
 `rectSrc`  
 参照、`RECT`構造のソースを特定します。  
  
 `pointDest`  
 参照、[ポイント](http://msdn.microsoft.com/library/windows/desktop/dd162805)論理単位で、移行先の四角形の左上隅を識別する構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 **描画**と同じ操作を実行[StretchBlt](#stretchblt)透明色またはアルファ チャネルにイメージが含まれていない場合、します。 その場合は、**描画**いずれかと同じ操作を実行[TransparentBlt](#transparentblt)または[AlphaBlend](#alphablend)必須とします。  
  
 バージョンの**描画**元の四角形を指定しない、ソース イメージ全体が既定値です。 バージョンの**描画**先の四角形のサイズを指定しませんが、ソース イメージのサイズは、既定または縮小が行われます。  
  
##  <a name="getbits"></a>CImage::GetBits  
 ビットマップのピクセルの実際のビット値へのポインターを取得します。  
  
```
void* GetBits() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ビットマップ バッファーへのポインター。 ビットマップがボトムアップ DIB の場合は、ポインターは、バッファーの最後に記載します。 ビットマップがトップダウン DIB の場合、ポインターは、バッファーの最初のバイトを指します。  
  
### <a name="remarks"></a>コメント  
 によって返される値と共にこのポインターを使用して[GetPitch](#getpitch)を検索して、イメージ内の個々 のピクセルを変更します。  
  
> [!NOTE]
>  このメソッドは、DIB セクション ビットマップだけをサポートしています。その結果のピクセルにアクセスする、 `CImage` DIB セクションのピクセルのと同様のオブジェクトします。 返されたポインターが指す位置 (0, 0)、ピクセルです。  
  
##  <a name="getbpp"></a>CImage::GetBPP  
 ビット/ピクセル値を取得します。  
  
```
int GetBPP() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 ビット/ピクセルの数。  
  
### <a name="remarks"></a>コメント  
 この値は、各ピクセルを定義するビット数と、ビットマップの色の最大数を決定します。  
  
 1、4、8、16、24、または 32 ビット/ピクセルは通常です。 参照してください、 **biBitCount**のメンバー [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376)で、[!INCLUDE[winSDK](./includes/winsdk_md.md)]の詳細については、この値にします。  
  
##  <a name="getcolortable"></a>CImage::GetColorTable  
 DIB セクションのパレット内のエントリの範囲から、赤、緑、青 (RGB) の色の値を取得します。  
  
```
void GetColorTable(UINT iFirstColor,
 UINT nColors,
 RGBQUAD* prgbColors) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `iFirstColor`  
 取得する最初のエントリのカラー テーブルのインデックス。  
  
 `nColors`  
 取得するカラー テーブル エントリの数。  
  
 `prgbColors`  
 配列へのポインター [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938)構造体の色を取得するテーブルのエントリ。  
  
##  <a name="getdc"></a>CImage::GetDC  
 現在選択されているイメージを持っているデバイス コンテキストを取得します。  
  
```
HDC GetDC() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 デバイス コンテキストを識別するハンドル。  
  
### <a name="remarks"></a>コメント  
 呼び出しごとに`GetDC`、後続の呼び出しにする必要があります[ReleaseDC](#releasedc)します。  
  
##  <a name="getexporterfilterstring"></a>CImage::GetExporterFilterString  
 イメージを保存するためには、使用可能なイメージ形式を検索します。  
  
```
static HRESULT GetExporterFilterString(CSimpleString& strExporters,
 CSimpleArray<GUID>& aguidFileTypes,
 LPCTSTR pszAllFilesDescription = NULL,
 DWORD dwExclude = excludeDefaultSave,
 TCHAR chSeparator = _T('|'));
```  
  
### <a name="parameters"></a>パラメーター  
 *strExporters*  
 参照、 **CSimpleString**オブジェクトです。 参照してください**解説**の詳細。  
  
 `aguidFileTypes`  
 文字列内のファイルの種類のいずれかに対応する各要素に、Guid の配列。 例では`pszAllFilesDescription`下`aguidFileTypes`[0] は`GUID_NULL`残りの配列値は、現在のオペレーティング システムでサポートされているイメージ ファイル形式とします。  
  
> [!NOTE]
>  定数の一覧については、次を参照してください。**イメージ ファイル形式の定数**で、[!INCLUDE[winSDK](./includes/winsdk_md.md)]です。  
  
 `pszAllFilesDescription`  
 このパラメーターがない場合**NULL**、フィルター文字列では、一覧の先頭に追加の&1; つのフィルターができます。 このフィルターは、現在の値が`pszAllFilesDescription`その説明の一覧で、その他のエクスポーターでサポートされている任意の拡張子のファイルを受け入れるとします。  
  
 例:  

```cpp  
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any exporter.
CImage::GetExporterFilterString(
    strExporters, aguidFileTypes, 
 _T("All Image Files"));
```  

  
 `dwExclude`  
 一覧から除外するファイルの種類を指定するビット フラグのセット。 指定できるフラグは次のとおりです。  
  
- **excludeGIF** = 0x01 除外 GIF ファイルです。  
  
- **excludeBMP** = 0x02 除外 BMP (Windows ビットマップ) ファイルです。  
  
- **excludeEMF** = 0x04 除外 EMF (拡張メタファイル) ファイルです。  
  
- **excludeWMF** = 0x08 除外 WMF (Windows のメタファイル) ファイルです。  
  
- **excludeJPEG** = 0x10 除外 JPEG ファイルです。  
  
- **excludePNG** = 0x20 除外 PNG ファイルです。  
  
- **excludeTIFF** = 0x40 除外 TIFF ファイルです。  
  
- **excludeIcon** = 0x80 除外 ICO (Windows のアイコン) ファイルです。  
  
- **excludeOther** = 0x80000000 が上記以外の他のファイル種類を除外します。  
  
- **excludeDefaultLoad** = 0 の種類は、既定で含まれるすべてのファイルの負荷を  
  
- **excludeDefaultSave** = **excludeIcon | excludeEMF | excludeWMF**特別な要件があるために、これらのファイルを既定で除外するよう、保存するためです。  
  
 `chSeparator`  
 イメージ形式の間で使用される区切り記号。 参照してください**解説**の詳細。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
### <a name="remarks"></a>コメント  
 Mfc は、結果の書式指定文字列を渡すことができます[CFileDialog](../../mfc/reference/cfiledialog-class.md)ファイル名を付けて保存 ダイアログ ボックスで使用可能なイメージ ファイルの拡張機能を公開するオブジェクトの書式します。  
  
 パラメーター *strExporter*形式があります。  
  
 ファイルの description0 |\*.ext0 | filedescription1 |\*.ext1 |. ファイルの説明*n*|\*します。ext *n*||  
  
 ここで ' |' で指定された区切り記号`chSeparator`します。 例:  
  
 `"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`  
  
 既定の区切り記号を使用して ' |' MFC にこの文字列を渡す場合`CFileDialog`オブジェクトです。 一般的な名前を付けて保存 ダイアログ ボックスにこの文字列を渡す場合は、null の区切り記号 '\0' を使用します。  
  
##  <a name="getheight"></a>CImage::GetHeight  
 イメージのピクセルの高さを取得します。  
  
```
int GetHeight() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 イメージのピクセル単位の高さ。  
  
##  <a name="getimporterfilterstring"></a>CImage::GetImporterFilterString  
 イメージの読み込みに使用できるイメージ形式を検索します。  
  
```
static HRESULT GetImporterFilterString(CSimpleString& strImporters,
 CSimpleArray<GUID>& aguidFileTypes,
 LPCTSTR pszAllFilesDescription = NULL,
 DWORD dwExclude = excludeDefaultLoad,
 TCHAR chSeparator = _T('|'));
```  
  
### <a name="parameters"></a>パラメーター  
 *strImporters*  
 参照、 **CSimpleString**オブジェクトです。 参照してください**解説**の詳細。  
  
 `aguidFileTypes`  
 文字列内のファイルの種類のいずれかに対応する各要素に、Guid の配列。 例では`pszAllFilesDescription`下`aguidFileTypes`[0] は`GUID_NULL`残りの配列を含む値は、現在のオペレーティング システムでサポートされているイメージ ファイル形式です。  
  
> [!NOTE]
>  定数の一覧については、次を参照してください。**イメージ ファイル形式の定数**で、[!INCLUDE[winSDK](./includes/winsdk_md.md)]です。  
  
 `pszAllFilesDescription`  
 このパラメーターがない場合**NULL**、フィルター文字列では、一覧の先頭に追加の&1; つのフィルターができます。 このフィルターは、現在の値が`pszAllFilesDescription`その説明の一覧で、その他のエクスポーターでサポートされている任意の拡張子のファイルを受け入れるとします。  
  
 例:  

```cpp  
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any importer.
CImage::GetImporterFilterString(
    strImporters, aguidFileTypes, 
 _T("All Image Files"));
```  

  
 `dwExclude`  
 一覧から除外するファイルの種類を指定するビット フラグのセット。 指定できるフラグは次のとおりです。  
  
- **excludeGIF** = 0x01 除外 GIF ファイルです。  
  
- **excludeBMP** = 0x02 除外 BMP (Windows ビットマップ) ファイルです。  
  
- **excludeEMF** = 0x04 除外 EMF (拡張メタファイル) ファイルです。  
  
- **excludeWMF** = 0x08 除外 WMF (Windows のメタファイル) ファイルです。  
  
- **excludeJPEG** = 0x10 除外 JPEG ファイルです。  
  
- **excludePNG** = 0x20 除外 PNG ファイルです。  
  
- **excludeTIFF** = 0x40 除外 TIFF ファイルです。  
  
- **excludeIcon** = 0x80 除外 ICO (Windows のアイコン) ファイルです。  
  
- **excludeOther** = 0x80000000 が上記以外の他のファイル種類を除外します。  
  
- **excludeDefaultLoad** = 0 の種類は、既定で含まれるすべてのファイルの負荷を  
  
- **excludeDefaultSave** = **excludeIcon | excludeEMF | excludeWMF**特別な要件があるために、これらのファイルを既定で除外するよう、保存するためです。  
  
 `chSeparator`  
 イメージ形式の間で使用される区切り記号。 参照してください**解説**の詳細。  
  
### <a name="remarks"></a>コメント  
 Mfc は、結果の書式指定文字列を渡すことができます[CFileDialog](../../mfc/reference/cfiledialog-class.md)で使用可能なイメージ ファイルの拡張機能を公開するオブジェクトの書式、**ファイルを開く** ダイアログ ボックス。  
  
 パラメーター *strImporter*形式があります。  
  
 ファイルの description0 |\*.ext0 | filedescription1 |\*.ext1 |. ファイルの説明*n*|\*します。ext *n*||  
  
 ここで ' |' で指定された区切り記号`chSeparator`します。 例:  
  
 `"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`  
  
 既定の区切り記号を使用して ' |' MFC にこの文字列を渡す場合`CFileDialog`オブジェクトです。 共通にこの文字列を渡す場合は、null の区切り記号 '\0' を使用して**ファイルを開く** ダイアログ ボックス。  
  
##  <a name="getmaxcolortableentries"></a>CImage::GetMaxColorTableEntries  
 カラー テーブル内のエントリの最大数を取得します。  
  
```
int GetMaxColorTableEntries() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 カラー テーブル内のエントリの数。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、DIB セクション ビットマップだけをサポートします。  
  
##  <a name="getpitch"></a>CImage::GetPitch  
 イメージの高さを取得します。  
  
```
int GetPitch() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 イメージのピッチです。 戻り値が負の場合は、ビットマップはボトムアップの DIB を起点と左下隅です。 戻り値が正の場合は、ビットマップはトップダウン DIB と原点は左上隅です。  
  
### <a name="remarks"></a>コメント  
 音の高さは、2 つのメモリ アドレスを&1; つのビットマップの行の先頭を表すと次のビットマップ行の先頭の間のバイト単位の距離です。 声の高さは、バイト単位で測定されるため、イメージの声の高さでは、ピクセル形式を決定することができます。 声の高さには、ビットマップ用に予約の追加のメモリを含めることもできます。  
  
 使用`GetPitch`と[GetBits](#getbits)を個々 のピクセルの画像を検索します。  
  
> [!NOTE]
>  このメソッドは、DIB セクション ビットマップだけをサポートします。  
  
##  <a name="getpixel"></a>CImage::GetPixel  
 指定された位置にあるピクセルの色を取得*x*と*y*します。  
  
```
COLORREF GetPixel(int x,int y) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 ピクセルの x 座標。  
  
 *y*  
 ピクセルの y 座標。  
  
### <a name="return-value"></a>戻り値  
 赤、緑、青 (RGB) の値、ピクセル。 戻り値は、ピクセルが現在のクリップ領域の外部にある場合は、 **CLR_INVALID**します。  
  
##  <a name="getpixeladdress"></a>CImage::GetPixelAddress  
 ピクセルの正確なアドレスを取得します。  
  
```
void* GetPixelAddress(int x,int y) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 ピクセルの x 座標。  
  
 *y*  
 ピクセルの y 座標。  
  
### <a name="remarks"></a>コメント  
 アドレスは、ピクセルの座標、ビットマップ、およびピクセルごとのビットのピッチに従って決定されます。  
  
 ピクセルあたり 8 ビット未満のある形式の場合は、このメソッドは、ピクセルを含むバイトのアドレスを返します。 たとえば、イメージ形式は 4 ビット/ピクセル、`GetPixelAddress`を返します。 バイトごとの 2 ピクセルの最初のピクセルにすると、バイトのアドレスを計算する必要があります。  
  
> [!NOTE]
>  このメソッドは、DIB セクション ビットマップだけをサポートします。  
  
##  <a name="gettransparentcolor"></a>CImage::GetTransparentColor  
 透明色カラー パレット内の位置を示すインデックスを取得します。  
  
```
LONG GetTransparentColor() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 透明色のインデックス。  
  
##  <a name="getwidth"></a>CImage::GetWidth  
 イメージのピクセルの幅を取得します。  
  
```
int GetWidth() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 ピクセル単位で、ビットマップの幅。  
  
##  <a name="isdibsection"></a>CImage::IsDIBSection  
 割り当てられているビットマップが DIB セクションであるかどうかを判断します。  
  
```
bool IsDIBSection() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 **true**割り当てられているビットマップが DIB セクションである場合。 それ以外の場合**false**します。  
  
### <a name="remarks"></a>コメント  
 ビットマップは DIB のセクションではない場合は、以下を使用することはできません`CImage`メソッドで、DIB セクション ビットマップだけをサポートします。  
  
- [GetBits](#getbits)  
  
- [GetColorTable](#getcolortable)  
  
- [GetMaxColorTableEntries](#getmaxcolortableentries)  
  
- [GetPitch](#getpitch)  
  
- [GetPixelAddress](#getpixeladdress)  
  
- [IsIndexed](#isindexed)  
  
- [SetColorTable](#setcolortable)  
  
##  <a name="isindexed"></a>CImage::IsIndexed  
 ビットマップのピクセルがカラー パレットにマップするかどうかを決定します。  
  
```
bool IsIndexed() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 **true**インデックス以外の場合**false**します。  
  
### <a name="remarks"></a>コメント  
 このメソッドが戻る**true**ビットマップが 8 ビットである場合にのみ (256 色) 以内です。  
  
> [!NOTE]
>  このメソッドは、DIB セクション ビットマップだけをサポートします。  
  
##  <a name="isnull"></a>CImage::IsNull  
 ビットマップが現在読み込まれているかどうかを判断します。  
  
```
bool IsNull() const throw();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドが戻る**True**ビットマップ現在ない場合ロード以外の場合**False**します。  
  
##  <a name="istransparencysupported"></a>CImage::IsTransparencySupported  
 アプリケーションが透明なビットマップをサポートし、Windows 2000 またはそれ以降にコンパイルされたかどうかを示します。  
  
```
static BOOL IsTransparencySupported() throw();
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、現在のプラットフォームは、透過性をサポートしています。 それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 戻り値は&0; 以外の値、および透過性がサポートされている場合への呼び出し[AlphaBlend](#alphablend)、 [TransparentBlt](#transparentblt)、または[描画](#draw)透明色を処理します。  
  
 Windows 2000 または Windows 98 の前にオペレーティング システムで使用するアプリケーションをコンパイルすると、このメソッドは新しいオペレーティング システムであっても、0 を常に返します。  
  

##  <a name="load"></a>CImage::Load  
 イメージを読み込みます。  
  
```
HRESULT Load(LPCTSTR pszFileName) throw();
HRESULT Load(IStream* pStream) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszFileName`  
 読み込むイメージ ファイルの名前を含む文字列へのポインター。  
  
 `pStream`  
 読み込むイメージ ファイルの名前を格納しているストリームへのポインター。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
### <a name="remarks"></a>コメント  
 指定されたイメージを読み込み*pszFileName*または`pStream`です。  
  
 有効なイメージの種類は、BMP、GIF、JPEG、PNG、TIFF およびです。  
  
##  <a name="loadfromresource"></a>CImage::LoadFromResource  
 イメージを読み込み、`BITMAP`リソースです。  
  
```
void LoadFromResource(
 HINSTANCE hInstance,
 LPCTSTR pszResourceName) throw();

void LoadFromResource(
 HINSTANCE hInstance,
 UINT nIDResource) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hInstance`  
 読み込まれるイメージが含まれるモジュールのインスタンスへのハンドルします。  
  
 `pszResourceName`  
 読み込むイメージが含まれるリソースの名前を含む文字列へのポインター。  
  
 `nIDResource`  
 読み込むリソースの ID。  
  
### <a name="remarks"></a>コメント  
 リソースは、型でなければなりません`BITMAP`します。  
  
##  <a name="maskblt"></a>CImage::MaskBlt  
 指定したマスクとラスター オペレーションを使用する元とコピー先のビットマップの色のデータを結合します。  
  
```
BOOL MaskBlt(
 HDC hDestDC,
 int xDest,
 int yDest,
 int nDestWidth,
 int nDestHeight,
 int xSrc,
 int ySrc,
 HBITMAP hbmMask,
 int xMask,
 int yMask,
 DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
 HDC hDestDC,
 const RECT& rectDest,
 const POINT& pointSrc,
 HBITMAP hbmMask,
 const POINT& pointMask,
 DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
 HDC hDestDC,
 int xDest,
 int yDest,
 HBITMAP hbmMask,
 DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
 HDC hDestDC,
 const POINT& pointDest,
 HBITMAP hbmMask,
 DWORD dwROP = SRCCOPY) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hDestDC`  
 実行可能ファイルは、リソースを含むモジュールへのハンドル。  
  
 `xDest`  
 X 座標、コピー先の四角形の左上隅の論理単位です。  
  
 `yDest`  
 Y 座標、コピー先の四角形の左上隅の論理単位です。  
  
 `nDestWidth`  
 論理ユニットは、コピー先の四角形と元のビットマップの幅。  
  
 `nDestHeight`  
 論理ユニットは、コピー先の四角形と元のビットマップの高さ。  
  
 `xSrc`  
 元のビットマップの左上隅の論理 x 座標。  
  
 `ySrc`  
 元のビットマップの左上隅の論理 y 座標。  
  
 `hbmMask`  
 転送元デバイス コンテキストで、カラー ビットマップと組み合わせて、モノクロ マスク ビットマップへのハンドルします。  
  
 `xMask`  
 指定されたマスク ビットマップの水平方向のピクセルのオフセット、`hbmMask`パラメーター。  
  
 `yMask`  
 指定されたマスク ビットマップの垂直方向のピクセルのオフセット、`hbmMask`パラメーター。  
  
 `dwROP`  
 ソースおよび変換先データの組み合わせを制御するメソッドを使用する前景色と背景の両方の三項ラスター オペレーション コードを指定します。 バック グラウンドのラスター オペレーション コードは、この値には、この値の上位ワードの高位バイトで格納されます。フォア グラウンド ラスター オペレーション コードは、この値には、この値の上位ワードの下位バイトで格納されます。この値の下位ワードは無視され、0 にする必要があります。 前景色と背景がこのメソッドのコンテキストでの詳細については、次を参照してください。`MaskBlt`で、[!INCLUDE[winSDK](./includes/winsdk_md.md)]です。 共通のラスター オペレーション コードの一覧は、次を参照してください。`BitBlt`で、[!INCLUDE[winSDK](./includes/winsdk_md.md)]です。  
  
 `rectDest`  
 参照、`RECT`構造体、送信先を識別します。  
  
 `pointSrc`  
 A`POINT`元の四角形の左上隅を示す構造体。  
  
 `pointMask`  
 A**ポイント**マスク ビットマップの左上隅を示す構造体。  
  
 `pointDest`  
 参照、**ポイント**論理単位で、移行先の四角形の左上隅を識別する構造体。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、0 以外。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、Windows NT では、バージョン 4.0 以降のみに適用されます。  
  
##  <a name="operator_hbitmap"></a>CImage::operator HBITMAP  
 この演算子の接続されている Windows GDI ハンドルの取得を使用して、`CImage`オブジェクトです。 この演算子はキャスト演算子の`HBITMAP`オブジェクトです。  
  
##  <a name="plgblt"></a>CImage::PlgBlt  
 転送元デバイス コンテキスト内の四角形からコピー先デバイス コンテキストで指定した平行四辺形にビット ブロック転送を実行します。  
  
```
BOOL PlgBlt(
 HDC hDestDC,
 const POINT* pPoints,
 HBITMAP hbmMask = NULL) const throw();

BOOL PlgBlt(
 HDC hDestDC,
 const POINT* pPoints,
 int xSrc,
 int ySrc,
 int nSrcWidth,
 int nSrcHeight,
 HBITMAP hbmMask = NULL,
 int xMask = 0,
 int yMask = 0) const throw();

BOOL PlgBlt(
 HDC hDestDC,
 const POINT* pPoints,
 const RECT& rectSrc,
 HBITMAP hbmMask = NULL,
 const POINT& pointMask = CPoint(0, 0)) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hDestDC`  
 コピー先デバイス コンテキストへのハンドル。  
  
 *pPoints*  
 先の平行四辺形の&3; つの角を識別する論理空間内の次の&3; つの点の配列へのポインター。 元の四角形の左上隅は、この配列、配列内の&2; つ目のポイントを右上隅および&3; 番目のポイントを左下隅の最初の要素にマップされます。 元の四角形の右下隅は、暗黙の型の&4; 番目の点、平行四辺形内にマップされます。  
  
 `hbmMask`  
 元の四角形の色をマスクするために使用されるオプションのモノクロ ビットマップへのハンドル。  
  
 `xSrc`  
 X 座標、元の四角形の左上隅の論理単位です。  
  
 `ySrc`  
 Y 座標、元の四角形の左上隅の論理単位です。  
  
 `nSrcWidth`  
 論理ユニットは、元の四角形の幅。  
  
 `nSrcHeight`  
 論理ユニットは、元の四角形の高さ。  
  
 `xMask`  
 モノクロ ビットマップの左上隅の x 座標。  
  
 `yMask`  
 モノクロ ビットマップの左上隅の y 座標。  
  
 `rectSrc`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体の元の四角形の座標を指定します。  
  
 `pointMask`  
 A[ポイント](http://msdn.microsoft.com/library/windows/desktop/dd162805)マスク ビットマップの左上隅を示す構造体。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、0 以外。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 場合`hbmMask`モノクロ ビットマップが有効**PlgBit**元の四角形からの色データのビット マスクをこのビットマップを使用します。  
  
 このメソッドは、Windows NT では、バージョン 4.0 以降のみに適用されます。 参照してください[PlgBlt](http://msdn.microsoft.com/library/windows/desktop/dd162804)で、[!INCLUDE[winSDK](./includes/winsdk_md.md)]より詳細な情報です。  
  
##  <a name="releasedc"></a>CImage::ReleaseDC  
 デバイス コンテキストを解放します。  
  
```
void ReleaseDC() const throw();
```  
  
### <a name="remarks"></a>コメント  
 デバイス コンテキストに一度に選択する&1; つだけのビットマップを呼び出す必要があります`ReleaseDC`呼び出しごとに[GetDC](#getdc)します。  
  
##  <a name="releasegdiplus"></a>CImage::ReleaseGDIPlus  
 GDI + で使用されているリソースを解放します。  
  
```
void ReleaseGDIPlus() throw();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出すをグローバル カタログ サーバーによって割り当てられたリソースを解放する必要があります`CImage`オブジェクトです。 参照してください[CImage::CImage](#cimage)します。  
  
##  <a name="save"></a>CImage::Save  
 指定したストリームまたはファイルをディスクに画像を保存します。  
  
```
HRESULT Save(IStream* pStream,
 REFGUID guidFileType) const throw();

HRESULT Save(LPCTSTR pszFileName,
 REFGUID guidFileType= GUID_NULL) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pStream`  
 ファイルのイメージ データを含む COM IStream オブジェクトへのポインター。  
  
 *pszFileName*  
 イメージのファイル名へのポインター。  
  
 `guidFileType`  
 イメージを保存するファイルの種類。 次のいずれかの値を指定します。  
  
- **ImageFormatBMP**圧縮されていないビットマップ イメージです。  
  
- **ImageFormatPNG** A ポータブル ネットワーク グラフィックス (PNG) 圧縮されたイメージ。  
  
- **ImageFormatJPEG** A JPEG 圧縮されたイメージ。  
  
- **ImageFormatGIF** A GIF 圧縮されたイメージ。  
  
> [!NOTE]
>  定数の一覧については、次を参照してください。**イメージ ファイル形式の定数**で、[!INCLUDE[winSDK](./includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
### <a name="remarks"></a>コメント  
 指定した名前と型を使用してイメージを保存するには、この関数を呼び出します。 場合、`guidFileType`パラメーターが含まれていない、ファイル名のファイルの拡張機能を使用して、イメージ形式を決定します。 拡張機能が指定されていない場合、イメージが BMP 形式で保存されます。  
  
##  <a name="setcolortable"></a>CImage::SetColorTable  
 DIB セクションのパレットのエントリの範囲の赤、緑、青 (RGB) の色値を設定します。  
  
```
void SetColorTable(
  UINT iFirstColor, 
  UINT nColors,
  const RGBQUAD* prgbColors) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `iFirstColor`  
 設定する最初のエントリのカラー テーブルのインデックス。  
  
 `nColors`  
 設定するカラー テーブル エントリの数。  
  
 `prgbColors`  
 配列へのポインター [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938)テーブル エントリの色を設定する構造体。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、DIB セクション ビットマップだけをサポートします。  
  
##  <a name="setpixel"></a>CImage::SetPixel  
 ビットマップ内の指定の場所には、ピクセルの色を設定します。  
  
```
void SetPixel(int x, int y, COLORREF color) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 設定するピクセルの水平方向の位置。  
  
 *y*  
 設定するピクセルの垂直方向の位置。  
  
 `color`  
 ピクセルを設定する色。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ピクセルの座標が選択されているクリッピング領域の外にある場合に失敗します。  
  
##  <a name="setpixelindexed"></a>CImage::SetPixelIndexed  
 ある色ピクセルの色を設定`iIndex`カラー パレットにします。  
  
```
void SetPixelIndexed(int x, int y, int iIndex) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 設定するピクセルの水平方向の位置。  
  
 *y*  
 設定するピクセルの垂直方向の位置。  
  
 `iIndex`  
 カラー パレットの色のインデックス。  
  
##  <a name="setpixelrgb"></a>CImage::SetPixelRGB  
 によって指定された場所にあるピクセル設定*x*と*y*で示される色に*r*、 *g*、および*b*、赤、緑、青 (RGB) のイメージです。  
  
```
void SetPixelRGB(  
 int x,
 int y,
 BYTE r,
 BYTE g,
 BYTE b) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 設定するピクセルの水平方向の位置。  
  
 *y*  
 設定するピクセルの垂直方向の位置。  
  
 *r*  
 赤の色の彩度。  
  
 *g*  
 緑の色の彩度。  
  
 *b*  
 青の色の彩度。  
  
### <a name="remarks"></a>コメント  
 赤、緑、および青のパラメーターは、それぞれ 0 ~ 255 の数値で表されます。 すべての&3; つのパラメーターを&0; に設定した場合、色は黒です。 すべての 3 つのパラメーターを 255 に設定した場合、色は白です。  
  
##  <a name="settransparentcolor"></a>CImage::SetTransparentColor  
 透明色として指定したインデックス位置にある、色を設定します。  
  
```
LONG SetTransparentColor(LONG iTransparentColor) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *iTransparentColor*  
 透過色に設定する色のカラー パレット内のインデックス。 –&1;、色が設定されていない場合透過的なです。  
  
### <a name="return-value"></a>戻り値  
 以前、色のインデックスに透明として設定します。  
  
##  <a name="stretchblt"></a>CImage::StretchBlt  
 コピー元デバイス コンテキストから現在のデバイス コンテキストにビットマップをコピーします。  
  
```
BOOL StretchBlt(
 HDC hDestDC,
 int xDest,
 int yDest,
 int nDestWidth,
 int nDestHeight,
 DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
 HDC hDestDC,
 const RECT& rectDest,
 DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
 HDC hDestDC,
 int xDest,
 int yDest,
 int nDestWidth,
 int nDestHeight,
 int xSrc,
 int ySrc,
 int nSrcWidth,
 int nSrcHeight,
 DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
 HDC hDestDC,
 const RECT& rectDest,
 const RECT& rectSrc,
 DWORD dwROP = SRCCOPY) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hDestDC`  
 コピー先デバイス コンテキストへのハンドル。  
  
 `xDest`  
 X 座標、コピー先の四角形の左上隅の論理単位です。  
  
 `yDest`  
 Y 座標、コピー先の四角形の左上隅の論理単位です。  
  
 `nDestWidth`  
 論理ユニットは、コピー先の四角形の幅。  
  
 `nDestHeight`  
 論理ユニットは、コピー先の四角形の高さ。  
  
 `dwROP`  
 実行するラスター オペレーションです。 ラスター オペレーション コードは、変換先を形成する、ソース、変換先、およびパターンのビットで定義された、現在選択されているブラシ) を組み合わせる方法を定義します。 参照してください[BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370)で、[!INCLUDE[winSDK](./includes/winsdk_md.md)]の他のラスター オペレーション コードとその説明の一覧です。  
  
 `rectDest`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体、送信先を識別します。  
  
 `xSrc`  
 X 座標、元の四角形の左上隅の論理単位です。  
  
 `ySrc`  
 Y 座標、元の四角形の左上隅の論理単位です。  
  
 `nSrcWidth`  
 論理ユニットは、元の四角形の幅。  
  
 `nSrcHeight`  
 論理ユニットは、元の四角形の高さ。  
  
 `rectSrc`  
 参照、`RECT`構造のソースを特定します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、0 以外。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [StretchBlt](http://msdn.microsoft.com/library/windows/desktop/dd145120)で、[!INCLUDE[winSDK](./includes/winsdk_md.md)]です。  
  
##  <a name="transparentblt"></a>CImage::TransparentBlt  
 コピー元デバイス コンテキストから現在のデバイス コンテキストにビットマップをコピーします。  
  
```
BOOL TransparentBlt(
 HDC hDestDC,
 int xDest,
 int yDest,
 int nDestWidth,
 int nDestHeight,
 UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
 HDC hDestDC,
 const RECT& rectDest,
 UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
 HDC hDestDC,
 int xDest,
 int yDest,
 int nDestWidth,
 int nDestHeight,
 int xSrc,
 int ySrc,
 int nSrcWidth,
 int nSrcHeight,
 UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
 HDC hDestDC,
 const RECT& rectDest,
 const RECT& rectSrc,
 UINT crTransparent = CLR_INVALID) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hDestDC`  
 コピー先デバイス コンテキストへのハンドル。  
  
 `xDest`  
 X 座標、コピー先の四角形の左上隅の論理単位です。  
  
 `yDest`  
 Y 座標、コピー先の四角形の左上隅の論理単位です。  
  
 `nDestWidth`  
 論理ユニットは、コピー先の四角形の幅。  
  
 `nDestHeight`  
 論理ユニットは、コピー先の四角形の高さ。  
  
 *crTransparent*  
 コピー元のビットマップが透明として扱うの色。 既定では、 **CLR_INVALID**、現在は、イメージの透明色として設定する色を使用することを示します。  
  
 `rectDest`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体、送信先を識別します。  
  
 `xSrc`  
 X 座標、元の四角形の左上隅の論理単位です。  
  
 `ySrc`  
 Y 座標、元の四角形の左上隅の論理単位です。  
  
 `nSrcWidth`  
 論理ユニットは、元の四角形の幅。  
  
 `nSrcHeight`  
 論理ユニットは、元の四角形の高さ。  
  
 `rectSrc`  
 参照、`RECT`構造のソースを特定します。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**成功した場合、それ以外の場合**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 `TransparentBlt`4 ビット/ピクセルと 8 ビット/ピクセルのビットマップをソースに対応します。 使用[CImage::AlphaBlend](#alphablend)を透明に 32 ビット/ピクセルのビットマップを指定します。  
  
  
### <a name="example"></a>例  

```cpp  
// Performs a transparent blit from the source image to the destination 
// image using the images' current transparency settings
BOOL TransparentBlt(CImage* pSrcImage, CImage* pDstImage, 
       int xDest, int yDest, int nDestWidth, int nDestHeight)
{
  HDC hDstDC = NULL;
  BOOL bResult;

  if(pSrcImage == NULL || pDstImage == NULL)
  {
  // Invalid parameter
  return FALSE;
  }

  // Obtain a DC to the destination image
  hDstDC = pDstImage->GetDC();

  // Perform the blit
  bResult = pSrcImage->TransparentBlt(hDstDC, xDest, yDest, nDestWidth, nDestHeight);

  // Release the destination DC
  pDstImage->ReleaseDC();

  return bResult;
}
```

  
## <a name="see-also"></a>関連項目  
 [MMXSwarm サンプル](../../visual-cpp-samples.md)   
 [SimpleImage サンプル](../../visual-cpp-samples.md)   
 [デバイスに依存しないビットマップ](http://msdn.microsoft.com/library/windows/desktop/dd183562)   
 [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183494)   
 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)
 [デバイスに依存しないビットマップ](http://msdn.microsoft.com/library/windows/desktop/dd183562)   
 [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183494)   










