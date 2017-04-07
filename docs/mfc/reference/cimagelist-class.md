---
title: "CImageList クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CImageList
- AFXCMN/CImageList
- AFXCMN/CImageList::CImageList
- AFXCMN/CImageList::Add
- AFXCMN/CImageList::Attach
- AFXCMN/CImageList::BeginDrag
- AFXCMN/CImageList::Copy
- AFXCMN/CImageList::Create
- AFXCMN/CImageList::DeleteImageList
- AFXCMN/CImageList::DeleteTempMap
- AFXCMN/CImageList::Detach
- AFXCMN/CImageList::DragEnter
- AFXCMN/CImageList::DragLeave
- AFXCMN/CImageList::DragMove
- AFXCMN/CImageList::DragShowNolock
- AFXCMN/CImageList::Draw
- AFXCMN/CImageList::DrawEx
- AFXCMN/CImageList::DrawIndirect
- AFXCMN/CImageList::EndDrag
- AFXCMN/CImageList::ExtractIcon
- AFXCMN/CImageList::FromHandle
- AFXCMN/CImageList::FromHandlePermanent
- AFXCMN/CImageList::GetBkColor
- AFXCMN/CImageList::GetDragImage
- AFXCMN/CImageList::GetImageCount
- AFXCMN/CImageList::GetImageInfo
- AFXCMN/CImageList::GetSafeHandle
- AFXCMN/CImageList::Read
- AFXCMN/CImageList::Remove
- AFXCMN/CImageList::Replace
- AFXCMN/CImageList::SetBkColor
- AFXCMN/CImageList::SetDragCursorImage
- AFXCMN/CImageList::SetImageCount
- AFXCMN/CImageList::SetOverlayImage
- AFXCMN/CImageList::Write
- AFXCMN/CImageList::m_hImageList
dev_langs:
- C++
helpviewer_keywords:
- Windows common controls [C++], CImageList
- image lists [C++], CImageList class
- CImageList class
ms.assetid: b6d1a704-1c82-4548-8a8f-77972adc98a5
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: e61d99d6d68b1c68cd5e306dd0fcd10d6fe4324d
ms.lasthandoff: 02/24/2017

