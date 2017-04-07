---
title: "CBrush クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBrush
- AFXWIN/CBrush
- AFXWIN/CBrush::CBrush
- AFXWIN/CBrush::CreateBrushIndirect
- AFXWIN/CBrush::CreateDIBPatternBrush
- AFXWIN/CBrush::CreateHatchBrush
- AFXWIN/CBrush::CreatePatternBrush
- AFXWIN/CBrush::CreateSolidBrush
- AFXWIN/CBrush::CreateSysColorBrush
- AFXWIN/CBrush::FromHandle
- AFXWIN/CBrush::GetLogBrush
dev_langs:
- C++
helpviewer_keywords:
- brushes, CBrush class
- CBrush class
ms.assetid: e5ef2c62-dd95-4973-9090-f52f605900e1
caps.latest.revision: 21
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
ms.openlocfilehash: efcbe2757de3a7e4621e2b20c88726ead111cf8c
ms.lasthandoff: 02/24/2017

---
# <a name="cbrush-class"></a>CBrush クラス
Windows のグラフィック デバイス インターフェイス (GDI) のブラシをカプセル化します。  
  
## <a name="syntax"></a>構文  
  
```  
class CBrush : public CGdiObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CBrush::CBrush](#cbrush)|`CBrush` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CBrush::CreateBrushIndirect](#createbrushindirect)|スタイル、色、およびに指定されたパターンでブラシを初期化、 [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035)構造体。|  
|[CBrush::CreateDIBPatternBrush](#createdibpatternbrush)|デバイスに依存しないビットマップ (DIB) で指定されたパターンでブラシを初期化します。|  
|[CBrush::CreateHatchBrush](#createhatchbrush)|指定したハッシュ パターンおよび色のブラシを初期化します。|  
|[CBrush::CreatePatternBrush](#createpatternbrush)|ビットマップが指定したパターンでブラシを初期化します。|  
|[CBrush::CreateSolidBrush](#createsolidbrush)|指定した純色でブラシを初期化します。|  
|[CBrush::CreateSysColorBrush](#createsyscolorbrush)|既定のシステム カラーであるブラシを作成します。|  
|[CBrush::FromHandle](#fromhandle)|ポインターを返す、`CBrush`を Windows のハンドルが指定されると`HBRUSH`オブジェクトです。|  
|[CBrush::GetLogBrush](#getlogbrush)|取得、 [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035)構造体。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CBrush::operator HBRUSH](#operator_hbrush)|接続されている Windows ハンドルを返す、`CBrush`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 使用する、`CBrush`オブジェクト、構築、`CBrush`オブジェクトし、いずれかに渡す`CDC`ブラシを必要とするメンバー関数。  
  
 ブラシは、ハッチ、およびパターン実線、できます。  
  
 詳細については`CBrush`を参照してください[グラフィック オブジェクト](../../mfc/graphic-objects.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBrush`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cbrush"></a>CBrush::CBrush  
 `CBrush` オブジェクトを構築します。  
  
