---
title: "CRgn クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRgn"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HRGN"
  - "CRgn クラス"
  - "MFC の領域"
ms.assetid: d904da84-76aa-481e-8780-b09485f49e64
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CRgn クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows のグラフィック デバイス インターフェイス (GDI) の領域をカプセル化したものです。  
  
## <a name="syntax"></a>構文  
  
```  
class CRgn : public CGdiObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CRgn::CRgn](#crgn__crgn)|`CRgn` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRgn::CombineRgn](#crgn__combinergn)|セット、 `CRgn` オブジェクトを指定した 2 つの共用体に同等である `CRgn` オブジェクトです。|  
|[CRgn::CopyRgn](#crgn__copyrgn)|セット、 `CRgn` オブジェクトは指定したコピーを `CRgn` オブジェクトです。|  
|[CRgn::CreateEllipticRgn](#crgn__createellipticrgn)|初期化、 `CRgn` 楕円の領域を持つオブジェクト。|  
|[CRgn::CreateEllipticRgnIndirect](#crgn__createellipticrgnindirect)|初期化、 `CRgn` によって定義される楕円形の領域を持つオブジェクト、 [RECT](RECT%20Structure1.md) 構造体。|  
|[CRgn::CreateFromData](#crgn__createfromdata)|指定された領域と変換のデータから領域を作成します。|  
|[CRgn::CreateFromPath](#crgn__createfrompath)|指定したデバイス コンテキストに選択されているパスからの領域を作成します。|  
|[CRgn::CreatePolygonRgn](#crgn__createpolygonrgn)|初期化、 `CRgn` 多角形の領域を持つオブジェクト。 システム多角形自動的に閉じます、必要に応じて、最初最後の頂点から線が描画します。|  
|[CRgn::CreatePolyPolygonRgn](#crgn__createpolypolygonrgn)|初期化、 `CRgn` 、一連の閉じた多角形で構成される領域を持つオブジェクト。 多角形、切り離されたか、重なる可能性があります。|  
|[CRgn::CreateRectRgn](#crgn__createrectrgn)|初期化、 `CRgn` 四角形の領域を持つオブジェクト。|  
|[CRgn::CreateRectRgnIndirect](#crgn__createrectrgnindirect)|初期化、 `CRgn` によって定義された四角形の領域を持つオブジェクト、 [RECT](RECT%20Structure1.md) 構造体。|  
|[CRgn::CreateRoundRectRgn](#crgn__createroundrectrgn)|初期化、 `CRgn` 角の丸い四角形の領域を持つオブジェクト。|  
|[CRgn::EqualRgn](#crgn__equalrgn)|2 つ `CRgn` オブジェクトが等しいかどうかを決定します。|  
|[CRgn::FromHandle](#crgn__fromhandle)|ポインターを返す、 `CRgn` Windows 領域へのハンドルが指定されるとします。|  
|[CRgn::GetRegionData](#crgn__getregiondata)|指定された領域を示すデータを指定したバッファーに格納します。|  
|[CRgn::GetRgnBox](#crgn__getrgnbox)|外接する四角形の座標を取得、 `CRgn` オブジェクトです。|  
|[CRgn::OffsetRgn](#crgn__offsetrgn)|移動、 `CRgn` 指定されたオフセットでのオブジェクト。|  
|[CRgn::PtInRegion](#crgn__ptinregion)|指定した点がリージョンにするかどうかを判断します。|  
|[CRgn::RectInRegion](#crgn__rectinregion)|指定した四角形の任意の部分が、領域の境界内かどうかを判断します。|  
|[CRgn::SetRectRgn](#crgn__setrectrgn)|セット、 `CRgn` オブジェクトを指定した四角形領域。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CRgn::operator HRGN](#crgn__operator_hrgn)|含まれる Windows ハンドルを返す、 `CRgn` オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 領域は、ウィンドウ内での楕円形または多角形領域です。 クラスのメンバー関数を使用する領域を使用して、 `CRgn` クラスのメンバーとして定義されているクリッピング関数と `CDC`です。  
  
 メンバー関数は、 `CRgn` を作成、変更、および呼び出される領域オブジェクトに関する情報を取得します。  
  
 使用する方法について `CRgn`, を参照してください [グラフィック オブジェクト](../../mfc/graphic-objects.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CRgn`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="a-namecrgncombinergna-crgncombinergn"></a><a name="crgn__combinergn"></a>  CRgn::CombineRgn  
 既存の 2 つの領域を組み合わせることによって、新しい GDI 領域を作成します。  
  
