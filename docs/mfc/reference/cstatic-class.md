---
title: "CStatic クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStatic
dev_langs:
- C++
helpviewer_keywords:
- enhanced metafiles
- cursors, displaying
- static controls
- controls [MFC], static
- icons, displaying
- CStatic class
- enhanced metafiles, displaying
- bitmaps, displaying
ms.assetid: e7c94cd9-5ebd-428a-aa30-b3e51f8efb95
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
ms.openlocfilehash: 0209fad1b84b782cdec7927cb5a04e9bb3083d64
ms.lasthandoff: 02/24/2017

---
# <a name="cstatic-class"></a>CStatic クラス
Windows のスタティック コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CStatic : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CStatic::CStatic](#cstatic)|`CStatic` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CStatic::Create](#create)|Windows のスタティック コントロールを作成し、それをアタッチ、`CStatic`オブジェクトです。|  
|[CStatic::DrawItem](#drawitem)|オーナー描画のスタティック コントロールを描画するためにオーバーライドします。|  
|[CStatic::GetBitmap](#getbitmap)|以前、ビットマップのハンドルを取得[SetBitmap](#setbitmap)します。|  
|[CStatic::GetCursor](#getcursor)|カーソルのイメージのハンドルが以前に設定と取得[以前](#setcursor)します。|  
|[CStatic::GetEnhMetaFile](#getenhmetafile)|以前の拡張メタファイルのハンドルを取得[SetEnhMetaFile](#setenhmetafile)します。|  
|[CStatic::GetIcon](#geticon)|既に設定アイコンのハンドルを取得[SetIcon](#seticon)します。|  
|[CStatic::SetBitmap](#setbitmap)|静的コントロールに表示されるビットマップを指定します。|  
|[CStatic::SetCursor](#setcursor)|静的コントロールに表示されるカーソルのイメージを指定します。|  
|[CStatic::SetEnhMetaFile](#setenhmetafile)|静的コントロールに表示される拡張メタファイルを指定します。|  
|[CStatic::SetIcon](#seticon)|静的コントロールに表示されるアイコンを指定します。|  
  
## <a name="remarks"></a>コメント  
 静的コントロールでは、テキスト文字列、ボックス、四角形、アイコン、カーソル、ビットマップ、または拡張メタファイルを表示します。 これは、ラベル付け、ボックス、またはその他のコントロールを個別に使用できます。 静的コントロールは通常の入力を受け取らないし、用意されていません。使用して作成された場合に、マウス クリックの親に通知、ただし、 **SS_NOTIFY**スタイル。  
  
 2 つの手順では、スタティック コントロールを作成します。 最初に、構築するコンス トラクターを呼び出し、`CStatic`オブジェクトを呼び出し、[作成](#create)静的コントロールを作成し、アタッチして、メンバー関数、`CStatic`オブジェクトです。  
  
 作成する場合、 `CStatic` (ダイアログ リソースの場合) を使ってダイアログ ボックス内のオブジェクト、`CStatic`ダイアログ ボックスを閉じたときに、オブジェクトが自動的に破棄されます。  
  
 作成する場合、`CStatic`ウィンドウ内でオブジェクトを破棄しても必要があります。 A`CStatic`ウィンドウ内のスタック上に作成されたオブジェクトが自動的に破棄されます。 作成する場合、`CStatic`を使用して、ヒープ上のオブジェクト、**新しい**関数を呼び出す必要があります**削除**オブジェクトを破棄しての操作が終了します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CStatic`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="a-namecreatea--cstaticcreate"></a><a name="create"></a>CStatic::Create  
 Windows のスタティック コントロールを作成し、それをアタッチ、`CStatic`オブジェクトです。  
  
```  
virtual BOOL Create(
    LPCTSTR lpszText,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID = 0xffff);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszText`  
 コントロール内に配置するテキストを指定します。 場合**NULL**テキストは表示されません。  
  
 `dwStyle`  
 静的コントロールのウィンドウ スタイルを指定します。 任意の組み合わせを適用[静的コントロール スタイル](../../mfc/reference/static-styles.md)コントロールにします。  
  
 `rect`  
 スタティック コントロールのサイズと位置を指定します。 いずれかになります、`RECT`構造体、または`CRect`オブジェクトです。  
  
 `pParentWnd`  
 指定、`CStatic`親ウィンドウを通常、`CDialog`オブジェクトです。 ことはできません**NULL**します。  
  
 `nID`  
 静的コントロールのコントロール ID を指定します  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 構築、 `CStatic`&2; つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出す`CStatic`、し、呼び出す**作成**、Windows のスタティック コントロールを作成およびそれにアタッチする、`CStatic`オブジェクトです。  
  
 次の適用[ウィンドウ スタイル](../../mfc/reference/window-styles.md)静的コントロールにします。  
  
- **WS_CHILD**常に  
  
- **WS_VISIBLE**通常  
  
- **WS_DISABLED**ことはほとんどありません  
  
 静的コントロールで、ビットマップ、カーソル、アイコン、またはメタファイルを表示する場合は、次のいずれかを適用する必要があります[静的コントロール スタイル](../../mfc/reference/static-styles.md):  
  
- **SS_BITMAP**ビットマップにこのスタイルを使用します。  
  
- **SS_ICON**カーソルおよびアイコンのスタイルを使用します。  
  
- **SS_ENHMETAFILE**拡張メタファイルにこのスタイルを使用します。  
  
 カーソル、ビットマップ、アイコンのも、次のスタイルを使用する可能性があります。  
  
- **SS_CENTERIMAGE**静的コントロールにイメージを中央に使用します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatic&#1;](../../mfc/reference/codesnippet/cpp/cstatic-class_1.cpp)]  
  
##  <a name="a-namecstatica--cstaticcstatic"></a><a name="cstatic"></a>CStatic::CStatic  
 `CStatic` オブジェクトを構築します。  
  
```  
CStatic();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatic&#2;](../../mfc/reference/codesnippet/cpp/cstatic-class_2.cpp)]  
  
##  <a name="a-namedrawitema--cstaticdrawitem"></a><a name="drawitem"></a>CStatic::DrawItem  
 オーナー描画のスタティック コントロールを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpDrawItemStruct`  
 ポインター、 [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md)構造体。 構造体には、描画される項目と必要な図面の種類に関する情報が含まれています。  
  
### <a name="remarks"></a>コメント  
 オーナー描画の描画を実装するには、この関数をオーバーライド**CStatic**オブジェクト (コントロールにスタイルがある**SS_OWNERDRAW**)。  
  
##  <a name="a-namegetbitmapa--cstaticgetbitmap"></a><a name="getbitmap"></a>CStatic::GetBitmap  
 以前、ビットマップのハンドルを取得[SetBitmap](#setbitmap)、つまりに関連付けられている`CStatic`します。  
  
```  
HBITMAP GetBitmap() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のビットマップを識別するハンドルまたは**NULL**ビットマップが設定されていない場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatic&#3;](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]  
  
##  <a name="a-namegetcursora--cstaticgetcursor"></a><a name="getcursor"></a>CStatic::GetCursor  
 以前、カーソルのハンドルを取得[以前](#setcursor)、つまりに関連付けられている`CStatic`します。  
  
```  
HCURSOR GetCursor();
```  
  
### <a name="return-value"></a>戻り値  
 現在のカーソルのハンドルまたは**NULL**カーソルが設定されていない場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatic&4;](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]  
  
##  <a name="a-namegetenhmetafilea--cstaticgetenhmetafile"></a><a name="getenhmetafile"></a>CStatic::GetEnhMetaFile  
 以前は、拡張メタファイルのハンドルを取得[SetEnhMetafile](#setenhmetafile)、つまりに関連付けられている`CStatic`します。  
  
```  
HENHMETAFILE GetEnhMetaFile() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の拡張メタファイルを識別するハンドルまたは**NULL**拡張メタファイルが設定されていない場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatic&#5;](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]  
  
##  <a name="a-namegeticona--cstaticgeticon"></a><a name="geticon"></a>CStatic::GetIcon  
 以前のアイコンのハンドルを取得[SetIcon](#seticon)、つまりに関連付けられている`CStatic`します。  
  
```  
HICON GetIcon() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のアイコンを識別するハンドルまたは**NULL**アイコンが設定されていない場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatic&6;](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]  
  
##  <a name="a-namesetbitmapa--cstaticsetbitmap"></a><a name="setbitmap"></a>CStatic::SetBitmap  
 静的コントロールには、新しいビットマップを関連付けます。  
  
```  
HBITMAP SetBitmap(HBITMAP hBitmap);
```  
  
### <a name="parameters"></a>パラメーター  
 `hBitmap`  
 静的コントロールに描画されるビットマップのハンドル。  
  
### <a name="return-value"></a>戻り値  
 静的コントロールに既に関連付けられているビットマップのハンドルまたは`NULL`静的コントロールに関連付けられたビットマップがない場合。  
  
### <a name="remarks"></a>コメント  
 ビットマップは、静的コントロールに自動的に描画されます。 既定では、左上隅に描画され、スタティック コントロールは、ビットマップのサイズを変更する場合は。  
  
 さまざまなウィンドウや静的コントロール スタイルを次のように使用できます。  
  
-   SS_BITMAP は、ビットマップを常にこのスタイルを使用します。  
  
-   静的コントロールにイメージを中央に SS_CENTERIMAGE に使用します。 静的コントロールよりも大きい場合は、イメージはクリップされます。 静的コントロールより小さい場合は、ビットマップの左上隅にあるピクセルの色によってイメージの周囲の空白領域が入力されます。  
  
-   MFC クラスを提供する`CBitmap`はより、Win32 呼び出しよりも、ビットマップ イメージに機能する必要があるときに使用できる`LoadBitmap`です。 `CBitmap`、協力を得てでよく使用されて、GDI オブジェクトの&1; つの種類が含まれています`CStatic`、これは、`CWnd`スタティック コントロールとしてグラフィック オブジェクトを表示するために使用されるクラスです。  
  
 `CImage`デバイス独立ビットマップ (DIB) を簡単に処理することができます、ATL と MFC クラス。 詳細については、次を参照してください。 [CImage クラス](../../atl-mfc-shared/reference/cimage-class.md)します。  
  
-   一般的な使用量を提供する`CStatic::SetBitmap`の HBITMAP 演算子によって返される GDI オブジェクト、`CBitmap`または`CImage`オブジェクトです。 これを行うコードでは、次の行に似ています。  
  
```  
MyStaticControl.SetBitmap(HBITMAP(MyBitmap));
```  
次の例では、2 つ作成されます`CStatic`ヒープのオブジェクト。 使用してシステム ビットマップに&1; つを次に、`CBitmap::LoadOEMBitmap`とを使用してファイルから、その他の`CImage::Load`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatic&#3;](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]  
  
##  <a name="a-namesetcursora--cstaticsetcursor"></a><a name="setcursor"></a>CStatic::SetCursor  
 静的のコントロールに新しいカーソル イメージを関連付けます。  
  
```  
HCURSOR SetCursor(HCURSOR hCursor);
```  
  
### <a name="parameters"></a>パラメーター  
 `hCursor`  
 静的コントロールに描画されるカーソルのハンドル。  
  
### <a name="return-value"></a>戻り値  
 関連付けられたカーソルのハンドルまたは**NULL**静的コントロールに関連付けられたカーソルがない場合。  
  
### <a name="remarks"></a>コメント  
 カーソルは静的コントロールに自動的に描画されます。 既定では、左上隅に描画され、スタティック コントロールは、カーソルのサイズを変更する場合は。  
  
 さまざまなウィンドウや静的コントロール スタイルを以下を使用することができます。  
  
- **SS_ICON**カーソル、アイコン、常にこのスタイルを使用します。  
  
- **SS_CENTERIMAGE**スタティック コントロールの中央に使用します。 静的コントロールよりも大きい場合は、イメージはクリップされます。 静的コントロールより小さい場合は、スタティック コントロールの背景色とイメージの周囲の空白領域が入力されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatic&4;](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]  
  
##  <a name="a-namesetenhmetafilea--cstaticsetenhmetafile"></a><a name="setenhmetafile"></a>CStatic::SetEnhMetaFile  
 新しい拡張メタファイル イメージを静的コントロールに関連付けます。  
  
```  
HENHMETAFILE SetEnhMetaFile(HENHMETAFILE hMetaFile);
```  
  
### <a name="parameters"></a>パラメーター  
 `hMetaFile`  
 静的コントロールに描画するメタファイルのハンドル。  
  
### <a name="return-value"></a>戻り値  
 関連付けられた拡張メタファイルのハンドルまたは**NULL**静的コントロールに関連付けられた拡張メタファイルがない場合。  
  
### <a name="remarks"></a>コメント  
 拡張メタファイルは静的コントロールに自動的に描画されます。 拡張メタファイルは静的コントロールのサイズに合わせてスケーリングされます。  
  
 さまざまなウィンドウや静的コントロール スタイルを以下を使用することができます。  
  
- **SS_ENHMETAFILE**拡張メタファイルで常にこのスタイルを使用します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatic&#5;](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]  
  
##  <a name="a-nameseticona--cstaticseticon"></a><a name="seticon"></a>CStatic::SetIcon  
 静的のコントロールに新しいアイコン イメージを関連付けます。  
  
```  
HICON SetIcon(HICON hIcon);
```  
  
### <a name="parameters"></a>パラメーター  
 `hIcon`  
 静的コントロールに描画されるアイコンのハンドル。  
  
### <a name="return-value"></a>戻り値  
 関連付けられたアイコンのハンドルまたは**NULL**静的コントロールに関連付けられたアイコンがない場合。  
  
### <a name="remarks"></a>コメント  
 アイコンは、静的コントロールに自動的に描画されます。 既定では、左上隅に描画され、スタティック コントロールは、アイコンのサイズを変更する場合は。  
  
 さまざまなウィンドウや静的コントロール スタイルを以下を使用することができます。  
  
- **SS_ICON**カーソル、アイコン、常にこのスタイルを使用します。  
  
- **SS_CENTERIMAGE**スタティック コントロールの中央に使用します。 静的コントロールよりも大きい場合は、イメージはクリップされます。 静的コントロールより小さい場合は、スタティック コントロールの背景色とイメージの周囲の空白領域が入力されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CStatic&6;](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [CButton クラス](../../mfc/reference/cbutton-class.md)   
 [CComboBox クラス](../../mfc/reference/ccombobox-class.md)   
 [CEdit クラス](../../mfc/reference/cedit-class.md)   
 [CListBox クラス](../../mfc/reference/clistbox-class.md)   
 [CScrollBar クラス](../../mfc/reference/cscrollbar-class.md)   
 [CDialog クラス](../../mfc/reference/cdialog-class.md)