---
# <a name="cimagelist-class"></a>CImageList クラス
Windows コモン イメージ リスト コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CImageList : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CImageList::CImageList](#cimagelist)|`CImageList` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CImageList::Add](#add)|イメージ リストに、イメージまたはイメージを追加します。|  
|[CImageList::Attach](#attach)|イメージ リストのアタッチ、`CImageList`オブジェクトです。|  
|[CImageList::BeginDrag](#begindrag)|イメージのドラッグを開始します。|  
|[CImageList::Copy](#copy)|内のイメージをコピー、`CImageList`オブジェクトです。|  
|[CImageList::Create](#create)|イメージ リストを初期化し、それを`CImageList`オブジェクトです。|  
|[CImageList::DeleteImageList](#deleteimagelist)|イメージ リストを削除します。|  
|[CImageList::DeleteTempMap](#deletetempmap)|によって呼び出される、 [CWinApp](../../mfc/reference/cwinapp-class.md)アイドル時間のハンドラーを一時的なを削除する`CImageList`によって作成されたオブジェクト`FromHandle`します。|  
|[CImageList::Detach](#detach)|イメージ リスト オブジェクトのデタッチ、`CImageList`オブジェクトし、イメージ リストへのハンドルを返します。|  
|[CImageList::DragEnter](#dragenter)|ドラッグ操作中に更新プログラムをロックし、指定した位置にドラッグ イメージを表示します。|  
|[生じたとき](#dragleave)|ウィンドウのロックを解除し、ウィンドウを更新できるように、ドラッグ イメージを非表示にします。|  
|[CImageList::DragMove](#dragmove)|ドラッグ アンド ドロップ操作中にドラッグされているイメージを移動します。|  
|[CImageList::DragShowNolock](#dragshownolock)|ドラッグ操作中にウィンドウをロックすることがなくドラッグ イメージの表示と非表示を切り替えます。|  
|[:Draw](#draw)|ドラッグ アンド ドロップ操作中にドラッグされているイメージを描画します。|  
|[CImageList::DrawEx](#drawex)|指定したデバイス コンテキストでのイメージ リストのアイテムを描画します。 関数は、指定の描画スタイルを使用し、指定した色を使用してイメージを統合します。|  
|[CImageList::DrawIndirect](#drawindirect)|イメージ リストからイメージを描画します。|  
|[CImageList::EndDrag](#enddrag)|ドラッグ操作を終了します。|  
|[CImageList::ExtractIcon](#extracticon)|イメージとイメージ リスト内のマスクに基づいてアイコンを作成します。|  
|[CImageList::FromHandle](#fromhandle)|ポインターを返す、`CImageList`イメージ リストへのハンドルが指定されるとします。 `CImageList` オブジェクトがハンドルに関連付けられていない場合は、一時的な `CImageList` オブジェクトが生成され、関連付けられます。|  
|[CImageList::FromHandlePermanent](#fromhandlepermanent)|ポインターを返す、`CImageList`イメージ リストへのハンドルが指定されるとします。 場合、`CImageList`オブジェクトは、ハンドルに関連付けられていない**NULL**が返されます。|  
|[CImageList::GetBkColor](#getbkcolor)|イメージ リストの現在の背景色を取得します。|  
|[CImageList::GetDragImage](#getdragimage)|ドラッグすることに使用される一時的なイメージ リストを取得します。|  
|[CImageList::GetImageCount](#getimagecount)|イメージ リスト内のイメージの数を取得します。|  
|[CImageList::GetImageInfo](#getimageinfo)|イメージに関する情報を取得します。|  
|[CImageList::GetSafeHandle](#getsafehandle)|取得**m_hImageList**します。|  
|[CImageList::Read](#read)|アーカイブからのイメージ リストを読み取ります。|  
|[CImageList::Remove](#remove)|イメージ リストからイメージを削除します。|  
|[CImageList::Replace](#replace)|イメージ リスト内のイメージを新しいイメージで置き換えます。|  
|[CImageList::SetBkColor](#setbkcolor)|イメージ リストの背景色を設定します。|  
|[CImageList::SetDragCursorImage](#setdragcursorimage)|新しいドラッグ イメージを作成します。|  
|[CImageList::SetImageCount](#setimagecount)|イメージ リストのイメージのカウントをリセットします。|  
|[CImageList::SetOverlayImage](#setoverlayimage)|オーバーレイ マスクとして使用するイメージの一覧にイメージの&0; から始まるインデックスを追加します。|  
|[CImageList::Write](#write)|イメージ リストをアーカイブに書き込みます。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CImageList::operator HIMAGELIST](#operator_himagelist)|返します。、`HIMAGELIST`に接続されている、`CImageList`です。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CImageList::m_hImageList](#m_himagelist)|このオブジェクトにアタッチされているイメージ リストのハンドル。|  
  
## <a name="remarks"></a>コメント  
 「イメージ リスト」は、0 から始まるインデックスを使用してをそれぞれ参照でき、同じサイズのイメージのコレクションです。 イメージ リストを使用して、アイコンまたはビットマップの大規模なセットを効率的に管理できます。 画面デバイス形式の&1; つの大きなビットマップのイメージ リスト内のすべてのイメージが含まれています。 イメージ リストには、透過的にイメージを描画するためのマスク (アイコンのスタイル) を含むモノクロ ビットマップを含めることもできます。 Microsoft Win32 アプリケーション プログラミング インターフェイス (API) を使用すると、イメージを描画を作成し、イメージ リストを破棄、追加しイメージを削除する、イメージを置き換える、イメージのマージ、およびイメージのドラッグ イメージ リストの関数を提供します。  
  
 このコントロール (つまり、`CImageList`クラス) は以降、Windows 95/98 および Windows NT version 3.51 で実行するプログラムにのみ使用できます。  
  
 使用する方法について`CImageList`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CImageList](../../mfc/using-cimagelist.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CImageList`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="add"></a>CImageList::Add  
 1 つまたは複数のイメージまたはアイコン イメージ リストを追加するには、この関数を呼び出します。  
  
```  
int Add(
    CBitmap* pbmImage,  
    CBitmap* pbmMask);

 
int Add(
    CBitmap* pbmImage,  
    COLORREF crMask);  
  
int Add(HICON hIcon);
```  
  
### <a name="parameters"></a>パラメーター  
 `pbmImage`  
 イメージまたはイメージを含むビットマップへのポインター。 イメージの数は、ビットマップの幅から推測されます。  
  
 `pbmMask`  
 マスクを持つビットマップへのポインター。 イメージ リストとマスクを使用しない場合は、このパラメーターは無視されます。  
  
 `crMask`  
 マスクを生成するために使用する色。 与えられたビットマップにこの色は、各ピクセルは黒に変更し、マスクの対応するビットは&1; に設定します。  
  
 `hIcon`  
 ビットマップと、新しいイメージのマスクに含まれているアイコンのハンドル。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、最初の新しいイメージの 0 から始まるインデックスそれ以外の場合 – 1 です。  
  
### <a name="remarks"></a>コメント  
 関連付けが済んだら、アイコンのハンドルを外すを担当しています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CImageList&#1;](../../mfc/reference/codesnippet/cpp/cimagelist-class_1.cpp)]  
  
##  <a name="attach"></a>CImageList::Attach  
 イメージ リストをアタッチするには、この関数を呼び出す、`CImageList`オブジェクトです。  
  
```  
BOOL Attach(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>パラメーター  
 `hImageList`  
 イメージ リスト オブジェクトへのハンドル。  
  
### <a name="return-value"></a>戻り値  
 添付ファイルが正常に実行された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CImageList&#2;](../../mfc/reference/codesnippet/cpp/cimagelist-class_2.cpp)]  
  
##  <a name="begindrag"></a>CImageList::BeginDrag  
 イメージのドラッグを開始するには、この関数を呼び出します。  
  
```  
BOOL BeginDrag(
    int nImage,  
    CPoint ptHotSpot);
```  
  
### <a name="parameters"></a>パラメーター  
 `nImage`  
 ドラッグするイメージの&0; から始まるインデックス。  
  
 `ptHotSpot`  
 ドラッグの開始位置 (通常は、カーソル位置) の座標です。 座標は、イメージの左上隅を基準としました。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数では、ドラッグすることに使用される一時的なイメージ リストを作成します。 イメージは、現在のカーソルで指定されたイメージとマスクを結合します。 それ以降に応答`WM_MOUSEMOVE`、メッセージを使用してドラッグ イメージを行うことができます、`DragMove`メンバー関数。 ドラッグ操作を終了するには、使用することができます、`EndDrag`メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CImageList&#3;](../../mfc/reference/codesnippet/cpp/cimagelist-class_3.cpp)]  
  
##  <a name="cimagelist"></a>CImageList::CImageList  
 `CImageList` オブジェクトを構築します。  
  
```  
CImageList();
```  
  
##  <a name="copy"></a>CImageList::Copy  
 このメンバー関数は、Win32 関数の動作を実装して[ImageList_Copy](http://msdn.microsoft.com/library/windows/desktop/bb761520)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
BOOL Copy(
    int iDst,  
    int iSrc,  
    UINT uFlags = ILCF_MOVE);

 
BOOL Copy(
    int iDst,  
    CImageList* pSrc,  
    int iSrc,  
    UINT uFlags = ILCF_MOVE);
```  
  
### <a name="parameters"></a>パラメーター  
 *iDst*  
 コピー操作のコピー先として使用するイメージの&0; から始まるインデックス。  
  
 `iSrc`  
 コピー操作のソースとして使用するイメージの&0; から始まるインデックス。  
  
 `uFlags`  
 ビット フラグの値にするコピー操作の種類を指定します。 このパラメーターは、次の値のいずれかになります。  
  
|値|説明|  
|-----------|-------------|  
|`ILCF_MOVE`|ソース イメージは、コピー先の画像のインデックスにコピーされます。 この操作により、既存のイメージの複数のインスタンス。 `ILCF_MOVE` が既定値です。|  
|`ILCF_SWAP`|ソースとコピー先のイメージは、イメージ リスト内の位置を交換します。|  
  
 `pSrc`  
 ポインター、`CImageList`コピー操作の対象となっているオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CImageList&6;](../../mfc/reference/codesnippet/cpp/cimagelist-class_4.cpp)]  
  
##  <a name="create"></a>CImageList::Create  
 イメージ リストを初期化し、それを[CImageList](../../mfc/reference/cimagelist-class.md)オブジェクトです。  
  
```  
BOOL Create(
    int cx,  
    int cy,  
    UINT nFlags,  
    int nInitial,  
    int nGrow);

 
BOOL Create(
    UINT nBitmapID,  
    int cx,  
    int nGrow,  
    COLORREF crMask);

 
BOOL Create(
    LPCTSTR lpszBitmapID,  
    int cx,  
    int nGrow,  
    COLORREF crMask);

 
BOOL Create(
    CImageList& imagelist1,  
    int nImage1,  
    CImageList& imagelist2,  
    int nImage2,  
    int dx,  
    int dy);  
  
BOOL Create(CImageList* pImageList);
```  
  
### <a name="parameters"></a>パラメーター  
 `cx`  
 ピクセル単位で各イメージのサイズ。  
  
 `cy`  
 ピクセル単位で各イメージのサイズ。  
  
 `nFlags`  
 作成するイメージ リストの種類を指定します。 このパラメーターは、次の値の組み合わせを指定できますが、1 つだけを含めること、`ILC_COLOR`値。  
  
|値|説明|  
|-----------|-------------|  
|`ILC_COLOR`|その他の何もしない場合は、既定の動作を使用して`ILC_COLOR`* フラグを指定します。 既定値は、通常、 `ILC_COLOR4`; 既定では古いディスプレイ ドライバーが、`ILC_COLORDDB`です。|  
|`ILC_COLOR4`|イメージの一覧については、ビットマップとして 4 ビット (16 色) のデバイスに依存しないビットマップ (DIB) セクションを使用します。|  
|`ILC_COLOR8`|8 ビットの DIB セクションを使用します。 カラー テーブルに使用される色は、ハーフトーン パレットの色と同じです。|  
|`ILC_COLOR16`|16 ビット (32/64 k の色) の DIB セクションです。|  
|`ILC_COLOR24`|24 ビットの DIB セクションを使用します。|  
|`ILC_COLOR32`|32 ビットの DIB セクションを使用します。|  
|`ILC_COLORDDB`|デバイス依存ビットマップを使用します。|  
|`ILC_MASK`|マスクを使用します。 イメージ リストには、マスクとして使用されるモノクロ ビットマップは、うちの&1; つ、2 つのビットマップが含まれています。 この値が含まれない場合、イメージ リストには、1 つだけのビットマップが含まれています。 参照してください[はイメージ リストのイメージを描画](../../mfc/drawing-images-from-an-image-list.md)マスクされたイメージの詳細についてです。|  
  
 `nInitial`  
 イメージ リストが最初に格納されるイメージの数です。  
  
 `nGrow`  
 イメージ リストできます拡張を許可する、システムは、新しいイメージを格納するためにリストのサイズを変更する必要があるときにイメージの数。 このパラメーターは、サイズを変更したイメージ リストを含めることができる新しいイメージの数を表します。  
  
 `nBitmapID`  
 イメージ リストと関連付けられているビットマップのリソース Id です。  
  
 `crMask`  
 マスクの生成に使用される色。 黒に、各ピクセルを指定したビットマップにこの色を変更し、マスクの対応するビットは&1; に設定します。  
  
 `lpszBitmapID`  
 イメージのリソース Id を含む文字列。  
  
 `imagelist1`  
 `CImageList` オブジェクトへの参照。  
  
 `nImage1`  
 最初の既存のイメージのインデックス。  
  
 `imagelist2`  
 `CImageList` オブジェクトへの参照。  
  
 `nImage2`  
 2 つ目の既存のイメージのインデックス。  
  
 `dx`  
 最初の画像のピクセル単位でのリレーションシップにおける&2; 番目の画像の x 軸のオフセットします。  
  
 `dy`  
 最初の画像のピクセル単位でのリレーションシップにおける&2; 番目の画像の y 軸のオフセットします。  
  
 `pImageList`  
 ポインター、`CImageList`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 構築する、`CImageList`で&2; つの手順を実行します。 最初に、コンス トラクターを呼び出すし、まず`Create`、イメージ リストを作成およびそれにアタッチする、`CImageList`オブジェクトです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CImageList&#7;](../../mfc/reference/codesnippet/cpp/cimagelist-class_5.cpp)]  
  
##  <a name="deleteimagelist"></a>CImageList::DeleteImageList  
 イメージ リストを削除するには、この関数を呼び出します。  
  
```  
BOOL DeleteImageList();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CImageList&#8;](../../mfc/reference/codesnippet/cpp/cimagelist-class_6.cpp)]  
  
##  <a name="deletetempmap"></a>CImageList::DeleteTempMap  
 により自動的に呼び出さ、`CWinApp`アイドル ハンドラー`DeleteTempMap`一時的な削除`CImageList`によって作成されたオブジェクト[FromHandle](#fromhandle)、すべてのハンドルを破棄しません ( `hImageList`) に一時的に関連付けられている、 **ImageList**オブジェクトです。  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CImageList&#9;](../../mfc/reference/codesnippet/cpp/cimagelist-class_7.cpp)]  
  
##  <a name="detach"></a>CImageList::Detach  
 イメージ リスト オブジェクトをデタッチするには、この関数を呼び出して、`CImageList`オブジェクトです。  
  
```  
HIMAGELIST Detach();
```  
  
### <a name="return-value"></a>戻り値  
 イメージ リスト オブジェクトへのハンドル。  
  
### <a name="remarks"></a>コメント  
 この関数は、イメージ リストのオブジェクトへのハンドルを返します。  
  
### <a name="example"></a>例  
  例を参照してください[CImageList::Attach](#attach)します。  
  
##  <a name="dragenter"></a>CImageList::DragEnter  
 ドラッグ操作中にロックの更新で指定されたウィンドウを`pWndLock`で指定された位置にドラッグ イメージを表示および`point`です。  
  
```  
static BOOL PASCAL DragEnter(
    CWnd* pWndLock,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWndLock`  
 ドラッグ イメージを所有するウィンドウへのポインター。  
  
 `point`  
 ドラッグ イメージを表示する位置。 (クライアント領域ではなく) ウィンドウの左上隅に対する相対座標とは。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 座標は、座標を指定するときに枠線やタイトル バー、メニュー バーなどのウィンドウの要素の幅を補う必要がありますので、ウィンドウの左上隅を基準としました。  
  
 場合`pWndLock`は**NULL**、この関数は、デスクトップ ウィンドウに関連付けられている表示のコンテキストで、イメージを描画し、画面の左上隅に対する相対座標は、です。  
  
 この関数は、ドラッグ操作中に指定されたウィンドウにあるその他のすべての更新をロックします。 ドラッグ アンド ドロップ操作のターゲットを強調表示などのドラッグ操作中に描画を実行する必要がある場合は一時的に非表示にするドラッグされているイメージを使用して、[生じたとき](#dragleave)関数です。  
  
### <a name="example"></a>例  
  例を参照してください[CImageList::BeginDrag](#begindrag)します。  
  
##  <a name="dragleave"></a>生じたとき  
 指定されたウィンドウのロックを解除`pWndLock`し、ドラッグ イメージを更新するウィンドウを非表示にします。  
  
```  
static BOOL PASCAL DragLeave(CWnd* pWndLock);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWndLock`  
 ドラッグ イメージを所有するウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
  例を参照してください[CImageList::EndDrag](#enddrag)します。  
  
##  <a name="dragmove"></a>CImageList::DragMove  
 ドラッグ アンド ドロップ操作中にドラッグされているイメージを移動するには、この関数を呼び出します。  
  
```  
static BOOL PASCAL DragMove(CPoint pt);
```  
  
### <a name="parameters"></a>パラメーター  
 `pt`  
 新しい位置にドラッグします。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は通常に応えてと呼ばれる、`WM_MOUSEMOVE`メッセージです。 ドラッグ操作を開始するを使用して、`BeginDrag`メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CImageList&4;](../../mfc/reference/codesnippet/cpp/cimagelist-class_8.cpp)]  
  
##  <a name="dragshownolock"></a>CImageList::DragShowNolock  
 ドラッグ操作中にウィンドウをロックすることがなくドラッグ イメージの表示と非表示を切り替えます。  
  
```  
static BOOL PASCAL DragShowNolock(BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 `bShow`  
 ドラッグ イメージを表示するかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 [CImageList::DragEnter](#dragenter)関数は、ドラッグ操作中にウィンドウに対するすべての更新をロックします。 ただし、この関数では、ウィンドウはロックされません。  
  
##  <a name="draw"></a>:Draw  
 ドラッグ アンド ドロップ操作中にドラッグされているイメージを描画するには、この関数を呼び出します。  
  
```  
BOOL Draw(
    CDC* pDC,  
    int nImage,  
    POINT pt,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 コピー先デバイス コンテキストへのポインター。  
  
 `nImage`  
 描画するイメージの&0; から始まるインデックス。  
  
 `pt`  
 指定したデバイス コンテキスト内に描画する場所です。  
  
 `nStyle`  
 描画スタイルを指定するフラグします。 これらの値の&1; つ以上を指定できます。  
  
|値|説明|  
|-----------|-------------|  
|`ILD_BLEND25`、 **ILD_FOCUS**|システムの強調表示色を 25% を混合して、イメージを描画します。 イメージ リストには、マスクが含まれていない場合は、この値を指定しても効果はありません。|  
|`ILD_BLEND50`、 **ILD_SELECTED**、 **ILD_BLEND**|システムの強調表示色を 50% を混合して、イメージを描画します。 イメージ リストには、マスクが含まれていない場合は、この値を指定しても効果はありません。|  
|**ILD_MASK**|マスクを描画します。|  
|`ILD_NORMAL`|イメージ リストの背景色を使用してイメージを描画します。 背景色がある場合、`CLR_NONE`透過的にマスクを使用して値、イメージを描画します。|  
|`ILD_TRANSPARENT`|透過的に背景色に関係なく、マスクを使用して、イメージを描画します。|  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
  例を参照してください[CImageList::SetOverlayImage](#setoverlayimage)します。  
  
##  <a name="drawex"></a>CImageList::DrawEx  
 指定したデバイス コンテキストでのイメージ リストのアイテムを描画します。  
  
```  
BOOL DrawEx(
    CDC* pDC,  
    int nImage,  
    POINT pt,  
    SIZE sz,  
    COLORREF clrBk,  
    COLORREF clrFg,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 コピー先デバイス コンテキストへのポインター。  
  
 `nImage`  
 描画するイメージの&0; から始まるインデックス。  
  
 `pt`  
 指定したデバイス コンテキスト内に描画する場所です。  
  
 `sz`  
 イメージの左上隅に対して相対的に描画するイメージの部分のサイズ。 参照してください`dx`と*dy*で[ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536)で、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]*します。*  
  
 *clrBk*  
 イメージの背景色です。 参照してください*rgbBk*で[ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536)で、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]*します。*  
  
 *clrFg*  
 イメージの前景色。 参照してください*rgbFg*で[ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536)で、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]*します。*  
  
 `nStyle`  
 描画スタイルを指定するフラグします。 参照してください*は*で[ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536)で、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]*します。*  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 関数は、指定の描画スタイルを使用し、指定した色を使用してイメージを統合します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CImageList&#10;](../../mfc/reference/codesnippet/cpp/cimagelist-class_9.cpp)]  
  
##  <a name="drawindirect"></a>CImageList::DrawIndirect  
 イメージの一覧からイメージを描画するには、このメンバー関数を呼び出します。  
  
```  
BOOL DrawIndirect(IMAGELISTDRAWPARAMS* pimldp);

 
BOOL DrawIndirect(
    CDC* pDC,  
    int nImage,  
    POINT pt,  
    SIZE sz,  
    POINT ptOrigin,  
    UINT fStyle = ILD_NORMAL,  
    DWORD dwRop = SRCCOPY,  
    COLORREF rgbBack = CLR_DEFAULT,  
    COLORREF rgbFore = CLR_DEFAULT,  
    DWORD fState = ILS_NORMAL,  
    DWORD Frame = 0,  
    COLORREF crEffect = CLR_DEFAULT);
```  
  
### <a name="parameters"></a>パラメーター  
 *pimldp*  
 ポインター、[された](http://msdn.microsoft.com/library/windows/desktop/bb761395)描画操作に関する情報を格納する構造体。  
  
 `pDC`  
 コピー先デバイス コンテキストへのポインター。 これを削除する必要があります[CDC](../../mfc/reference/cdc-class.md)オブジェクトの操作が終了します。  
  
 `nImage`  
 描画するイメージの&0; から始まるインデックス。  
  
 `pt`  
 A[ポイント](http://msdn.microsoft.com/library/windows/desktop/dd162805)イメージを描画する x および y 座標を含む構造体。  
  
 `sz`  
 A[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)描画するイメージのサイズを示す構造体。  
  
 *ptOrigin*  
 A[ポイント](http://msdn.microsoft.com/library/windows/desktop/dd162805)イメージ自体を基準として描画操作の左上隅を指定する x および y 座標を含む構造体。 左側の指定した x 座標と y 座標の上に配置されているイメージのピクセルは描画されません。  
  
 `fStyle`  
 描画スタイルと、必要に応じて、オーバーレイのイメージを指定するフラグします。 オーバーレイのイメージの詳細については「解説」セクションを参照してください。 MFC の既定の実装`ILD_NORMAL`、イメージ リストの背景色を使用してイメージを描画します。 背景色がある場合、`CLR_NONE`マスクを透過的に使用する値、イメージを描画します。  
  
 可能なその他のスタイルは、「、**は**のメンバー、[された](http://msdn.microsoft.com/library/windows/desktop/bb761395)構造体。  
  
 *dwRop*  
 ラスター オペレーション コードを指定する値。 これらのコードでは、最終的な色を実現するために、移行先の四角形の色データの元の四角形の色データの結合方法を定義します。 MFC の既定の実装、 **SRCCOPY**元の四角形をコピー先の四角形に直接コピーします。 場合にこのパラメーターは無視、`fStyle`パラメーターは含まれません、 **ILD_ROP**フラグ。  
  
 他の有効値は、「、 **dwRop**のメンバー、[された](http://msdn.microsoft.com/library/windows/desktop/bb761395)構造体。  
  
 *rgbBack*  
 既定では、画像の背景色`CLR_DEFAULT`します。 このパラメーターには、アプリケーション定義の RGB 値または値は次のいずれかを指定できます。  
  
|値|説明|  
|-----------|-------------|  
|`CLR_DEFAULT`|既定の背景色。 イメージ リストの背景色を使用してイメージを描画します。|  
|`CLR_NONE`|背景色がありません。 イメージが透過的に描画します。|  
  
 *rgbFore*  
 既定では、前景色をイメージ`CLR_DEFAULT`します。 このパラメーターには、アプリケーション定義の RGB 値または値は次のいずれかを指定できます。  
  
|値|説明|  
|-----------|-------------|  
|`CLR_DEFAULT`|既定の前景の色。 前景色としてシステムの強調表示色を使用してイメージを描画します。|  
|`CLR_NONE`|ディザー カラーなし。 イメージは、コピー先デバイス コンテキストの色とブレンドされます。|  
  
 場合にのみ、このパラメーターは使用`fStyle`を含む、`ILD_BLEND25`または`ILD_BLEND50`フラグ。  
  
 *fState*  
 描画状態を指定するフラグを設定します。 このメンバーは、1 つまたは複数のイメージ リストの状態フラグを含めることができます。  
  
 *フレーム*  
 飽和とアルファ ブレンドの効果の動作に影響します。  
  
 使用すると**ILS_SATURATE**、このメンバーは、アイコン内の各ピクセルの RGB の組の各色コンポーネントに追加されている値を保持します。  
  
 使用すると**ILS_APLHA**、このメンバーは、アルファ チャネルに値を保持します。 この値は、0 から 255 で、0 が完全に透明、255 が完全に不透明に指定できます。  
  
 *crEffect*  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)光彩とシャドウ効果を使用する値。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**イメージが正常に描画された、それ以外の場合**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 Win32 構造を手動で入力する場合は、最初のバージョンを使用します。 MFC の既定の引数の&1; つ以上の利用または構造体を操作しないようにする場合は、2 番目のバージョンを使用します。  
  
 オーバーレイ イメージは、このメンバー関数で指定されたプライマリのイメージの上に描画される画像、`nImage`パラメーター。 使用してオーバーレイ マスクを描画、[描画](#draw)オーバーレイ マスクを使用して指定の&1; から始まるインデックスを持つメンバー関数、[から](http://msdn.microsoft.com/library/windows/desktop/bb761408)マクロです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CImageList&#11;](../../mfc/reference/codesnippet/cpp/cimagelist-class_10.cpp)]  
  
##  <a name="enddrag"></a>CImageList::EndDrag  
 ドラッグ操作を終了するには、この関数を呼び出します。  
  
```  
static void PASCAL EndDrag();
```  
  
### <a name="remarks"></a>コメント  
 ドラッグ操作を開始するを使用して、`BeginDrag`メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CImageList&#5;](../../mfc/reference/codesnippet/cpp/cimagelist-class_11.cpp)]  
  
##  <a name="extracticon"></a>CImageList::ExtractIcon  
 イメージとイメージ リストに関連するマスクに基づいてアイコンを作成するには、この関数を呼び出します。  
  
```  
HICON ExtractIcon(int nImage);
```  
  
### <a name="parameters"></a>パラメーター  
 `nImage`  
 イメージの&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、アイコンのハンドルそれ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 このメソッドでの動作に依存している、 [ImageList_ExtractIcon](http://msdn.microsoft.com/library/windows/desktop/bb761401)マクロをアイコンを作成します。 参照してください、 [ImageList_ExtractIcon](http://msdn.microsoft.com/library/windows/desktop/bb761401)用のマクロの詳細については、アイコンの作成と削除をします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CImageList&#12;](../../mfc/reference/codesnippet/cpp/cimagelist-class_12.cpp)]  
  
##  <a name="fromhandle"></a>CImageList::FromHandle  
 ポインターを返す、`CImageList`イメージ リストへのハンドルが指定されるとします。  
  
```  
static CImageList* PASCAL FromHandle(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>パラメーター  
 `hImageList`  
 イメージ リストを指定します。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CImageList`成功以外の場合は、オブジェクト**NULL**します。  
  
### <a name="remarks"></a>コメント  
 場合、`CImageList`ハンドルが一時的に既にアタッチされていない`CImageList`オブジェクトが作成され、接続されています。 この一時`CImageList`オブジェクトは、次回アプリケーションは、イベント ループでのアイドル時間を持つ、までれた時点ですべての一時オブジェクトは削除のみ有効です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CImageList&#13;](../../mfc/reference/codesnippet/cpp/cimagelist-class_13.cpp)]  
  
##  <a name="fromhandlepermanent"></a>CImageList::FromHandlePermanent  
 ポインターを返す、`CImageList`イメージ リストへのハンドルが指定されるとします。  
  
```  
static CImageList* PASCAL FromHandlePermanent(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>パラメーター  
 `hImageList`  
 イメージ リストを指定します。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CImageList`成功以外の場合は、オブジェクト**NULL**します。  
  
### <a name="remarks"></a>コメント  
 場合、`CImageList`オブジェクトは、ハンドルに関連付けられていない**NULL**が返されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CImageList&#14;](../../mfc/reference/codesnippet/cpp/cimagelist-class_14.cpp)]  
  
##  <a name="getbkcolor"></a>CImageList::GetBkColor  
 イメージ リストの現在の背景色を取得するには、この関数を呼び出します。  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 RGB 色の値の`CImageList`オブジェクトの背景色。  
  
### <a name="example"></a>例  
  例を参照してください[CImageList::SetBkColor](#setbkcolor)します。  
  
##  <a name="getdragimage"></a>CImageList::GetDragImage  
 ドラッグすることに使用される一時的なイメージ リストを取得します。  
  
```  
static CImageList* PASCAL GetDragImage(
    LPPOINT lpPoint,  
    LPPOINT lpPointHotSpot);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPoint`  
 アドレス、[ポイント](http://msdn.microsoft.com/library/windows/desktop/dd162805)を現在を受け取る構造体の位置にドラッグします。  
  
 *lpPointHotSpot*  
 アドレス、**ポイント**ドラッグ位置からドラッグ イメージのオフセットを受け取る構造体。  
  
### <a name="return-value"></a>戻り値  
 かどうかは成功すると、一時イメージへのポインターを一覧表示されるドラッグ; で使用それ以外の場合、 **NULL**します。  
  
##  <a name="getimagecount"></a>CImageList::GetImageCount  
 イメージ リスト内のイメージの数を取得するには、この関数を呼び出します。  
  
```  
int GetImageCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 イメージの数。  
  
### <a name="example"></a>例  
  例を参照してください[CImageList::ExtractIcon](#extracticon)します。  
  
##  <a name="getimageinfo"></a>CImageList::GetImageInfo  
 この関数では、イメージに関する情報を取得します。  
  
```  
BOOL GetImageInfo(
    int nImage,  
    IMAGEINFO* pImageInfo) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nImage`  
 イメージの&0; から始まるインデックス。  
  
 *pImageInfo*  
 ポインター、 [IMAGEINFO](http://msdn.microsoft.com/library/windows/desktop/bb761393)イメージに関する情報を受け取る構造体。 イメージのビットマップを直接操作は、この構造体の情報を使用できます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `IMAGEINFO`構造体には、イメージ リスト内のイメージに関する情報が含まれています。  
  
##  <a name="getsafehandle"></a>CImageList::GetSafeHandle  
 取得するには、この関数を呼び出して、 **m_hImageList**データ メンバーです。  
  
```  
HIMAGELIST GetSafeHandle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 は、接続されているイメージ リストへのハンドルそれ以外の場合**NULL**オブジェクトがアタッチされていない場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CImageList&#15;](../../mfc/reference/codesnippet/cpp/cimagelist-class_15.cpp)]  
  
##  <a name="m_himagelist"></a>CImageList::m_hImageList  
 このオブジェクトにアタッチされているイメージ リストのハンドル。  
  
 **HIMAGELIST m_hImageList です。**  
  
### <a name="remarks"></a>コメント  
 **M_hImageList**データ メンバーは型のパブリック変数`HIMAGELIST`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CImageList 第&23;](../../mfc/reference/codesnippet/cpp/cimagelist-class_16.cpp)]  
  
##  <a name="operator_himagelist"></a>CImageList::operator HIMAGELIST  
 この演算子を使用して、接続されているハンドルの取得、`CImageList`オブジェクトです。  
  
```  
operator HIMAGELIST() const;  
```  
  
### <a name="return-value"></a>戻り値  
 かどうかは成功すると、イメージ リストへのハンドルによって表される、`CImageList`オブジェクト。 それ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 この演算子はキャスト演算子の`HIMAGELIST`オブジェクトです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CImageList&#16;](../../mfc/reference/codesnippet/cpp/cimagelist-class_17.cpp)]  
  
##  <a name="read"></a>CImageList::Read  
 この関数では、アーカイブからのイメージ リストを読み込みます。  
  
```  
BOOL Read(CArchive* pArchive);
```  
  
### <a name="parameters"></a>パラメーター  
 `pArchive`  
 ポインター、`CArchive`イメージ リストが読み込まれる元となるオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CImageList&#18;](../../mfc/reference/codesnippet/cpp/cimagelist-class_18.cpp)]  
  
##  <a name="remove"></a>CImageList::Remove  
 イメージ リスト オブジェクトからイメージを削除するには、この関数を呼び出します。  
  
```  
BOOL Remove(int nImage);
```  
  
### <a name="parameters"></a>パラメーター  
 `nImage`  
 削除するイメージの&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 次のすべてのアイテム`nImage`下の&1; つの位置に移動するようになりました。 などのイメージ リストに&2; つの項目が含まれている場合の最初の項目を削除すると、最初の位置で今すぐに残りの項目。 `nImage`=&0; の最初の位置に項目を入力します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CImageList&#19;](../../mfc/reference/codesnippet/cpp/cimagelist-class_19.cpp)]  
  
##  <a name="replace"></a>CImageList::Replace  
 この関数では、新しいイメージをイメージ リスト内のイメージを置き換えます。  
  
```  
BOOL Replace(
    int nImage,  
    CBitmap* pbmImage,  
    CBitmap* pbmMask);

 
int Replace(
    int nImage,  
    HICON hIcon);
```  
  
### <a name="parameters"></a>パラメーター  
 `nImage`  
 置換するイメージの&0; から始まるインデックス。  
  
 `pbmImage`  
 イメージを含むビットマップへのポインター。  
  
 `pbmMask`  
 マスクを持つビットマップへのポインター。 イメージ リストとマスクを使用しない場合は、このパラメーターは無視されます。  
  
 `hIcon`  
 ビットマップと、新しいイメージのマスクに含まれているアイコンへのハンドル。  
  
### <a name="return-value"></a>戻り値  
 返すバージョン**BOOL**成功。 それ以外の場合 0 の場合は、0 以外を返します。  
  
 返すバージョン`int`成功した場合は – イメージの 0 から始まるインデックスを返す 1 です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を呼び出した後に呼び出して[呼び出す前](#setimagecount)プレース ホルダーを有効なイメージを割り当てるには、新しいには、イメージのインデックス番号。  
  
### <a name="example"></a>例  
  例を参照してください[CImageList::SetImageCount](#setimagecount)します。  
  
##  <a name="setbkcolor"></a>CImageList::SetBkColor  
 イメージ リストの背景色を設定するには、この関数を呼び出します。  
  
```  
COLORREF SetBkColor(COLORREF cr);
```  
  
### <a name="parameters"></a>パラメーター  
 `cr`  
 背景色を設定します。 できます`CLR_NONE`します。 その場合は、イメージが透過的にマスクを使用して描画されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、直前の背景色それ以外の場合`CLR_NONE`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CImageList&#20;](../../mfc/reference/codesnippet/cpp/cimagelist-class_20.cpp)]  
  
##  <a name="setdragcursorimage"></a>CImageList::SetDragCursorImage  
 現在のドラッグ イメージと指定したイメージ (通常はマウス カーソル イメージ) を組み合わせることによって、新しいドラッグ イメージを作成します。  
  
```  
BOOL SetDragCursorImage(
    int nDrag,  
    CPoint ptHotSpot);
```  
  
### <a name="parameters"></a>パラメーター  
 *nDrag*  
 ドラッグ イメージに対して結合される新しいイメージのインデックス。  
  
 `ptHotSpot`  
 新しいイメージ内のホット スポットの位置。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ドラッグの関数は、ドラッグ操作中に、新しいイメージを使用するため、Windows を使用する必要があります[ShowCursor](http://msdn.microsoft.com/library/windows/desktop/ms648396)関数を呼び出した後、実際のマウス カーソルを非表示に`CImageList::SetDragCursorImage`します。 それ以外の場合、システムは、ドラッグ操作の実行中の&2; つのマウス カーソルがあるように見える場合があります。  
  
##  <a name="setimagecount"></a>CImageList::SetImageCount  
 内のイメージの番号をリセットするには、このメンバー関数を呼び出す、`CImageList`オブジェクトです。  
  
```  
BOOL SetImageCount(UINT uNewCount);
```  
  
### <a name="parameters"></a>パラメーター  
 *uNewCount*  
 イメージ リストのイメージの新しいの合計数を指定する値。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 イメージ リストのイメージの数を増やすには、このメンバー関数を呼び出した場合、呼び出す[置換](#replace)に新しいインデックスを有効なイメージに割り当てる各追加のイメージにします。 有効なイメージに、インデックスの割り当てに失敗した場合は、新しいイメージを作成する描画操作は予測できません。  
  
 イメージ リストのサイズを小さくには、この関数を使用して、切り捨てられたイメージが解放されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CImageList #&21;](../../mfc/reference/codesnippet/cpp/cimagelist-class_21.cpp)]  
  
##  <a name="setoverlayimage"></a>CImageList::SetOverlayImage  
 オーバーレイ マスクとして使用するイメージの一覧にイメージの&0; から始まるインデックスを追加するには、この関数を呼び出します。  
  
```  
BOOL SetOverlayImage(
    int nImage,  
    int nOverlay);
```  
  
### <a name="parameters"></a>パラメーター  
 `nImage`  
 オーバーレイ マスクとして使用するイメージの&0; から始まるインデックス。  
  
 *nOverlay*  
 オーバーレイ マスクの&1; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 一覧には、最大で&4; つのインデックスを追加できます。  
  
 オーバーレイ マスクは、別のイメージ上に透過的に描画されるイメージです。 使用してイメージ上のオーバーレイ マスクを描画、 [:draw](#draw)オーバーレイ マスクを使用して指定の&1; から始まるインデックスを持つメンバー関数、**から**マクロです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CImageList #&22;](../../mfc/reference/codesnippet/cpp/cimagelist-class_22.cpp)]  
  
##  <a name="write"></a>CImageList::Write  
 イメージ リスト オブジェクトをアーカイブに書き込むには、この関数を呼び出します。  
  
```  
BOOL Write(CArchive* pArchive);
```  
  
### <a name="parameters"></a>パラメーター  
 `pArchive`  
 ポインター、`CArchive`イメージ リストが格納されるオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CImageList&17;](../../mfc/reference/codesnippet/cpp/cimagelist-class_23.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CListCtrl クラス](../../mfc/reference/clistctrl-class.md)   
 [CTabCtrl クラス](../../mfc/reference/ctabctrl-class.md)