```  
CBrush(); 
CBrush(COLORREF crColor); 
CBrush(int nIndex, COLORREF crColor); 
explicit CBrush(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>パラメーター  
 `crColor`  
 RGB 色としてブラシの前景色を指定します。 ブラシをハッチすると、このパラメーターは、() の陰影の色を指定します。  
  
 `nIndex`  
 ブラシの陰影のスタイルを指定します。 次の値のいずれかを指定できます。  
  
- `HS_BDIAGONAL`45 ° の下位方向へ陰影 (左右から)  
  
- `HS_CROSS`水平および垂直方向の格子  
  
- `HS_DIAGCROSS`45 度をクロスハッチします。  
  
- `HS_FDIAGONAL`45 ° の上ハッチ (左右から)  
  
- `HS_HORIZONTAL`水平方向の陰影  
  
- `HS_VERTICAL`垂直方向の陰影  
  
 `pBitmap`  
 指す、`CBitmap`ブラシが描画されるビットマップを指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 `CBrush`コンス トラクターが&4; つオーバー ロードします。引数なしのコンス トラクターを作成、初期化されていない`CBrush`オブジェクトを使用する前に初期化する必要があります。  
  
 引数なしのコンス トラクターを使用する場合、その結果を初期化する必要があります`CBrush`オブジェクトを[CreateSolidBrush](#createsolidbrush)、 [CreateHatchBrush](#createhatchbrush)、 [CreateBrushIndirect](#createbrushindirect)、[とき](#createpatternbrush)、または[構築](#createdibpatternbrush)します。 いずれかの引数を受け取るコンス トラクターを使用する場合、これ以上初期化必要があります。 引数を持つコンス トラクターは、引数なしのコンス トラクターは常に成功しますが、エラーが発生した場合、例外をスローできます。  
  
 1 つのコンス トラクター [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)パラメーターを指定した色ソリッド ブラシを構築します。 色の RGB 値を指定およびで作成できます。、 `RGB` WINDOWS 内のマクロです。H.  
  
 2 つのパラメーターを持つコンス トラクターは、ハッチ ブラシを作成します。 `nIndex`ハッチ パターンのインデックスを指定します。 `crColor`パラメーターは、色を指定します。  
  
 持つコンス トラクター、`CBitmap`パラメーターは、パターンのブラシを作成します。 パラメーターは、ビットマップを識別します。 ビットマップを使用して作成されたと見なされます[CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap)、 [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect)、 [CBitmap::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap)、または[CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap)します。 塗りつぶしのパターンで使用するビットマップの最小サイズは、8 ピクセルの 8 ピクセルです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&21;](../../mfc/codesnippet/cpp/cbrush-class_1.cpp)]  
  
##  <a name="createbrushindirect"></a>CBrush::CreateBrushIndirect  
 スタイル、色、およびに指定されたパターンでブラシを初期化、 [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035)構造体。  
  
```  
BOOL CreateBrushIndirect(const LOGBRUSH* lpLogBrush);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpLogBrush*  
 指す、 [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035)ブラシについての情報を格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ブラシは、現在の任意のデバイス コンテキスト ブラシとして、後で選択できます。  
  
 (1 平面、ピクセルあたり 1 ビット) のモノクロ ビットマップを使用して作成されたブラシは、現在のテキストと背景色を使用して描画されます。 0 に設定されたビットで表されるピクセルは、現在のテキストの色が描画されます。 1 に設定されたビットで表されるピクセルは、現在の背景色が描画されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&22;](../../mfc/codesnippet/cpp/cbrush-class_2.cpp)]  
  
##  <a name="createdibpatternbrush"></a>CBrush::CreateDIBPatternBrush  
 デバイスに依存しないビットマップ (DIB) で指定されたパターンでブラシを初期化します。  
  
```  
BOOL CreateDIBPatternBrush(
    HGLOBAL hPackedDIB,  
    UINT nUsage);

 
BOOL CreateDIBPatternBrush(
    const void* lpPackedDIB,  
    UINT nUsage);
```  
  
### <a name="parameters"></a>パラメーター  
 *hPackedDIB*  
 パックされたデバイスに依存しないビットマップ (DIB) を格納しているグローバル メモリ オブジェクトを識別します。  
  
 *nUsage*  
 指定するかどうか、 **bmiColors**のフィールド、 [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md)データ構造 (「パック DIB」の一部) は、明示的な RGB 値またはインデックスを現在実現論理パレットに含まれています。 パラメーターには、次の値のいずれかを指定する必要があります。  
  
- **DIB_PAL_COLORS**カラー テーブルは、16 ビットのインデックスの配列で構成されます。  
  
- **DIB_RGB_COLORS**カラー テーブルには、リテラルの RGB 値が含まれています。  
  
 *lpPackedDIB*  
 構成される、パックされた DIB を指す、`BITMAPINFO`構造体の直後に、ビットマップのピクセルを定義するバイト配列。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ブラシは、ラスター オペレーションをサポートする任意のデバイス コンテキストに対して、後で選択できます。  
  
 DIB を処理する方法では、2 つのバージョンが異なります。  
  
-   最初のバージョンでの DIB を識別するハンドルを取得するを呼び出す Windows **GlobalAlloc**関数をグローバル メモリのブロックを割り当てます。 メモリを開梱されているの DIB を記入します。  
  
