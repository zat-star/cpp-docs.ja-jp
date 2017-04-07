---
title: "CFont クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFont
- AFXWIN/CFont
- AFXWIN/CFont::CFont
- AFXWIN/CFont::CreateFont
- AFXWIN/CFont::CreateFontIndirect
- AFXWIN/CFont::CreatePointFont
- AFXWIN/CFont::CreatePointFontIndirect
- AFXWIN/CFont::FromHandle
- AFXWIN/CFont::GetLogFont
dev_langs:
- C++
helpviewer_keywords:
- CFont class
- GDI, font classes
- fonts, MFC classes
ms.assetid: 3fad6bfe-d6ce-4ab9-967a-5ce0aa102800
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
ms.openlocfilehash: cc7ecfb850bf24013acdb55075eeb3d64d4994ee
ms.lasthandoff: 02/24/2017

---
# <a name="cfont-class"></a>CFont クラス
Windows のグラフィック デバイス インターフェイス (GDI) のフォントをカプセル化したもので、フォントを操作するメンバー関数を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CFont : public CGdiObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CFont::CFont](#cfont)|`CFont` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFont::CreateFont](#createfont)|初期化、`CFont`指定の特性を持つ。|  
|[CFont::CreateFontIndirect](#createfontindirect)|初期化、`CFont`オブジェクトで指定された特性を持つ、`LOGFONT`構造体。|  
|[CFont::CreatePointFont](#createpointfont)|初期化、`CFont`ポイント、およびタイプフェイス&10; 分の&1; 単位は指定された高さにします。|  
|[CFont::CreatePointFontIndirect](#createpointfontindirect)|同じ`CreateFontIndirect`する点を除いて、フォントの高さが論理ユニットではなく、ポイント&0;.1 単位で測定されます。|  
|[CFont::FromHandle](#fromhandle)|ポインターを返す、 `CFont` Windows が指定されると**HFONT**します。|  
|[CFont::GetLogFont](#getlogfont)|入力、`LOGFONT`に接続されている論理フォントに関する情報を`CFont`オブジェクトです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CFont::operator HFONT](#operator_hfont)|接続されている Windows GDI フォント ハンドルを返します。、`CFont`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 使用する、`CFont`オブジェクト、構築、`CFont`オブジェクトしてアタッチ Windows フォントで[構築](#createfont)、 [CreateFontIndirect](#createfontindirect)、 [CreatePointFont](#createpointfont)、または[CreatePointFontIndirect](#createpointfontindirect)、し、オブジェクトのメンバー関数を使用して、フォントを操作します。  
  
 `CreatePointFont`と`CreatePointFontIndirect`関数は、多くの場合よりも使いやすく`CreateFont`または`CreateFontIndirect`のためフォントの高さの変換、ポイント サイズから論理ユニットを自動的にします。  
  
 詳細については`CFont`を参照してください[グラフィック オブジェクト](../../mfc/graphic-objects.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CFont`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cfont"></a>CFont::CFont  
 `CFont` オブジェクトを構築します。  
  
```  
CFont();
```  
  
### <a name="remarks"></a>コメント  
 結果のオブジェクトを初期化する必要があります`CreateFont`、 `CreateFontIndirect`、 `CreatePointFont`、または`CreatePointFontIndirect`を使用する前にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&70;](../../mfc/codesnippet/cpp/cfont-class_1.cpp)]  
  
##  <a name="createfont"></a>CFont::CreateFont  
 初期化、`CFont`指定の特性を持つオブジェクト。  
  
```  
BOOL CreateFont(
    int nHeight,  
    int nWidth,  
    int nEscapement,  
    int nOrientation,  
    int nWeight,  
    BYTE bItalic,  
    BYTE bUnderline,  
    BYTE cStrikeOut,  
    BYTE nCharSet,  
    BYTE nOutPrecision,  
    BYTE nClipPrecision,  
    BYTE nQuality,  
    BYTE nPitchAndFamily,  
    LPCTSTR lpszFacename);
```  
  
### <a name="parameters"></a>パラメーター  
 `nHeight`  
 フォントの高さを (論理単位で) でを指定します。 参照してください、`lfHeight`のメンバー、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]についてです。 絶対値`nHeight`が変換された後、16,384 デバイス単位を超えない必要があります。 高さ比較を行う場合に、すべてのフォントが要求されたサイズを超える場合も、フォント マッパーは最も大きいフォントが要求されたサイズを超えていないか、最小のフォントを探します。  
  
 `nWidth`  
 フォントの文字 (論理単位で平均の幅を指定します。 場合`nWidth`が 0 の差の絶対値によって決定される最も近い一致を検索する利用可能なフォントのデジタル化縦横比と一致するデバイスの縦横比場合、。  
  
 `nEscapement`  
 傾斜ベクターと表示面の x 軸の角を (0.1 度単位) を指定します。 傾斜ベクターは、行の最初と最後の文字の原点を結ぶ直線です。 角度は、x 軸から反時計回りに測定されます。 参照してください、`lfEscapement`内のメンバー、`LOGFONT`構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細。  
  
 `nOrientation`  
 角度 (度 0.1 単位で)、文字のベースラインと x 軸を指定します。 角度は、y 軸方向のダウンして、x 軸の y 方向が上の座標系から時計回りに座標系を x 軸から反時計回りに測定されます。  
  
 `nWeight`  
 フォントの太さ (で 1000 ピクセル単位) を指定します。 参照してください、`lfWeight`内のメンバー、`LOGFONT`構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細。 説明の値は概数です。実際の外観は、フォントに依存します。 一部のフォントがのみ`FW_NORMAL`、 `FW_REGULAR`、および`FW_BOLD`重みです。 場合`FW_DONTCARE`を指定すると、既定の重みが使用されます。  
  
 `bItalic`  
 フォントが斜体かどうかを指定します。  
  
 `bUnderline`  
 フォントの下線が引かれたかどうかを指定します。  
  
 `cStrikeOut`  
 のフォントの文字が当てられたかどうかを指定します。 場合に取り消し線フォントを指定する&0; 以外の値に設定します。  
  
 `nCharSet`  
 フォントの文字セットの指定、`lfCharSet`内のメンバー、`LOGFONT`構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の値の一覧です。  
  
 OEM 文字セットは、システムによって異なります。  
  
 その他の文字セットを使用するフォントは、システムに存在することができます。 不明な文字セットとフォントを使用するアプリケーションでは、変換や、そのフォントで表示するのには文字列の解釈がしよう必要があります。 代わりに、文字列は、出力デバイス ドライバーに直接渡す必要があります。  
  
 フォント マッパーを使用して、`DEFAULT_CHARSET`値。 アプリケーションでは、論理フォントを完全に記述するのにフォントのサイズと名前を許可するように、この値を使用できます。 指定した名前のフォントが存在しない場合、任意の文字セットからフォントは、指定したフォントの代わりに使用できます。 予期しない結果を避けるためには、アプリケーションが使用する、`DEFAULT_CHARSET`値を多用しないようにします。  
  
 `nOutPrecision`  
 目的の出力の有効桁数を指定します。 出力の有効桁数は、要求されたフォントの高さ、幅、文字の方向、傾斜、およびピッチに出力をどの程度一致する必要がありますを定義します。 参照してください、`lfOutPrecision`内のメンバー、`LOGFONT`構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]値と詳細の一覧についてです。  
  
 `nClipPrecision`  
 希望するクリッピングの有効桁数を指定します。 クリッピング精度は、部分的にクリッピング領域の外側にある文字をクリップする方法を定義します。 参照してください、`lfClipPrecision`内のメンバー、`LOGFONT`構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の値の一覧です。  
  
 読み取り専用の埋め込みフォントを使用するアプリケーションを指定する必要があります`CLIP_ENCAPSULATE`します。  
  
 デバイス、truetype フォント、およびベクター フォントの一貫した回転を実現するために、アプリケーションは、結合を OR 演算子を使用して、`CLIP_LH_ANGLES`値とその他の`nClipPrecision`値。 場合、`CLIP_LH_ANGLES`ビットが設定されている、すべてのフォントの回転、座標系の向きが左手座標系かによって違います右手座標系か。 (詳細については、座標系の向きの説明を参照して、`nOrientation`パラメーターです)。場合`CLIP_LH_ANGLES`が設定されていないデバイス フォント常に反時計回りに回転、その他のフォントの回転、座標系の向きに依存します。  
  
 `nQuality`  
 フォントの出力品質は、実際の物理的なフォントの論理フォント属性を一致するように、GDI を試みる必要がありますか慎重に定義を指定します。 参照してください、`lfQuality`内のメンバー、`LOGFONT`構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の値の一覧です。  
  
 `nPitchAndFamily`  
 ピッチとフォントのファミリを指定します。 参照してください、`lfPitchAndFamily`内のメンバー、`LOGFONT`構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]値と詳細の一覧についてです。  
  
 `lpszFacename`  
 A`CString`またはフォントの書体名を指定する null で終わる文字列へのポインター。 この文字列の長さは 30 文字を超えない必要があります。 Windows [EnumFontFamilies](http://msdn.microsoft.com/library/windows/desktop/dd162619)関数を使用して、現在利用可能なすべてのフォントを列挙します。 場合`lpszFacename`は`NULL`GDI がデバイスに依存しない書体を使用します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 フォントは、任意のデバイス コンテキストのフォントとして後で選択できます。  
  
 `CreateFont`関数では、新しい Windows GDI フォントは作成されません。 それだけで、最も近いから選択利用できる物理フォントに、GDI します。  
  
 アプリケーションは、論理フォントを作成するときに、ほとんどのパラメーターに既定の設定を使用できます。 特定の値を常に指定するパラメーターは、`nHeight`と`lpszFacename`です。 場合`nHeight`と`lpszFacename`が設定されていない場合、アプリケーションによって作成される論理フォントにはデバイスに依存します。  
  
 終了するときに、`CFont`によって作成されたオブジェクト、`CreateFont`関数を使用して`CDC::SelectObject`をデバイス コンテキストに、別のフォントを選択し、削除、`CFont`オブジェクトが不要です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&71;](../../mfc/codesnippet/cpp/cfont-class_2.cpp)]  
  
##  <a name="createfontindirect"></a>CFont::CreateFontIndirect  
 初期化、`CFont`オブジェクトで指定された特性を持つ、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)構造体。  
  
```  
BOOL CreateFontIndirect(const LOGFONT* lpLogFont);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpLogFont`  
 指す、`LOGFONT`論理フォントの特性を定義する構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 フォントは、任意のデバイスの現在のフォントとして後で選択できます。  
  
 このフォントにで指定された特性、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)構造体。 使用して、フォントが選択されている場合、 [:selectobject](../../mfc/reference/cdc-class.md#selectobject)論理フォントを既存の物理フォントとは、メンバー関数では、GDI フォント マッパーとします。 フォント マッパーは、完全に一致する論理フォントを検索する失敗した場合、要求された特性をできるだけ多くします一致する特性を持つ別のフォントを提供します。  
  
 不要になった必要がある場合、`CFont`によって作成されたオブジェクト、`CreateFontIndirect`関数を使用して`CDC::SelectObject`をデバイス コンテキストに、別のフォントを選択し、削除、`CFont`オブジェクトが不要です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&72;](../../mfc/codesnippet/cpp/cfont-class_3.cpp)]  
  
##  <a name="createpointfont"></a>CFont::CreatePointFont  
 この関数は、指定したフォントのフォントを作成し、ポイント サイズを簡単な方法を提供します。  
  
```  
BOOL CreatePointFont(
    int nPointSize,  
    LPCTSTR lpszFaceName,  
    CDC* pDC = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `nPointSize`  
 必要な点の&1;/10 でフォントの高さ。 (たとえば、パスの 12 ポイントのフォントを指定するのには 120 です。)  
  
 `lpszFaceName`  
 A`CString`またはフォントの書体名を指定する null で終わる文字列へのポインター。 この文字列の長さは 30 文字を超えない必要があります。 Windows **EnumFontFamilies**関数を使用して、現在利用可能なすべてのフォントを列挙します。 場合`lpszFaceName`は**NULL**GDI がデバイスに依存しない書体を使用します。  
  
 `pDC`  
 ポインター、 [CDC](../../mfc/reference/cdc-class.md)を使用する高さを変換するオブジェクト`nPointSize`の論理ユニットにします。 場合**NULL**画面のデバイス コンテキストは、変換に使用します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、0 以外。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 高さを自動変換`nPointSize`論理ユニットを使用して、`CDC`によって指されるオブジェクト`pDC`します。  
  
 終了するときに、`CFont`によって作成されたオブジェクト、`CreatePointFont`関数で最初に、デバイス コンテキストからフォントを選択し、削除、`CFont`オブジェクトです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&73;](../../mfc/codesnippet/cpp/cfont-class_4.cpp)]  
  
##  <a name="createpointfontindirect"></a>CFont::CreatePointFontIndirect  
 この関数は、同じ[CreateFontIndirect](#createfontindirect)する点を除いて、**する**のメンバー、`LOGFONT`はデバイスではなくポイント単位の部分の&1;/10 に解釈されます。  
  
```  
BOOL CreatePointFontIndirect(
    const LOGFONT* lpLogFont,  
    CDC* pDC = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpLogFont`  
 指す、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)論理フォントの特性を定義する構造体。 **する**のメンバー、`LOGFONT`構造体は、論理ユニットではなく、ポイントの部分の&1;/10 で計測されます。 (たとえば、設定**する**を 120 に 12 ポイントのフォントを指定します)。  
  
 `pDC`  
 ポインター、 [CDC](../../mfc/reference/cdc-class.md)を使用する高さを変換するオブジェクト**する**の論理ユニットにします。 場合**NULL**画面のデバイス コンテキストは、変換に使用します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、0 以外。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 この関数は、高さを自動的に変換**する**を使用して論理ユニットに、`CDC`によって指されるオブジェクト`pDC`渡される前に、`LOGFONT`構造 Windows にログオンします。  
  
 終了するときに、`CFont`によって作成されたオブジェクト、`CreatePointFontIndirect`関数で最初に、デバイス コンテキストからフォントを選択し、削除、`CFont`オブジェクトです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&74;](../../mfc/codesnippet/cpp/cfont-class_5.cpp)]  
  
##  <a name="fromhandle"></a>CFont::FromHandle  
 ポインターを返す、`CFont`が指定されると、 **HFONT** Windows GDI フォント オブジェクトへのハンドルします。  
  
```  
static CFont* PASCAL FromHandle(HFONT hFont);
```  
  
### <a name="parameters"></a>パラメーター  
 `hFont`  
 **HFONT** Windows フォントに対するハンドルします。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CFont`成功以外の場合は、オブジェクト**NULL**します。  
  
### <a name="remarks"></a>コメント  
 場合、 `CFont` 、一時的なハンドルにオブジェクトが既にアタッチされていない`CFont`オブジェクトが作成され、接続されています。 この一時`CFont`だけですべて一時的なグラフィックを時間があるオブジェクトは削除されるまで、次回、アプリケーションのアイドル時間のイベント ループで、オブジェクトが有効です。 言い換えると、別の方法は、一時オブジェクトは、1 つのウィンドウ メッセージを処理中にのみ有効です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&75;](../../mfc/codesnippet/cpp/cfont-class_6.cpp)]  
  
##  <a name="getlogfont"></a>CFont::GetLogFont  
 コピーを取得するには、この関数を呼び出して、`LOGFONT`の構造体`CFont`します。  
  
```  
int GetLogFont(LOGFONT* pLogFont);
```  
  
### <a name="parameters"></a>パラメーター  
 *pLogFont*  
 ポインター、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)フォント情報を受け取る構造です。  
  
### <a name="return-value"></a>戻り値  
 関数が成功すると、それ以外の場合 0 0 以外の値。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&76;](../../mfc/codesnippet/cpp/cfont-class_7.cpp)]  
  
##  <a name="operator_hfont"></a>CFont::operator HFONT  
 接続されているフォントの Windows GDI ハンドルの取得にこの演算子を使用して、`CFont`オブジェクトです。  
  
```  
operator HFONT() const;  
```  
  
### <a name="return-value"></a>戻り値  
 接続されている Windows GDI フォント オブジェクトのハンドルを`CFont`成功した場合は**NULL**します。  
  
### <a name="remarks"></a>コメント  
 この演算子からの変換が自動的に使用されるため`CFont`に[フォントとテキスト](http://msdn.microsoft.com/library/windows/desktop/dd144819)を渡すことができます`CFont`する関数にオブジェクト**HFONT**秒です。  
  
 グラフィック オブジェクトの使い方の詳細については、次を参照してください。[グラフィック オブジェクト](http://msdn.microsoft.com/library/windows/desktop/dd144962)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&77;](../../mfc/codesnippet/cpp/cfont-class_8.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル HIERSVR](../../visual-cpp-samples.md)   
 [CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)




