---
title: "CPalette クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPalette
- AFXWIN/CPalette
- AFXWIN/CPalette::CPalette
- AFXWIN/CPalette::AnimatePalette
- AFXWIN/CPalette::CreateHalftonePalette
- AFXWIN/CPalette::CreatePalette
- AFXWIN/CPalette::FromHandle
- AFXWIN/CPalette::GetEntryCount
- AFXWIN/CPalette::GetNearestPaletteIndex
- AFXWIN/CPalette::GetPaletteEntries
- AFXWIN/CPalette::ResizePalette
- AFXWIN/CPalette::SetPaletteEntries
dev_langs:
- C++
helpviewer_keywords:
- CPalette class
- HPALETTE
- color palettes, MFC
ms.assetid: 8cd95498-53ed-4852-85e1-70e522541114
caps.latest.revision: 23
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
ms.openlocfilehash: 6ccd389eaf765993c59311cc1041893f2cf9fbfa
ms.lasthandoff: 02/24/2017

---
# <a name="cpalette-class"></a>CPalette クラス
Windows のカラー パレットをカプセル化します。  
  
## <a name="syntax"></a>構文  
  
```  
class CPalette : public CGdiObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CPalette::CPalette](#cpalette)|構築、`CPalette`ない接続されている Windows のパレットを持つオブジェクト。 初期化する必要があります、`CPalette`を使用する前に、初期化のメンバー関数のいずれかを持つオブジェクト。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPalette::AnimatePalette](#animatepalette)|識別される論理パレット内のエントリを置き換える、`CPalette`オブジェクトです。 アプリケーションが、クライアント領域を更新する Windows システム パレットに新しいエントリをすぐにマップされるためです。|  
|[CPalette::CreateHalftonePalette](#createhalftonepalette)|デバイス コンテキストのハーフトーン パレットを作成し、それにアタッチ、`CPalette`オブジェクトです。|  
|[CPalette::CreatePalette](#createpalette)|Windows のカラー パレットを作成し、それをアタッチ、`CPalette`オブジェクトです。|  
|[CPalette::FromHandle](#fromhandle)|ポインターを返す、 `CPalette` Windows パレット オブジェクトへのハンドルが指定されるとします。|  
|[CPalette::GetEntryCount](#getentrycount)|論理パレットのパレット エントリの数を取得します。|  
|[CPalette::GetNearestPaletteIndex](#getnearestpaletteindex)|論理パレットに色の値に最も近いエントリのインデックスを返します。|  
|[CPalette::GetPaletteEntries](#getpaletteentries)|論理パレットのパレット エントリの範囲を取得します。|  
|[CPalette::ResizePalette](#resizepalette)|指定された論理パレットのサイズを変更、`CPalette`エントリ数を指定するオブジェクト。|  
|[CPalette::SetPaletteEntries](#setpaletteentries)|論理パレット内のエントリの範囲内には、RGB 色の値とフラグを設定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CPalette::operator HPALETTE](#operator_hpalette)|返します。、`HPALETTE`に接続されている、`CPalette`です。|  
  
## <a name="remarks"></a>コメント  
 パレットでは、アプリケーションと (ディスプレイ デバイス) などの色の出力デバイス間のインターフェイスを提供します。 インターフェイスは、活用するために、出力デバイスの色の機能の重大な障害は他のアプリケーションで表示される色を妨げることがなくアプリケーションを使用します。 Windows は、アプリケーションの論理パレット (必要な色のリスト) と (を使用可能な色を定義) システム パレットを使用して、使用する色を決定します。  
  
 A`CPalette`オブジェクトによって参照されるパレットを操作するために、オブジェクトがメンバー関数を提供します。 構築、`CPalette`オブジェクトを実際のパレットのグラフィックス デバイス インターフェイス (GDI) オブジェクトを作成し、そのエントリとその他のプロパティを操作するメンバー関数を使用しています。  
  
 使用する方法について`CPalette`を参照してください[グラフィック オブジェクト](../../mfc/graphic-objects.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPalette`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="animatepalette"></a>CPalette::AnimatePalette  
 接続されている論理パレット内のエントリを置き換える、`CPalette`オブジェクトです。  
  
```  
void AnimatePalette(
    UINT nStartIndex,  
    UINT nNumEntries,  
    LPPALETTEENTRY lpPaletteColors);
```  
  