-   2 番目のバージョンで必要はありませんを呼び出す**GlobalAlloc**パックされた DIB のメモリを割り当てることです。  
  
 パックされた DIB から成る、`BITMAPINFO`直後に、ビットマップのピクセルを定義するバイト配列データ構造体。 塗りつぶしのパターンとして使用されるビットマップは、8 ピクセル × 8 ピクセルにする必要があります。 ビットマップが大きい場合は、Windows は、最初の 8 行とビットマップの左上隅のピクセルの 8 つの列に対応するビットだけを使用して、塗りつぶしパターンを作成します。  
  
 アプリケーションは、モノクロ デバイス コンテキストに、2 色の DIB パターン ブラシを選択すると、Windows は DIB で指定された色を無視し、代わりにデバイス コンテキストの現在のテキストと背景色を使用してパターン ブラシを表示します。 ピクセルの DIB の (DIB カラー テーブル内のオフセット 0) にある最初の色にマップは、テキストの色で表示されます。 (カラー テーブル内のオフセット 1) にある 2 番目の色にマップのピクセルは、背景色で表示されます。  
  
 次の Windows 関数を使用する方法の詳細については、次を参照してください、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]:。  
  
- [構築](http://msdn.microsoft.com/library/windows/desktop/dd183492)(3.0 より前のバージョンの Windows で作成されたアプリケーションで互換性のためだけにこの関数が提供されますを使用して、**されている**関数です。)。  
  
- [されている](http://msdn.microsoft.com/library/windows/desktop/dd183493)(この関数は Win32 ベースのアプリケーションで使用する必要があります)。  
  
- [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView 第&23;](../../mfc/codesnippet/cpp/cbrush-class_3.cpp)]  
  
##  <a name="createhatchbrush"></a>CBrush::CreateHatchBrush  
 指定したハッシュ パターンおよび色のブラシを初期化します。  
  
```  
BOOL CreateHatchBrush(
    int nIndex,  
    COLORREF crColor);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 ブラシの陰影のスタイルを指定します。 次の値のいずれかを指定できます。  
  
- `HS_BDIAGONAL`45 ° の下位方向へ陰影 (左右から)  
  
- `HS_CROSS`水平および垂直方向の格子  
  
- `HS_DIAGCROSS`45 度をクロスハッチします。  
  
- `HS_FDIAGONAL`45 ° の上ハッチ (左右から)  
  
- `HS_HORIZONTAL`水平方向の陰影  
  
- `HS_VERTICAL`垂直方向の陰影  
  
 `crColor`  
 RGB 色 (の陰影の色) として、ブラシの前景色を指定します。 参照してください[COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ブラシは、現在の任意のデバイス コンテキスト ブラシとして、後で選択できます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&24;](../../mfc/codesnippet/cpp/cbrush-class_4.cpp)]  
  
##  <a name="createpatternbrush"></a>CBrush::CreatePatternBrush  
 ビットマップが指定したパターンでブラシを初期化します。  
  
```  
BOOL CreatePatternBrush(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>パラメーター  
 `pBitmap`  
 ビットマップを識別します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ブラシは、ラスター オペレーションをサポートする任意のデバイス コンテキストに対して、後で選択できます。 識別されるビットマップ`pBitmap`を使用して初期化は、通常、 [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap)、 [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect)、 [CBitmap::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap)、または[CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap)関数です。  
  
 塗りつぶしのパターンとして使用されるビットマップは、8 ピクセル × 8 ピクセルにする必要があります。 ビットマップが大きい場合は、Windows は、最初の 8 行と列のビットマップの左上隅にあるピクセルに対応するビットだけ使用します。  
  
 ブラシのパターンは、関連するビットマップの影響を与えずに削除できます。 つまり、任意の数のパターンのブラシを作成する、ビットマップを使用することができます。  
  
 モノクロ ビットマップ (1 ピクセルあたり 1 ビット、1 色平面) を使用して作成されたブラシは、現在のテキストと背景色を使用して描画されます。 0 に設定されたビットで表されるピクセルは、現在のテキストの色で描画されます。 1 に設定されたビットで表されるピクセルは、現在の背景色で描画されます。  
  
 使用方法について[とき](http://msdn.microsoft.com/library/windows/desktop/dd183508)、Windows の機能を参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView&#25;](../../mfc/codesnippet/cpp/cbrush-class_5.cpp)]  
  
##  <a name="createsolidbrush"></a>CBrush::CreateSolidBrush  
 指定した純色でブラシを初期化します。  
  
```  
BOOL CreateSolidBrush(COLORREF crColor);
```  
  
### <a name="parameters"></a>パラメーター  
 `crColor`  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)をブラシの色を指定します。 色の RGB 値を指定およびで作成できます。、 `RGB` WINDOWS 内のマクロです。H.  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ブラシは、現在の任意のデバイス コンテキスト ブラシとして、後で選択できます。  
  
 アプリケーションが終了した場合で作成されたブラシを使用して`CreateSolidBrush`、デバイス コンテキスト ブラシを選択する必要があります。  
  
### <a name="example"></a>例  
  例を参照してください[CBrush::CBrush](#cbrush)します。  
  
##  <a name="createsyscolorbrush"></a>CBrush::CreateSysColorBrush  
 ブラシの色を初期化します。  
  
```  
BOOL CreateSysColorBrush(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 色のインデックスを指定します。 この値は、ウィンドウの要素のいずれかの描画に使用する色に対応します。 参照してください[GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の値の一覧です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ブラシは、現在の任意のデバイス コンテキスト ブラシとして、後で選択できます。  
  
 アプリケーションが終了した場合で作成されたブラシを使用して`CreateSysColorBrush`、デバイス コンテキスト ブラシを選択する必要があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&26;](../../mfc/codesnippet/cpp/cbrush-class_6.cpp)]  
  
##  <a name="fromhandle"></a>CBrush::FromHandle  
 ポインターを返す、`CBrush`ハンドルを Windows に指定されるとオブジェクト[HBRUSH](#operator_hbrush)オブジェクトです。  
  
```  
static CBrush* PASCAL FromHandle(HBRUSH hBrush);
```  
  
### <a name="parameters"></a>パラメーター  
 `hBrush`  
 `HANDLE`Windows GDI ブラシ。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CBrush`成功以外の場合は、オブジェクト**NULL**します。  
  
### <a name="remarks"></a>コメント  
 場合、`CBrush`オブジェクトが、一時的なハンドルに既にアタッチされていない`CBrush`オブジェクトが作成され、接続されています。 この一時`CBrush`オブジェクトが次回アプリケーションが、イベント ループのアイドル時間までのみ有効です。 この時点では、すべての一時的なグラフィック オブジェクトが削除されます。 つまり、一時オブジェクトは&1; つのウィンドウ メッセージを処理中にのみ有効です。  
  
 グラフィック オブジェクトの使い方の詳細については、次を参照してください。[グラフィック オブジェクト](http://msdn.microsoft.com/library/windows/desktop/dd144962)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CBrush::CBrush](#cbrush)します。  
  
##  <a name="getlogbrush"></a>CBrush::GetLogBrush  
 取得するには、このメンバー関数を呼び出す、`LOGBRUSH`構造体。  
  
```  
int GetLogBrush(LOGBRUSH* pLogBrush);
```  
  
### <a name="parameters"></a>パラメーター  
 `pLogBrush`  
 指す、 [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035)ブラシについての情報を格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合と`pLogBrush`有効なポインターでは、戻り値は、バッファーに格納されるバイト数。  
  
 関数が成功した場合と`pLogBrush`は**NULL**、戻り値は、関数の情報を保持するために必要なバイト数には、バッファーに保存します。  
  
 関数が失敗した場合、戻り値は 0 です。  
  
### <a name="remarks"></a>コメント  
 `LOGBRUSH`構造体は、スタイル、色、およびブラシのパターンを定義します。  
  
 たとえば、呼び出す`GetLogBrush`特定の色またはビットマップのパターンに一致します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&27;](../../mfc/codesnippet/cpp/cbrush-class_7.cpp)]  
  
##  <a name="operator_hbrush"></a>CBrush::operator HBRUSH  
 この演算子の接続されている Windows GDI ハンドルの取得を使用して、`CBrush`オブジェクトです。  
  
```  
operator HBRUSH() const;  
```  
  
### <a name="return-value"></a>戻り値  
 かどうかは成功すると、Windows GDI オブジェクトへのハンドルによって表される、`CBrush`オブジェクト。 それ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 この演算子はキャスト演算子の`HBRUSH`オブジェクトです。  
  
 グラフィック オブジェクトの使い方の詳細については、次を参照してください。[グラフィック オブジェクト](http://msdn.microsoft.com/library/windows/desktop/dd144962)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&28;](../../mfc/codesnippet/cpp/cbrush-class_8.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル PROPDLG](../../visual-cpp-samples.md)   
 [CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CBitmap クラス](../../mfc/reference/cbitmap-class.md)   
 [CDC クラス](../../mfc/reference/cdc-class.md)