```  
int CombineRgn(
    CRgn* pRgn1,  
    CRgn* pRgn2,  
    int nCombineMode);
```  
  
### <a name="parameters"></a>パラメーター  
 `pRgn1`  
 既存の領域を識別します。  
  
 `pRgn2`  
 既存の領域を識別します。  
  
 `nCombineMode`  
 2 つの領域を結合するときに実行する操作を指定します。 次の値のいずれかを指定できます。  
  
- **RGN_AND** (積集合) の両方のリージョンが重複する領域を使用します。  
  
- **RGN_COPY** リージョン 1 のコピーを作成 (で識別される `pRgn1`)。  
  
- **RGN_DIFF** 領域 1 の部分から成る領域を作成する (で識別される `pRgn1`) 領域 2 の一部ではない (で識別される `pRgn2`)。  
  
- **RGN_OR** 全体 (union) の両方の領域を結合します。  
  
- **RGN_XOR** 両方のリージョンを組み合わせたものですが重複する領域を削除します。  
  
### <a name="return-value"></a>戻り値  
 結果として得られる領域の種類を指定します。 次の値のいずれかを指定できます。  
  
- **COMPLEXREGION** 新しい領域には罫線を重複しています。  
  
- **エラー** 新しい領域は作成します。  
  
- **NULLREGION** 新しい領域が空です。  
  
- **SIMPLEREGION** 新しい領域には、重複する境界がありません。  
  
