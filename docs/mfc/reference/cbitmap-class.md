---
title: "CBitmap クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBitmap
- AFXWIN/CBitmap
- AFXWIN/CBitmap::CBitmap
- AFXWIN/CBitmap::CreateBitmap
- AFXWIN/CBitmap::CreateBitmapIndirect
- AFXWIN/CBitmap::CreateCompatibleBitmap
- AFXWIN/CBitmap::CreateDiscardableBitmap
- AFXWIN/CBitmap::FromHandle
- AFXWIN/CBitmap::GetBitmap
- AFXWIN/CBitmap::GetBitmapBits
- AFXWIN/CBitmap::GetBitmapDimension
- AFXWIN/CBitmap::LoadBitmap
- AFXWIN/CBitmap::LoadMappedBitmap
- AFXWIN/CBitmap::LoadOEMBitmap
- AFXWIN/CBitmap::SetBitmapBits
- AFXWIN/CBitmap::SetBitmapDimension
dev_langs:
- C++
helpviewer_keywords:
- drawing, tools
- CBitmap class
- GDI bitmap
ms.assetid: 3980616a-c59d-495a-86e6-62bd3889c84c
caps.latest.revision: 22
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
ms.openlocfilehash: ccfe592bbbae8c0eff22baa6e1baac56754ef6fc
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cbitmap-class"></a>CBitmap クラス
Windows のグラフィック デバイス インターフェイス (GDI: Graphics Device Interface) のビットマップをカプセル化したもので、ビットマップを操作するためのメンバー関数を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CBitmap : public CGdiObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CBitmap::CBitmap](#cbitmap)|`CBitmap` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CBitmap::CreateBitmap](#createbitmap)|デバイスに依存するメモリのビットマップを指定した幅、高さ、およびビット パターンを持つオブジェクトを初期化します。|  
|[CBitmap::CreateBitmapIndirect](#createbitmapindirect)|指定された幅、高さ、および (指定されている) 場合、ビット パターンを持つビットマップでのオブジェクトを初期化、**ビットマップ**構造体。|  
|[CBitmap::CreateCompatibleBitmap](#createcompatiblebitmap)|指定されたデバイスと互換性があるように、ビットマップでオブジェクトを初期化します。|  
|[CBitmap::CreateDiscardableBitmap](#creatediscardablebitmap)|指定されたデバイスと互換性があるビットマップを破棄できるオブジェクトを初期化します。|  
|[CBitmap::FromHandle](#fromhandle)|ポインターを返す、`CBitmap`を Windows のハンドルが指定されると`HBITMAP`ビットマップです。|  
|[CBitmap::GetBitmap](#getbitmap)|入力、**ビットマップ**ビットマップについての情報を含む構造体。|  
|[列](#getbitmapbits)|指定したビットマップのビットを指定されたバッファーにコピーします。|  
|[CBitmap::GetBitmapDimension](#getbitmapdimension)|ビットマップの高さと幅を返します。 高さと幅と見なされますによって以前に設定されている、[呼び出す](#setbitmapdimension)メンバー関数。|  
|[CBitmap::LoadBitmap](#loadbitmap)|アプリケーションの実行可能ファイルの名前付きのビットマップ リソースを読み込み、ビットマップをオブジェクトにアタッチするには、オブジェクトを初期化します。|  
|[CBitmap::LoadMappedBitmap](#loadmappedbitmap)|ビットマップを読み込んで、現在のシステムの色に色をマップします。|  
|[CBitmap::LoadOEMBitmap](#loadoembitmap)|定義済みの Windows ビットマップを読み込み、ビットマップをオブジェクトにアタッチするには、オブジェクトを初期化します。|  
|[CBitmap::SetBitmapBits](#setbitmapbits)|ビットマップのビットを指定したビット値に設定します。|  
|[CBitmap::SetBitmapDimension](#setbitmapdimension)|0.1 ミリメートル単位でのビットマップの幅と高さを割り当てます。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CBitmap::operator HBITMAP](#operator_hbitmap)|接続されている Windows ハンドルを返す、`CBitmap`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 使用する、`CBitmap`オブジェクト、オブジェクトを作成、初期化のメンバー関数のいずれかにビットマップ ハンドルをアタッチし、オブジェクトのメンバー関数を呼び出します。  
  
 ようなグラフィック オブジェクトの使用に関する詳細について`CBitmap`を参照してください[グラフィック オブジェクト](../../mfc/graphic-objects.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBitmap`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cbitmap"></a>CBitmap::CBitmap  
 `CBitmap` オブジェクトを構築します。  
  
```  
CBitmap();
```  
  
### <a name="remarks"></a>コメント  
 結果のオブジェクトは、メンバー関数の初期化のいずれかで初期化する必要があります。  
  
##  <a name="createbitmap"></a>CBitmap::CreateBitmap  
 指定した幅、高さ、ビット パターンに設定されている、デバイス依存のメモリ ビットマップを初期化します。  
  
```  
BOOL CreateBitmap(
    int nWidth,  
    int nHeight,  
    UINT nPlanes,  
    UINT nBitcount,  
    const void* lpBits);
```  
  
### <a name="parameters"></a>パラメーター  
 `nWidth`  
 ビットマップの幅 (ピクセル単位) を指定します。  
  
 `nHeight`  
 ビットマップの高さ (ピクセル単位) を指定します。  
  
 `nPlanes`  
 ビットマップ内でのカラー プレーンの数を指定します。  
  
 `nBitcount`  
 表示ピクセルごとのカラー ビット数を指定します。  
  
 `lpBits`  
 初期のビットマップのビット値を含むバイト配列を指します。 **NULL**の場合、新しいビットマップは初期化されないままになります。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 カラー ビットマップの場合、 `nPlanes` パラメーターまたは `nBitcount` パラメーターを 1 に設定する必要があります。 両方のパラメーターを 1 に設定すると、 `CreateBitmap` によってモノクロのビットマップが作成されます。  
  
 使用して「メモリ デバイス コンテキスト」の現在のビットマップとして選択するビットマップは、ディスプレイ デバイスに直接選択することはできません、 [:selectobject](../../mfc/reference/cdc-class.md#selectobject)を使用して、互換性のあるデバイス コンテキストにコピーし、[ビットマップ](../../mfc/reference/cdc-class.md#bitblt)関数です。  
  
 `CBitmap` 関数によって作成された `CreateBitmap` オブジェクトでの作業終了後、デバイス コンテキスト外のビットマップを最初に選択し、次に `CBitmap` オブジェクトを削除します。  
  
 詳しくは、 **BITMAP** 構造体の **bmBits** フィールドに関する記述をご覧ください。 [ビットマップ](../../mfc/reference/bitmap-structure.md)構造体は」の説明、 [CBitmap::CreateBitmapIndirect](#createbitmapindirect)メンバー関数。  
  
##  <a name="createbitmapindirect"></a>CBitmap::CreateBitmapIndirect  
 ビットマップの幅、高さ、およびが指す構造体で指定されたビット パターン (指定されている) 場合のある初期化`lpBitmap`します。  
  
```  
BOOL CreateBitmapIndirect(LPBITMAP lpBitmap);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpBitmap`  
 指す、[ビットマップ](../../mfc/reference/bitmap-structure.md)ビットマップについての情報を格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用してメモリ デバイス コンテキストの現在のビットマップとして選択するビットマップは、ディスプレイ デバイスに直接選択することはできません、 [:selectobject](../../mfc/reference/cdc-class.md#selectobject)を使用して、互換性のあるデバイス コンテキストにコピーし、[ビットマップ](../../mfc/reference/cdc-class.md#bitblt)または[CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt)関数です。 (、 [Cdc::patblt](../../mfc/reference/cdc-class.md#patblt)関数は、現在のブラシのビットマップをディスプレイ デバイス コンテキストに直接コピーできます)。  
  
 場合、**ビットマップ**構造体を指す、`lpBitmap`パラメーター値が入力されたを使用して、`GetObject`関数の場合、ビットマップのビットが指定されていないと、ビットマップが初期化されていません。 ビットマップを初期化するために、アプリケーション、関数など、使用できる[ビットマップ](../../mfc/reference/cdc-class.md#bitblt)または[SetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd162973)の最初のパラメーターで識別されるビットマップからビットをコピーする`CGdiObject::GetObject`によって作成されたビットマップに`CreateBitmapIndirect`します。  
  
 終了するときに、`CBitmap`オブジェクトを作成した`CreateBitmapIndirect`関数で最初に、デバイス コンテキストからビットマップを選択し、削除、`CBitmap`オブジェクトです。  
  
##  <a name="createcompatiblebitmap"></a>CBitmap::CreateCompatibleBitmap  
 指定されたデバイスと互換性があるビットマップ初期化`pDC`します。  
  
```  
BOOL CreateCompatibleBitmap(
    CDC* pDC,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 デバイス コンテキストを指定します。  
  
 `nWidth`  
 ビットマップの幅 (ピクセル単位) を指定します。  
  
 `nHeight`  
 ビットマップの高さ (ピクセル単位) を指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ビットマップは、同じ数のカラー プレーンまたは指定したデバイス コンテキストと同じビット/ピクセル形式を持ちます。 指定された&1; つと互換性があるすべてのメモリ デバイスの現在のビットマップとして選択できるように`pDC`します。  
  
 場合`pDC`メモリ デバイス コンテキストは、返されるビットマップは、そのデバイス コンテキストで現在選択されているビットマップと同じ形式を持ちます。 「メモリ デバイス コンテキスト」は、表示画面を表すメモリ ブロックです。 これは、互換性のあるデバイスの実際の表示画面にコピーする前にメモリ内のイメージを準備する使用できます。  
  
 メモリ デバイス コンテキストが作成されると、GDI はモノクロのストック ビットマップを自動的にそれを選択します。  
  
 ビットマップの形式がによって返される色メモリ デバイス コンテキストは、カラーかモノクロ ビットマップの選択は、以降、`CreateCompatibleBitmap`関数は常に同じ。 ただし、メモリ デバイス コンテキストの互換性のあるビットマップの形式は常に、デバイスの形式にします。  
  
 終了するときに、`CBitmap`オブジェクトを作成した、`CreateCompatibleBitmap`関数で最初に、デバイス コンテキストからビットマップを選択し、削除、`CBitmap`オブジェクトです。  
  
##  <a name="creatediscardablebitmap"></a>CBitmap::CreateDiscardableBitmap  
 破棄できるビットマップで識別されるデバイス コンテキストと互換性がある初期化`pDC`します。  
  
```  
BOOL CreateDiscardableBitmap(
    CDC* pDC,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 デバイス コンテキストを指定します。  
  
 `nWidth`  
 (Bits) で、ビットマップの幅を指定します。  
  
 `nHeight`  
 (Bits) で、ビットマップの高さを指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ビットマップは、同じ数のカラー プレーンまたは指定したデバイス コンテキストと同じビット/ピクセル形式を持ちます。 アプリケーションは、このビットマップを選択してによって指定されたものと互換性があるメモリ デバイスの現在のビットマップとして`pDC`します。  
  
 Windows では、アプリケーションではディスプレイ コンテキストに選択しない場合にのみ、この関数によって作成されたビットマップを破棄できます。 Windows が選択されていない、後でアプリケーションが、それを選択しようとした場合、ビットマップを破棄する場合、 [:selectobject](../../mfc/reference/cdc-class.md#selectobject)関数が返す**NULL**します。  
  
 終了するときに、`CBitmap`オブジェクトを作成した、`CreateDiscardableBitmap`関数で最初に、デバイス コンテキストからビットマップを選択し、削除、`CBitmap`オブジェクトです。  
  
##  <a name="fromhandle"></a>CBitmap::FromHandle  
 ポインターを返す、 `CBitmap` Windows GDI ビットマップを識別するハンドルが指定されるとします。  
  
```  
static CBitmap* PASCAL FromHandle(HBITMAP hBitmap);
```  
  
### <a name="parameters"></a>パラメーター  
 `hBitmap`  
 Windows GDI ビットマップを指定します。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CBitmap`成功以外の場合は、オブジェクト**NULL**します。  
  
### <a name="remarks"></a>コメント  
 場合、`CBitmap`オブジェクトはハンドルが一時的にまだアタッチされていない`CBitmap`オブジェクトが作成され、接続されています。 この一時`CBitmap`だけですべて一時的なグラフィックを時間があるオブジェクトは削除されるまで、次回、アプリケーションのアイドル時間のイベント ループで、オブジェクトが有効です。 言い換えると、別の方法は、1 つのウィンドウ メッセージを処理中に一時オブジェクトが有効でのみことです。  
  
##  <a name="getbitmap"></a>CBitmap::GetBitmap  
 割り当てられているビットマップのイメージのプロパティを取得します。  
  
```  
int GetBitmap(BITMAP* pBitMap);
```  
  
### <a name="parameters"></a>パラメーター  
 `pBitMap`  
 ポインター、 [BITMAP 構造体](../../mfc/reference/bitmap-structure.md)イメージのプロパティを受け取る。 このパラメーターは `NULL` にすることはできません。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getbitmapbits"></a>列  
 指定されたバッファーに割り当てられているビットマップのビット パターンをコピーします。  
  
```  
DWORD GetBitmapBits(
    DWORD dwCount,  
    LPVOID lpBits) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `dwCount`  
 バッファーにコピーするバイト数。  
  
 `lpBits`  
 ビットマップを受け取るバッファーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、バッファーにコピーされたバイト数それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用[CBitmap::GetBitmap](#getbitmap)必要なバッファー サイズを決定します。  
  
##  <a name="getbitmapdimension"></a>CBitmap::GetBitmapDimension  
 ビットマップの高さと幅を返します。  
  
```  
CSize GetBitmapDimension() const;  
```  
  
### <a name="return-value"></a>戻り値  
 幅と、ビットマップの高さは、0.1 ミリメートル単位で測定されます。 高さは、 **cy**のメンバー、`CSize`オブジェクト、および幅では、 **cx**メンバーです。 使用して、ビットマップの幅と高さを設定したがない場合`SetBitmapDimension`、戻り値は 0 です。  
  
### <a name="remarks"></a>コメント  
 高さと幅を使用して、以前に設定されていると見なされます、[呼び出す](#setbitmapdimension)メンバー関数。  
  
##  <a name="loadbitmap"></a>CBitmap::LoadBitmap  
 によって指定されたビットマップ リソースを読み込みます`lpszResourceName`の ID 番号によって識別される`nIDResource`アプリケーションの実行可能ファイルからです。  
  
```  
BOOL LoadBitmap(LPCTSTR lpszResourceName);  
BOOL LoadBitmap(UINT nIDResource);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszResourceName`  
 ビットマップ リソースの名前を表す null で終わる文字列へのポインター。  
  
 `nIDResource`  
 ビットマップ リソースのリソース ID 番号を指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 読み込まれたビットマップが接続されている、`CBitmap`オブジェクトです。  
  
 ビットマップがで識別される場合`lpszResourceName`が存在しない場合、メモリが不足してビットマップを読み込む場合、関数は、0 を返します。  
  
 使用することができます、 [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject)によって読み込まれるビットマップを削除する関数、`LoadBitmap`関数、または`CBitmap`デストラクターのオブジェクトを削除します。  
  
> [!CAUTION]
>  オブジェクトを削除する前に、デバイス コンテキストに選択されていないことを確認してください。  
  
 次のビットマップは、Windows 3.1 以降のバージョンに追加されました。  
  
 **OBM_UPARRROWIOBM_DNARROWIOBM_RGARROWIOBM_LFARROWI**  
  
 これらのビットマップは 3.0 と以前のバージョンの Windows 用のデバイス ドライバーに存在しません。 ビットマップと表示形式の完全な一覧については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="loadmappedbitmap"></a>CBitmap::LoadMappedBitmap  
 このメンバー関数を呼び出して、ビットマップを読み込んで、現在のシステムの色に色をマップします。  
  
```  
BOOL LoadMappedBitmap(
    UINT nIDBitmap,  
    UINT nFlags = 0,  
    LPCOLORMAP lpColorMap = NULL,  
    int nMapSize = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDBitmap`  
 ビットマップ リソースの ID。  
  
 `nFlags`  
 ビットマップに対するフラグです。 ゼロの場合、または**CMB_MASKED**します。  
  
 `lpColorMap`  
 ポインター、**カラーマップ**ビットマップにマップするために必要な色の情報を格納する構造体。 このパラメーターは場合**NULL**関数は既定のカラー マップを使用します。  
  
 *nMapSize*  
 マップの色の数が指す`lpColorMap`します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定では、`LoadMappedBitmap`ボタン グリフでよく使用される色をマップします。  
  
 マップされたビットマップを作成する方法の詳細については、Windows の関数を参照してください。 [CreateMappedBitmap](http://go.microsoft.com/fwlink/linkid=230562)と[カラーマップ](http://msdn.microsoft.com/library/windows/desktop/bb760448)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="loadoembitmap"></a>CBitmap::LoadOEMBitmap  
 Windows で使用される定義済みのビットマップを読み込みます。  
  
```  
BOOL LoadOEMBitmap(UINT nIDBitmap);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDBitmap`  
 定義済みの Windows ビットマップの ID 番号。 使用可能な値は、WINDOWS から以下に示します。H:  
  
|||  
|-|-|  
|**OBM_BTNCORNERS**|**OBM_OLD_RESTORE**|  
|**OBM_BTSIZE**|**OBM_OLD_RGARROW**|  
|**OBM_CHECK**|**OBM_OLD_UPARROW**|  
|**OBM_CHECKBOXES**|**OBM_OLD_ZOOM**|  
|**OBM_CLOSE**|**OBM_REDUCE**|  
|**OBM_COMBO**|**OBM_REDUCED**|  
|**OBM_DNARROW**|**OBM_RESTORE**|  
|**OBM_DNARROWD**|**OBM_RESTORED**|  
|**OBM_DNARROWI**|**OBM_RGARROW**|  
|**OBM_LFARROW**|**OBM_RGARROWD**|  
|**OBM_LFARROWD**|**OBM_RGARROWI**|  
|**OBM_LFARROWI**|**OBM_SIZE**|  
|**OBM_MNARROW**|**OBM_UPARROW**|  
|**OBM_OLD_CLOSE**|**OBM_UPARROWD**|  
|**OBM_OLD_DNARROW**|**OBM_UPARROW**|  
|**OBM_OLD_LFARROW**|**OBM_ZOOM**|  
|**OBM_OLD_REDUCE**|**OBM_ZOOMD**|  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 始まる名前をビットマップ**OBM_OLD** 3.0 より前のバージョンの Windows で使用されるビットマップを表します。  
  
 なお定数**OEMRESOURCE** WINDOWS をインクルードする前に定義する必要があります。H のいずれかを使用するために、 **OBM_**定数です。  
  
##  <a name="operator_hbitmap"></a>CBitmap::operator HBITMAP  
 この演算子の接続されている Windows GDI ハンドルの取得を使用して、`CBitmap`オブジェクトです。  
  
```  
operator HBITMAP() const;  
```  
  
### <a name="return-value"></a>戻り値  
 かどうかは成功すると、Windows GDI オブジェクトへのハンドルによって表される、`CBitmap`オブジェクト。 それ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 この演算子はキャスト演算子の`HBITMAP`オブジェクトです。  
  
 グラフィック オブジェクトの使い方の詳細については、次を参照してください。[グラフィック オブジェクト](http://msdn.microsoft.com/library/windows/desktop/dd144962)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="setbitmapbits"></a>CBitmap::SetBitmapBits  
 ビットマップのビットによって指定されたビットの値を設定`lpBits`します。  
  
```  
DWORD SetBitmapBits(
    DWORD dwCount,  
    const void* lpBits);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwCount`  
 指すバイト数を指定`lpBits`します。  
  
 `lpBits`  
 指す、**バイト**配列にコピーされるピクセル値を含む、`CBitmap`オブジェクトです。 ビットマップをそのイメージを正しく描画するためには、値を CBitmap インスタンスの作成時に指定された高さ、幅、および色深度の値に準拠するようにフォーマットされている必要があります。 詳細については、次を参照してください。 [CBitmap::CreateBitmap](#createbitmap)します。  
  
### <a name="return-value"></a>戻り値  
 ビットマップのビットを設定で使用されるバイト数関数が失敗した場合は 0。  
  
##  <a name="setbitmapdimension"></a>CBitmap::SetBitmapDimension  
 0.1 ミリメートル単位でのビットマップの幅と高さを割り当てます。  
  
```  
CSize SetBitmapDimension(
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 `nWidth`  
 (0.1 ミリメートル単位) のビットマップの幅を指定します。  
  
 `nHeight`  
 (0.1 ミリメートル単位) のビットマップの高さを指定します。  
  
### <a name="return-value"></a>戻り値  
 前のビットマップの寸法。 高さは、 **cy**のメンバー変数、`CSize`オブジェクト、および幅では、 **cx**メンバー変数です。  
  
### <a name="remarks"></a>コメント  
 GDI に送り返すアプリケーションを呼び出す場合を除くこれらの値を使用していない、 [GetBitmapDimension](#getbitmapdimension)メンバー関数。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MDI](../../visual-cpp-samples.md)   
 [CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)