### <a name="parameters"></a>パラメーター  
 `nStartIndex`  
 アニメーション化するパレットの最初のエントリを指定します。  
  
 `nNumEntries`  
 アニメーション化パレット内のエントリの数を指定します。  
  
 `lpPaletteColors`  
 配列の最初のメンバーを指す[受け取る](http://msdn.microsoft.com/library/windows/desktop/dd162769)構造体によって識別されるパレット エントリを置き換え`nStartIndex`と`nNumEntries`です。  
  
### <a name="remarks"></a>コメント  
 アプリケーションを呼び出すと`AnimatePalette`がない、クライアント領域を更新する Windows システム パレットに新しいエントリをすぐにマップされるためです。  
  
 `AnimatePalette`関数を持つエントリを変更するのみ、 **PC_RESERVED**フラグに対応する設定**palPaletteEntry**のメンバー、[保持](http://msdn.microsoft.com/library/windows/desktop/dd145040)構造に関連付けられている、`CPalette`オブジェクトです。 参照してください**保持**で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]詳細については、この構造体。  
  
##  <a name="cpalette"></a>CPalette::CPalette  
 `CPalette` オブジェクトを構築します。  
  
```  
CPalette();
```  
  
### <a name="remarks"></a>コメント  
 オブジェクトを含んでいない添付パレットが呼び出されるまで`CreatePalette`にいずれかにアタッチします。  
  
##  <a name="createhalftonepalette"></a>CPalette::CreateHalftonePalette  
 デバイス コンテキストのハーフトーン パレットを作成します。  
  
```  
BOOL CreateHalftonePalette(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 デバイス コンテキストを識別します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 アプリケーション デバイス コンテキストの伸縮モードが設定されている場合に、ハーフトーン パレットを作成する**ハーフトーン**します。 によって返される論理ハーフトーン パレット、 [CreateHalftonePalette](http://msdn.microsoft.com/library/windows/desktop/dd183503)メンバー関数が選択および前に、デバイス コンテキストに実現し、必要がありますできる、 [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt)または[StretchDIBits](http://msdn.microsoft.com/library/windows/desktop/dd145121)関数が呼び出されます。  
  
 参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細については`CreateHalftonePalette`と**StretchDIBits**します。  
  
##  <a name="createpalette"></a>CPalette::CreatePalette  
 初期化、`CPalette`によって Windows の論理のカラー パレットの作成と追加するオブジェクト、`CPalette`オブジェクトです。  
  
```  
BOOL CreatePalette(LPLOGPALETTE lpLogPalette);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpLogPalette`  
 指す、[保持](http://msdn.microsoft.com/library/windows/desktop/dd145040)論理パレットの色に関する情報を格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細については、**保持**構造体。  
  
##  <a name="fromhandle"></a>CPalette::FromHandle  
 ポインターを返す、 `CPalette` Windows パレット オブジェクトへのハンドルが指定されるとします。  
  
```  
static CPalette* PASCAL FromHandle(HPALETTE hPalette);
```  
  
### <a name="parameters"></a>パラメーター  
 `hPalette`  
 Windows GDI のカラー パレットへのハンドル。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CPalette`成功以外の場合は、オブジェクト**NULL**します。  
  
### <a name="remarks"></a>コメント  
 場合、`CPalette`オブジェクトが、Windows のパレットが一時的に既にアタッチされていない`CPalette`オブジェクトが作成され、接続されています。 この一時`CPalette`だけですべて一時的なグラフィックを時間があるオブジェクトは削除されるまで、次回、アプリケーションのアイドル時間のイベント ループで、オブジェクトが有効です。 つまり、一時オブジェクトは&1; つのウィンドウ メッセージを処理中にのみ有効です。  
  
##  <a name="getentrycount"></a>CPalette::GetEntryCount  
 指定した論理パレット内のエントリの数を取得するには、このメンバー関数を呼び出します。  
  
```  
int GetEntryCount();
```  
  
### <a name="return-value"></a>戻り値  
 論理パレット内のエントリの数です。  
  
##  <a name="getnearestpaletteindex"></a>CPalette::GetNearestPaletteIndex  
 指定した色の値に最も近い論理のパレットのエントリのインデックスを返します。  
  
```  
UINT GetNearestPaletteIndex(COLORREF crColor) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `crColor`  
 照合する色を指定します。  
  
### <a name="return-value"></a>戻り値  
 論理パレット内のエントリのインデックス。 エントリには、指定した色に最も近い色が含まれています。  
  
##  <a name="getpaletteentries"></a>CPalette::GetPaletteEntries  
 論理パレットのパレット エントリの範囲を取得します。  
  
```  
UINT GetPaletteEntries(
    UINT nStartIndex,  
    UINT nNumEntries,  
    LPPALETTEENTRY lpPaletteColors) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nStartIndex`  
 取得する論理パレットの最初のエントリを指定します。  
  
 `nNumEntries`  
 論理パレットを取得するには、エントリの数を指定します。  
  
 `lpPaletteColors`  
 配列を指す[受け取る](http://msdn.microsoft.com/library/windows/desktop/dd162769)パレット エントリを受信するデータ構造体。 配列で指定された数は、少なくともデータ構造を含める必要があります`nNumEntries`します。  
  
### <a name="return-value"></a>戻り値  
 論理パレット; から取得されたエントリ数関数が失敗した場合は 0 を返します。  
  
##  <a name="operator_hpalette"></a>CPalette::operator HPALETTE  
 この演算子の接続されている Windows GDI ハンドルの取得を使用して、`CPalette`オブジェクトです。  
  
```  
operator HPALETTE() const;  
```  
  
### <a name="return-value"></a>戻り値  
 かどうかは成功すると、Windows GDI オブジェクトへのハンドルによって表される、`CPalette`オブジェクト。 それ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 この演算子はキャスト演算子の`HPALETTE`オブジェクトです。  
  
 グラフィック オブジェクトの使い方の詳細については、記事を参照してください。[グラフィック オブジェクト](http://msdn.microsoft.com/library/windows/desktop/dd144962)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="resizepalette"></a>CPalette::ResizePalette  
 接続されている論理パレットのサイズを変更、`CPalette`オブジェクトで指定されたエントリの数を`nNumEntries`します。  
  
```  
BOOL ResizePalette(UINT nNumEntries);
```  
  
### <a name="parameters"></a>パラメーター  
 `nNumEntries`  
 サイズ変更された後、パレット内のエントリの数を指定します。  
  
### <a name="return-value"></a>戻り値  
 パレットが正しくサイズ変更された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションを呼び出す場合`ResizePalette`には、パレットのサイズを減らすためには、サイズが変更されたパレットに残っているエントリは変更されていません。 アプリケーションを呼び出す場合`ResizePalette`パレットを拡大する追加パレット エントリは黒 (赤、緑、青の値はすべて 0) に設定され、その他のすべてのエントリのフラグが 0 に設定されます。  
  
 Windows API の詳細については`ResizePalette`を参照してください[ため](http://msdn.microsoft.com/library/windows/desktop/dd162928)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="setpaletteentries"></a>CPalette::SetPaletteEntries  
 論理パレット内のエントリの範囲内には、RGB 色の値とフラグを設定します。  
  
```  
UINT SetPaletteEntries(
    UINT nStartIndex,  
    UINT nNumEntries,  
    LPPALETTEENTRY lpPaletteColors);
```  
  
### <a name="parameters"></a>パラメーター  
 `nStartIndex`  
 設定する論理パレットの最初のエントリを指定します。  
  
 `nNumEntries`  
 設定する論理パレット内のエントリの数を指定します。  
  
 `lpPaletteColors`  
 配列を指す[受け取る](http://msdn.microsoft.com/library/windows/desktop/dd162769)パレット エントリを受信するデータ構造体。 配列で指定された数は、少なくともデータ構造を含める必要があります`nNumEntries`します。  
  
### <a name="return-value"></a>戻り値  
 論理パレット内のエントリの数を設定関数が失敗した場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションを呼び出すとき、デバイス コンテキストに論理パレットを選択するかどうかは`SetPaletteEntries`、変更は反映されません、アプリケーションが[:realizepalette](../../mfc/reference/cdc-class.md#realizepalette)します。  
  
 詳細については、Windows 構造**受け取る**を参照してください[受け取る](http://msdn.microsoft.com/library/windows/desktop/dd162769)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル DIBLOOK](../../visual-cpp-samples.md)   
 [CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CPalette::GetPaletteEntries](#getpaletteentries)   
 [CPalette::SetPaletteEntries](#setpaletteentries)