### <a name="remarks"></a>コメント  
 領域は結合の指定に従って `nCombineMode`します。  
  
 2 つの領域は組み合わされ、結果として得られる領域ハンドルに格納されている、 `CRgn` オブジェクトです。 どのような領域に格納されるため、 `CRgn` オブジェクトは、結合された領域で置き換えられます。  
  
 領域のサイズが 32,767 で 32,767 の論理ユニット、またはメモリの 64 K に制限は、どちらか小さい方です。  
  
 使用 [CopyRgn](#crgn__copyrgn) 単に 1 つの領域を別のリージョンにコピーします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#144](../../mfc/codesnippet/CPP/crgn-class_1.cpp)]  
  
##  <a name="a-namecrgncopyrgna-crgncopyrgn"></a><a name="crgn__copyrgn"></a>  CRgn::CopyRgn  
 によって定義される領域をコピー `pRgnSrc` に、 `CRgn` オブジェクトです。  
  
```  
int CopyRgn(CRgn* pRgnSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 `pRgnSrc`  
 既存の領域を識別します。  
  
### <a name="return-value"></a>戻り値  
 結果として得られる領域の種類を指定します。 次の値のいずれかを指定できます。  
  
- **COMPLEXREGION** 新しい領域には罫線を重複しています。  
  
- **エラー** 新しい領域は作成します。  
  
- **NULLREGION** 新しい領域が空です。  
  
- **SIMPLEREGION** 新しい領域には、重複する境界がありません。  
  
### <a name="remarks"></a>コメント  
 新しい領域に格納されていた領域を置換する、 `CRgn` オブジェクトです。 この関数の特殊なケースは、 [CombineRgn](#crgn__combinergn) メンバー関数。  
  
### <a name="example"></a>例  
  例を参照してください [CRgn::CreateEllipticRgn](#crgn__createellipticrgn)します。  
  
##  <a name="a-namecrgncreateellipticrgna-crgncreateellipticrgn"></a><a name="crgn__createellipticrgn"></a>  CRgn::CreateEllipticRgn  
 楕円の領域を作成します。  
  
```  
BOOL CreateEllipticRgn(
    int x1,  
    int y1,  
    int x2,  
    int y2);
```  
  
### <a name="parameters"></a>パラメーター  
 `x1`  
 論理で楕円の外接する四角形の左上隅の x 座標を指定します。  
  
 `y1`  
 論理で楕円の外接する四角形の左上隅の y 座標を指定します。  
  
 `x2`  
 論理で楕円の外接する四角形の右下隅の x 座標を指定します。  
  
 `y2`  
 論理で楕円の外接する四角形の右下隅の y 座標を指定します。  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 指定された外接する四角形によって定義領域 `x1`, 、`y1`, 、`x2`, 、および `y2`です。 領域は、 `CRgn` オブジェクトです。  
  
 領域のサイズが 32,767 で 32,767 の論理ユニット、またはメモリの 64 K に制限は、どちらか小さい方です。  
  
 作成された領域の使用の終了時、 `CreateEllipticRgn` 関数の場合、アプリケーションは、デバイス コンテキストを使用するのリージョンを選択する必要があります、 `DeleteObject` 関数を削除します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#145](../../mfc/codesnippet/CPP/crgn-class_2.cpp)]  
  
##  <a name="a-namecrgncreateellipticrgnindirecta-crgncreateellipticrgnindirect"></a><a name="crgn__createellipticrgnindirect"></a>  CRgn::CreateEllipticRgnIndirect  
 楕円の領域を作成します。  
  
```  
BOOL CreateEllipticRgnIndirect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、 `RECT` 構造体、または `CRect` 楕円の外接する四角形の左上隅および右下隅の論理座標を格納しているオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 構造体またはによって指されるオブジェクトによって、領域が定義されている `lpRect` に格納されて、 `CRgn` オブジェクトです。  
  
 領域のサイズが 32,767 で 32,767 の論理ユニット、またはメモリの 64 K に制限は、どちらか小さい方です。  
  
 作成された領域の使用の終了時、 `CreateEllipticRgnIndirect` 関数の場合、アプリケーションは、デバイス コンテキストを使用するのリージョンを選択する必要があります、 `DeleteObject` 関数を削除します。  
  
### <a name="example"></a>例  
  例を参照してください [CRgn::CreateRectRgnIndirect](#crgn__createrectrgnindirect)します。  
  
##  <a name="a-namecrgncreatefromdataa-crgncreatefromdata"></a><a name="crgn__createfromdata"></a>  CRgn::CreateFromData  
 指定された領域と変換のデータから領域を作成します。  
  
```  
BOOL CreateFromData(
    const XFORM* lpXForm,  
    int nCount,  
    const RGNDATA* pRgnData);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpXForm*  
 指す、 [XFORM](../../mfc/reference/xform-structure.md) 領域で実行する変換を定義するデータ構造です。 このポインターが場合 **NULL**, 、識別情報の変換を使用します。  
  
 `nCount`  
 指すバイト数を指定 `pRgnData`します。  
  
 `pRgnData`  
 指す、 [RGNDATA](../../mfc/reference/rgndata-structure.md) 地域のデータを格納するデータ構造です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションでは、地域のデータを呼び出すことによって取得できます、 `CRgn::GetRegionData` 関数です。  
  
##  <a name="a-namecrgncreatefrompatha-crgncreatefrompath"></a><a name="crgn__createfrompath"></a>  CRgn::CreateFromPath  
 指定したデバイス コンテキストに選択されているパスからの領域を作成します。  
  
```  
BOOL CreateFromPath(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 閉じたパスを格納しているデバイス コンテキストを識別します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 識別されるデバイス コンテキスト、 `pDC` パラメーターは、閉じたパスを含める必要があります。 後 `CreateFromPath` 領域、Windows をパスに変換がデバイス コンテキストから閉じたパスを破棄します。  
  
##  <a name="a-namecrgncreatepolygonrgna-crgncreatepolygonrgn"></a><a name="crgn__createpolygonrgn"></a>  CRgn::CreatePolygonRgn  
 多角形の領域を作成します。  
  
```  
BOOL CreatePolygonRgn(
    LPPOINT lpPoints,  
    int nCount,  
    int nMode);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPoints`  
 配列を指す **ポイント** 構造体や配列の `CPoint` オブジェクトです。 各構造体は、x 座標と y 座標、多角形の頂点を 1 つの値を指定します。  **ポイント** 構造体には、次の形式。  
  
 `typedef struct tagPOINT {`  
  
 `int x;`  
  
 `int y;`  
  
 `} POINT;`  
  
 `nCount`  
 数を指定 **ポイント** 構造体または `CPoint` が配列内のオブジェクトが指す `lpPoints`します。  
  
 `nMode`  
 領域の塗りつぶしモードを指定します。 このパラメーターは、いずれかを指定できます **代替** または **ワインディング**します。  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 システム多角形自動的に閉じます、必要に応じて、最初最後の頂点から線が描画します。 結果として得られる領域に格納、 `CRgn` オブジェクトです。  
  
 領域のサイズが 32,767 で 32,767 の論理ユニット、またはメモリの 64 K に制限は、どちらか小さい方です。  
  
 多角形の塗りつぶしモードのときは **代替**, 、システムは、各スキャン ラインに奇数し、偶数の多角形の辺の間で領域を塗りつぶします。 つまり、システムは、最初と 2 番目の側の間で、3 番目と 4 番目の側との間の領域を塗りつぶします。  
  
 多角形の塗りつぶしモードのときは **ワインディング**, 、システムは、図が描いた領域を入力するかどうかを判断する方向を使用します。 多角形の場合は、各直線セグメントは、時計回りまたは反時計回りのいずれかに表示されます。 閉じた領域から図形の外側に描画架空の線が時計回りの直線セグメントを通過するたびに、カウントがインクリメントされます。 行が反時計回りに回転線セグメントを経過すると、カウントがデクリメントします。 図形の外側の行に達したら、カウントがゼロ以外の領域に入力されます。  
  
 アプリケーションが終了した場合に作成された領域を使用して、 `CreatePolygonRgn` 関数の場合、デバイス コンテキストのリージョンを選択する必要があります、 `DeleteObject` 関数を削除します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#146](../../mfc/codesnippet/CPP/crgn-class_3.cpp)]  
  
##  <a name="a-namecrgncreatepolypolygonrgna-crgncreatepolypolygonrgn"></a><a name="crgn__createpolypolygonrgn"></a>  CRgn::CreatePolyPolygonRgn  
 一連の閉じた多角形で構成される領域を作成します。  
  
```  
BOOL CreatePolyPolygonRgn(
    LPPOINT lpPoints,  
    LPINT lpPolyCounts,  
    int nCount,  
    int nPolyFillMode);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPoints`  
 配列を指す **ポイント** 構造体や配列の `CPoint` 多角形の頂点を定義するオブジェクト。 システムは自動的には閉じないために、各多角形を明示的に閉じる必要があります。 多角形が連続的に指定します。  **ポイント** 構造体には、次の形式。  
  
 `typedef struct tagPOINT {`  
  
 `int x;`  
  
 `int y;`  
  
 `} POINT;`  
  
 `lpPolyCounts`  
 整数の配列を指します。 最初の整数の最初の多角形の頂点の数を指定する、 `lpPoints` 、2 番目の整数の配列が 2 つ目の多角形の頂点の数を指定します。  
  
 `nCount`  
 指定の整数値の合計数、 `lpPolyCounts` 配列。  
  
 `nPolyFillMode`  
 多角形の塗りつぶしモードを指定します。 この値は、いずれかの **代替** または **ワインディング**します。  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 結果として得られる領域に格納、 `CRgn` オブジェクトです。  
  
 多角形、切り離されたか、重なる可能性があります。  
  
 領域のサイズが 32,767 で 32,767 の論理ユニット、またはメモリの 64 K に制限は、どちらか小さい方です。  
  
 多角形の塗りつぶしモードのときは **代替**, 、システムは、各スキャン ラインに奇数し、偶数の多角形の辺の間で領域を塗りつぶします。 つまり、システムは、最初と 2 番目の側の間で、3 番目と 4 番目の側との間の領域を塗りつぶします。  
  
 多角形の塗りつぶしモードのときは **ワインディング**, 、システムは、図が描いた領域を入力するかどうかを判断する方向を使用します。 多角形の場合は、各直線セグメントは、時計回りまたは反時計回りのいずれかに表示されます。 閉じた領域から図形の外側に描画架空の線が時計回りの直線セグメントを通過するたびに、カウントがインクリメントされます。 行が反時計回りに回転線セグメントを経過すると、カウントがデクリメントします。 図形の外側の行に達したら、カウントがゼロ以外の領域に入力されます。  
  
 アプリケーションが終了した場合に作成された領域を使用して、 `CreatePolyPolygonRgn` 関数の場合、デバイス コンテキストのリージョンを選択する必要があります、 [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#cgdiobject__deleteobject) メンバー関数を削除します。  
  
##  <a name="a-namecrgncreaterectrgna-crgncreaterectrgn"></a><a name="crgn__createrectrgn"></a>  CRgn::CreateRectRgn  
 格納されている四角形の領域を作成、 `CRgn` オブジェクトです。  
  
```  
BOOL CreateRectRgn(
    int x1,  
    int y1,  
    int x2,  
    int y2);
```  
  
### <a name="parameters"></a>パラメーター  
 `x1`  
 領域の左上隅の論理の x 座標を指定します。  
  
 `y1`  
 論理で領域の左上隅の y 座標を指定します。  
  
 `x2`  
 領域の右下隅の論理の x 座標を指定します。  
  
 `y2`  
 論理で領域の右下隅の y 座標を指定します。  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 領域のサイズが 32,767 で 32,767 の論理ユニット、またはメモリの 64 K に制限は、どちらか小さい方です。  
  
 によって作成された領域の使用の終了時 `CreateRectRgn`, 、アプリケーションを使用する必要があります、 [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#cgdiobject__deleteobject) 、領域を削除するメンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#147](../../mfc/codesnippet/CPP/crgn-class_4.cpp)]  
  
 たとえば、次を参照してください。 [CRgn::CombineRgn](#crgn__combinergn)します。  
  
##  <a name="a-namecrgncreaterectrgnindirecta-crgncreaterectrgnindirect"></a><a name="crgn__createrectrgnindirect"></a>  CRgn::CreateRectRgnIndirect  
 格納されている四角形の領域を作成、 `CRgn` オブジェクトです。  
  
```  
BOOL CreateRectRgnIndirect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、 `RECT` 構造または `CRect` 領域の左上隅および右下隅の論理座標を格納しているオブジェクト。  `RECT` 構造体には、次の形式。  
  
 `typedef struct tagRECT {`  
  
 `int left;`  
  
 `int top;`  
  
 `int right;`  
  
 `int bottom;`  
  
 `} RECT;`  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 領域のサイズが 32,767 で 32,767 の論理ユニット、またはメモリの 64 K に制限は、どちらか小さい方です。  
  
 によって作成された領域の使用の終了時 `CreateRectRgnIndirect`, 、アプリケーションを使用する必要があります、 [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#cgdiobject__deleteobject) 、領域を削除するメンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#148](../../mfc/codesnippet/CPP/crgn-class_5.cpp)]  
  
##  <a name="a-namecrgncreateroundrectrgna-crgncreateroundrectrgn"></a><a name="crgn__createroundrectrgn"></a>  CRgn::CreateRoundRectRgn  
 格納されている角の丸い四角形の領域を作成、 `CRgn` オブジェクトです。  
  
```  
BOOL CreateRoundRectRgn(
    int x1,  
    int y1,  
    int x2,  
    int y2,  
    int x3,  
    int y3);
```  
  
### <a name="parameters"></a>パラメーター  
 `x1`  
 領域の左上隅の論理の x 座標を指定します。  
  
 `y1`  
 論理で領域の左上隅の y 座標を指定します。  
  
 `x2`  
 領域の右下隅の論理の x 座標を指定します。  
  
 `y2`  
 論理で領域の右下隅の y 座標を指定します。  
  
 *x3*  
 丸い角を作成するために使用する、楕円の幅を指定します。  
  
 `y3`  
 丸い角を作成するために使用する省略記号の高さを指定します。  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 領域のサイズが 32,767 で 32,767 の論理ユニット、またはメモリの 64 K に制限は、どちらか小さい方です。  
  
 アプリケーションが終了した場合に作成された領域を使用して、 `CreateRoundRectRgn` 関数の場合、デバイス コンテキストのリージョンを選択する必要があります、 [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#cgdiobject__deleteobject) メンバー関数を削除します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#149](../../mfc/codesnippet/CPP/crgn-class_6.cpp)]  
  
##  <a name="a-namecrgncrgna-crgncrgn"></a><a name="crgn__crgn"></a>  CRgn::CRgn  
 `CRgn` オブジェクトを構築します。  
  
```  
CRgn();
```  
  
### <a name="remarks"></a>コメント  
  `m_hObject` データ メンバーが含まれていない、有効な Windows GDI 地域にはとその他の 1 つ以上のオブジェクトが初期化されるまで `CRgn` メンバー関数。  
  
### <a name="example"></a>例  
  例を参照してください [CRgn::CreateRoundRectRgn](#crgn__createroundrectrgn)します。  
  
##  <a name="a-namecrgnequalrgna-crgnequalrgn"></a><a name="crgn__equalrgn"></a>  CRgn::EqualRgn  
 指定された領域に格納されている領域に相当するかどうかを判断、 `CRgn` オブジェクトです。  
  
```  
BOOL EqualRgn(CRgn* pRgn) const;

 
```  
  
### <a name="parameters"></a>パラメーター  
 `pRgn`  
 領域を識別します。  
  
### <a name="return-value"></a>戻り値  
 2 つのリージョンが等しい場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#150](../../mfc/codesnippet/CPP/crgn-class_7.cpp)]  
  
##  <a name="a-namecrgnfromhandlea-crgnfromhandle"></a><a name="crgn__fromhandle"></a>  CRgn::FromHandle  
 ポインターを返す、 `CRgn` Windows 領域へのハンドルが指定されるとします。  
  
```  
static CRgn* PASCAL FromHandle(HRGN hRgn);
```  
  
### <a name="parameters"></a>パラメーター  
 `hRgn`  
 Windows の領域を識別するハンドルを指定します。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 `CRgn` オブジェクトです。 関数が正常に実行されなかった場合、戻り値は **NULL**します。  
  
### <a name="remarks"></a>コメント  
 場合、 `CRgn` オブジェクトが、一時的なハンドルに既にアタッチされていない `CRgn` オブジェクトが作成され、接続されています。 この一時 `CRgn` だけですべて一時的なグラフィックを時間があるオブジェクトは削除されるまで、次回、アプリケーションのアイドル時間のイベント ループで、オブジェクトが有効です。 言い換えると、別の方法は、1 つのウィンドウ メッセージを処理中に一時オブジェクトが有効でのみことです。  
  
##  <a name="a-namecrgngetregiondataa-crgngetregiondata"></a><a name="crgn__getregiondata"></a>  CRgn::GetRegionData  
 データ領域を説明するには、指定したバッファーを設定します。  
  
```  
int GetRegionData(
    LPRGNDATA lpRgnData,  
    int nCount) const;

 
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRgnData`  
 指す、 [RGNDATA](../../mfc/reference/rgndata-structure.md) 情報を受信するデータ構造です。 このパラメーターは場合 **NULL**, 、戻り値には、地域のデータに必要なバイト数が含まれています。  
  
 `nCount`  
 サイズ (バイト単位) を指定、 `lpRgnData` バッファー。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合と `nCount` 十分な数を指定します (バイト単位) の戻り値は常に `nCount`します。 関数が失敗した場合、または場合 `nCount` 以下を指定適切なバイト数、戻り値は 0 (エラー)。  
  
### <a name="remarks"></a>コメント  
 このデータには、領域を構成する四角形のディメンションが含まれています。 この関数は組み合わせて使用、 `CRgn::CreateFromData` 関数です。  
  
##  <a name="a-namecrgngetrgnboxa-crgngetrgnbox"></a><a name="crgn__getrgnbox"></a>  CRgn::GetRgnBox  
 外接する四角形の座標を取得、 `CRgn` オブジェクトです。  
  
```  
int GetRgnBox(LPRECT lpRect) const;

 
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、 `RECT` 構造または `CRect` 外接する四角形の座標を受け取るオブジェクト。  `RECT` 構造体には、次の形式。  
  
 `typedef struct tagRECT {`  
  
 `int left;`  
  
 `int top;`  
  
 `int right;`  
  
 `int bottom;`  
  
 `} RECT;`  
  
### <a name="return-value"></a>戻り値  
 領域の型を指定します。 次の値のいずれかを指定できます。  
  
- **COMPLEXREGION** 領域には罫線を重複しています。  
  
- **NULLREGION** 領域が空です。  
  
- **エラー** `CRgn` オブジェクトは、有効な地域を指定しません。  
  
- **SIMPLEREGION** 領域に重複する境界がありません。  
  
### <a name="example"></a>例  
  例を参照してください [CRgn::CreatePolygonRgn](#crgn__createpolygonrgn)します。  
  
##  <a name="a-namecrgnoffsetrgna-crgnoffsetrgn"></a><a name="crgn__offsetrgn"></a>  CRgn::OffsetRgn  
 格納されている領域を移動、 `CRgn` 指定されたオフセットでのオブジェクト。  
  
```  
int OffsetRgn(
    int x,  
    int y);

 
int OffsetRgn(
    POINT point);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 左に移動する単位数を指定します。  
  
 *y*  
 上下に移動する単位の数を指定します。  
  
 `point`  
 X 座標 `point` 左に移動する単位の数を指定します。 Y 座標 `point` を上下に移動する単位の数を指定します。  `point` パラメーターには、いずれかを指定できます、 **ポイント** 構造体、または `CPoint` オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 新しい領域の種類。 次の値のいずれかを指定できます。  
  
- **COMPLEXREGION** 領域には罫線を重複しています。  
  
- **エラー** 領域ハンドルが無効です。  
  
- **NULLREGION** 領域が空です。  
  
- **SIMPLEREGION** 領域に重複する境界がありません。  
  
### <a name="remarks"></a>コメント  
 関数は、領域を移動 *x* 、x 軸に沿った単位と *y* y 軸に沿った単位です。  
  
 領域の座標の値は、32,767 および以上-32,768 以下である必要があります。  *X* と *y* パラメーターは無効な領域の座標値を防ぐために慎重に選択する必要があります。  
  
### <a name="example"></a>例  
  例を参照してください [CRgn::CreateEllipticRgn](#crgn__createellipticrgn)します。  
  
##  <a name="a-namecrgnoperatorhrgna-crgnoperator-hrgn"></a><a name="crgn__operator_hrgn"></a>  CRgn::operator HRGN  
 この演算子の接続されている Windows GDI ハンドルの取得を使用して、 `CRgn` オブジェクトです。  
  
'' 演算子 HRGN() const です。

 
```  
  
### Return Value  
 If successful, a handle to the Windows GDI object represented by the `CRgn` object; otherwise **NULL**.  
  
### Remarks  
 This operator is a casting operator, which supports direct use of an **HRGN** object.  
  
 For more information about using graphic objects, see the article [Graphic Objects](http://msdn.microsoft.com/library/windows/desktop/dd144962) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="crgn__ptinregion"></a>  CRgn::PtInRegion  
 Checks whether the point given by *x* and *y* is in the region stored in the `CRgn` object.  
  
```  
BOOL PtInRegion (int x  
    int y) const です。

 
 
Const; BOOL PtInRegion (ポイント)

 
```  
  
### Parameters  
 *x*  
 Specifies the logical x-coordinate of the point to test.  
  
 *y*  
 Specifies the logical y-coordinate of the point to test.  
  
 `point`  
 The x- and y-coordinates of `point` specify the x- and y-coordinates of the point to test the value of. The `point` parameter can either be a **POINT** structure or a `CPoint` object.  
  
### Return Value  
 Nonzero if the point is in the region; otherwise 0.  
  
##  <a name="crgn__rectinregion"></a>  CRgn::RectInRegion  
 Determines whether any part of the rectangle specified by `lpRect` is within the boundaries of the region stored in the `CRgn` object.  
  
```  
BOOL RectInRegion(LPCRECT lpRect) const です。

 
```  
  
### Parameters  
 `lpRect`  
 Points to a `RECT` structure or `CRect` object. The `RECT` structure has the following form:  
  
 `typedef struct tagRECT {`  
  
 `int left;`  
  
 `int top;`  
  
 `int right;`  
  
 `int bottom;`  
  
 `} RECT;`  
  
### Return Value  
 Nonzero if any part of the specified rectangle lies within the boundaries of the region; otherwise 0.  
  
##  <a name="crgn__setrectrgn"></a>  CRgn::SetRectRgn  
 Creates a rectangular region.  
  
```  
void SetRectRgn (int x1、  
    int y1  
    int x2、  
    int y2) です。

 
void SetRectRgn (LPCRECT lpRect) です。
```  
  
### Parameters  
 `x1`  
 Specifies the x-coordinate of the upper-left corner of the rectangular region.  
  
 `y1`  
 Specifies the y-coordinate of the upper-left corner of the rectangular region.  
  
 `x2`  
 Specifies the x-coordinate of the lower-right corner of the rectangular region.  
  
 `y2`  
 Specifies the y-coordinate of the lower-right corner of the rectangular region.  
  
 `lpRect`  
 Specifies the rectangular region. Can be either a pointer to a `RECT` structure or a `CRect` object.  
  
### Remarks  
 Unlike [CreateRectRgn](#crgn__createrectrgn), however, it does not allocate any additional memory from the local Windows application heap. Instead, it uses the space allocated for the region stored in the `CRgn` object. This means that the `CRgn` object must already have been initialized with a valid Windows region before calling `SetRectRgn`. The points given by `x1`, `y1`, `x2`, and `y2` specify the minimum size of the allocated space.  
  
 Use this function instead of the `CreateRectRgn` member function to avoid calls to the local memory manager.  
  
## See Also  
 [CWnd Class](../Topic/CWnd%20Class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)



