---
title: "CMFCRibbonGallery クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonGallery
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::CMFCRibbonGallery
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::AddGroup
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::AddSubItem
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::Clear
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::EnableMenuResize
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::EnableMenuSideBar
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetCompactSize
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetDroppedDown
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetGroupName
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetGroupOffset
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetIconsInRow
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetItemToolTip
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetLastSelectedItem
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetPaletteID
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetRegularSize
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetSelectedItem
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::HasMenu
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::IsButtonMode
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::IsMenuResizeEnabled
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::IsMenuResizeVertical
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::IsMenuSideBar
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::OnAfterChangeRect
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::OnDraw
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::OnEnable
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::OnRTLChanged
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::RedrawIcons
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::RemoveItemToolTips
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::SelectItem
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::SetACCData
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::SetButtonMode
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::SetGroupName
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::SetIconsInRow
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::SetItemToolTip
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::SetPalette
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::SetPaletteID
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::OnDrawPaletteIcon
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonGallery class
ms.assetid: 9734c9c9-981c-4b3f-8c59-264fd41811b4
caps.latest.revision: 28
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
ms.openlocfilehash: c4eadb9820f2d7318131cc4d197dbe28d65491c0
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbongallery-class"></a>CMFCRibbonGallery クラス
Office 2007 スタイルのリボン ギャラリーを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonGallery : public CMFCRibbonButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonGallery::CMFCRibbonGallery](#cmfcribbongallery)|`CMFCRibbonGallery` オブジェクトを構築して初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonGallery::AddGroup](#addgroup)|ギャラリーには、新しいグループを追加します。|  
|[CMFCRibbonGallery::AddSubItem](#addsubitem)|ドロップダウン メニューに新しいメニュー項目を追加します。|  
|[CMFCRibbonGallery::Clear](#clear)|ギャラリーの内容を消去します。|  
|[CMFCRibbonGallery::EnableMenuResize](#enablemenuresize)|有効または無効 メニュー パネルのサイズを変更します。|  
|[CMFCRibbonGallery::EnableMenuSideBar](#enablemenusidebar)|有効またはポップアップ メニューの左側にサイド バーを無効にします。|  
|[CMFCRibbonGallery::GetCompactSize](#getcompactsize)|(上書き[CMFCRibbonButton::GetCompactSize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize))。|  
|[CMFCRibbonGallery::GetDroppedDown](#getdroppeddown)|(上書き[CMFCRibbonBaseElement::GetDroppedDown](../../mfc/reference/cmfcribbonbaseelement-class.md#getdroppeddown))。|  
|[CMFCRibbonGallery::GetGroupName](#getgroupname)|指定したインデックス位置にあるグループの名前を返します。|  
|[CMFCRibbonGallery::GetGroupOffset](#getgroupoffset)||  
|[CMFCRibbonGallery::GetIconsInRow](#geticonsinrow)|リボン ギャラリーの行の項目の数を返します。|  
|[CMFCRibbonGallery::GetItemToolTip](#getitemtooltip)|ギャラリーの項目に関連付けられているツールヒント テキストを返します。|  
|[CMFCRibbonGallery::GetLastSelectedItem](#getlastselecteditem)|ユーザーが選択したギャラリーでは、最後の項目のインデックスを返します。|  
|[CMFCRibbonGallery::GetPaletteID](#getpaletteid)|現在のギャラリーのコマンド ID を返します。|  
|[CMFCRibbonGallery::GetRegularSize](#getregularsize)|(上書き[CMFCRibbonButton::GetRegularSize](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize))。|  
|[CMFCRibbonGallery::GetSelectedItem](#getselecteditem)||  
|[CMFCRibbonGallery::HasMenu](#hasmenu)|(上書き[CMFCRibbonButton::HasMenu](../../mfc/reference/cmfcribbonbutton-class.md#hasmenu))。|  
|[CMFCRibbonGallery::IsButtonMode](#isbuttonmode)|ギャラリー ボタンで、ギャラリーが含まれているかどうかを指定します。|  
|[CMFCRibbonGallery::IsMenuResizeEnabled](#ismenuresizeenabled)|メニューのサイズ変更が有効か無効かを指定します。|  
|[CMFCRibbonGallery::IsMenuResizeVertical](#ismenuresizevertical)||  
|[CMFCRibbonGallery::IsMenuSideBar](#ismenusidebar)|サイド バーを有効または無効にするかどうかを指定します。|  
|[CMFCRibbonGallery::OnAfterChangeRect](#onafterchangerect)|(`CMFCRibbonButton::OnAfterChangeRect` をオーバーライドします)。|  
|[CMFCRibbonGallery::OnDraw](#ondraw)|(上書き[CMFCRibbonButton::OnDraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw))。|  
|[CMFCRibbonGallery::OnEnable](#onenable)|(`CMFCRibbonBaseElement::OnEnable` をオーバーライドします)。|  
|[CMFCRibbonGallery::OnRTLChanged](#onrtlchanged)|(上書き[CMFCRibbonBaseElement::OnRTLChanged](../../mfc/reference/cmfcribbonbaseelement-class.md#onrtlchanged))。|  
|[CMFCRibbonGallery::RedrawIcons](#redrawicons)|ギャラリーを再描画します。|  
|[CMFCRibbonGallery::RemoveItemToolTips](#removeitemtooltips)|ギャラリー内のすべての項目からヒントを削除します。|  
|[CMFCRibbonGallery::SelectItem](#selectitem)||  
|[CMFCRibbonGallery::SetACCData](#setaccdata)|(上書き[CMFCRibbonButton::SetACCData](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata))。|  
|[CMFCRibbonGallery::SetButtonMode](#setbuttonmode)|リボン上で直接パレットとして、またはドロップダウン ボタンとしてリボン ギャラリーを表示するかどうかを指定します。|  
|[CMFCRibbonGallery::SetGroupName](#setgroupname)|グループの名前を設定します。|  
|[CMFCRibbonGallery::SetIconsInRow](#seticonsinrow)|ギャラリー内の行ごとの項目の数を定義します。|  
|[CMFCRibbonGallery::SetItemToolTip](#setitemtooltip)|ギャラリー項目のツールヒント テキストを設定します。|  
|[CMFCRibbonGallery::SetPalette](#setpalette)|リボン ギャラリーをパレットをアタッチします。|  
|[CMFCRibbonGallery::SetPaletteID](#setpaletteid)|送信されるコマンド ID を定義、`WM_COMMAND`ギャラリー項目が選択されている場合に、メッセージです。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonGallery::OnDrawPaletteIcon](#ondrawpaletteicon)|ギャラリーのアイコンが描画されるときに、フレームワークによって呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 ギャラリー ボタンは、ユーザーが開いたときにギャラリーを表示する点を除いて、標準のメニュー ボタンと同じように動作します。 ギャラリー内の項目を選択すると、フレームワークは送信、`WM_COMMAND`メッセージが表示され、ボタンのコマンド ID。 メッセージを処理する場合を呼び出す必要があります[CMFCRibbonGallery::GetLastSelectedItem](#getlastselecteditem)をギャラリーから選択されたアイテムを決定します。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCRibbonGallery`を構成するクラス、`CMFCRibbonGallery`オブジェクトです。 この例では、ギャラリー内の行ごとの項目の数を指定 メニュー パネルのサイズ変更を有効にする、ポップアップ メニューの左側にサイド バーを有効にする、およびリボン バーに直接パレットとしてリボン ギャラリーを表示する方法を示します。 このコード スニペットの一部である、[クライアントの描画のサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_DrawClient&6;](../../mfc/reference/codesnippet/cpp/cmfcribbongallery-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md) [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md) [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxRibbonPaletteGallery.h  
  
##  <a name="addgroup"></a>CMFCRibbonGallery::AddGroup  
 ギャラリーには、新しいグループを追加します。  
  
```  
void AddGroup(
    LPCTSTR lpszGroupName,  
    UINT uiImagesPaletteResID,  
    int cxPaletteImage);

 
void AddGroup(
    LPCTSTR lpszGroupName,  
    CMFCToolBarImages& imagesGroup);

 
void AddGroup(
    LPCTSTR lpszGroupName,  
    int nIconsNum);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszGroupName`  
 グループの名前を指定します。  
  
 [入力] `uiImagesPaletteResID`  
 グループのイメージを含むイメージ リストのリソース ID を指定します。  
  
 [入力] `cxPaletteImage`  
 イメージのピクセル単位の幅を指定します。  
  
 [入力] `imagesGroup`  
 グループのイメージを格納するイメージ リストへの参照。  
  
 [入力] `nIconsNum`  
 グループのアイコンの数を指定します。 このパラメーターは、カスタム (オーナー描画) に対してのみ指定する必要がありますグループです。  
  
### <a name="remarks"></a>コメント  
 リボン ギャラリー項目は、このメソッドを呼び出して、複数のグループに分割できます。 各グループには、キャプションを設定できます。  
  
##  <a name="addsubitem"></a>CMFCRibbonGallery::AddSubItem  
 ドロップダウン メニューに新しいメニュー項目を追加します。  
  
```  
void AddSubItem(
    CMFCRibbonBaseElement* pSubItem,  
    int nIndex=-1,  
    BOOL bOnTop=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pSubItem`  
 メニューに追加する項目へのポインター。  
  
 [入力] `nIndex`  
 位置の&0; から始まるインデックスに項目を挿入する場所を指定します。  
  
 [入力] `bOnTop`  
 `TRUE`リボン ギャラリーの前に、項目を挿入することを指定するにはそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出すことによって、ポップアップ メニュー項目を含むポップアップ ギャラリーを組み合わせることができます。 ギャラリーの前後に、メニュー項目を配置することができます。  
  
 ギャラリー前に、の項目を挿入するには、次のように設定します。`bOnTop`に`TRUE`します。 設定`bOnTop`に`FALSE`ギャラリーの下部の項目を挿入します。  
  
> [!NOTE]
>  パラメーター`nIndex`挿入インデックス ギャラリーの上部にあると、ギャラリーの下部の両方を指定します。 ギャラリーの前に、の項目 1 つの位置を挿入する必要がある場合の設定など`nIndex`1 と`bOnTop`に`TRUE`します。 同様に、ギャラリーの下部の項目 1 つの位置に挿入する場合は、設定`nIndex`1 と`bOnTop`に`FALSE`します。  
  
##  <a name="clear"></a>CMFCRibbonGallery::Clear  
 ギャラリーの内容を消去します。  
  
```  
virtual void Clear();
```  
  
### <a name="remarks"></a>コメント  
 リボン ギャラリーからのすべてのコンテンツを削除するには、このメソッドを呼び出します。 リボン ギャラリーを新しいリボン ギャラリーまたはグループのセットをアタッチする前に、これを行う必要があります。  
  
##  <a name="cmfcribbongallery"></a>CMFCRibbonGallery::CMFCRibbonGallery  
 構築して初期化、 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)オブジェクトです。  
  
```  
CMFCRibbonGallery (
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex,  
    int nLargeImageIndex,  
    CMFCToolBarImages& imagesPalette);

 
CMFCRibbonGallery (
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex,  
    int nLargeImageIndex,  
    UINT uiImagesPaletteResID=0,  
    int cxPaletteImage=0);

 
CMFCRibbonGallery (
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex,  
    int nLargeImageIndex,  
    CSize sizeIcon,  
    int nIconsNum,  
    BOOL bDefaultButtonStyle=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 ユーザーがボタンをクリックしたときに実行するコマンドのコマンド ID を指定します。  
  
 `lpszText`  
 ボタンに表示するテキストを指定します。  
  
 `nSmallImageIndex`  
 ボタンに表示する小さなイメージの&0; から始まるインデックス。  
  
 `nLargeImageIndex`  
 ボタンに表示する大規模なイメージの&0; から始まるインデックス。  
  
 `imagesPalette`  
 参照、 [CMFCToolBarImages](../../mfc/reference/cmfctoolbarimages-class.md)ギャラリーに表示するイメージを保持するオブジェクト。  
  
 `uiImagesPaletteResID`  
 ギャラリーに表示するイメージの一覧のリソース ID。  
  
 `cxPaletteImage`  
 ギャラリーのイメージのピクセル単位の幅を指定します。  
  
 `sizeIcon`  
 ギャラリーのイメージのピクセル単位のサイズを指定します。  
  
 `nIconsNum`  
 ギャラリーでアイコンの数を指定します。  
  
 `bDefaultButtonStyle`  
 既定値またはオーナー描画ボタン スタイルを使用するかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="enablemenuresize"></a>CMFCRibbonGallery::EnableMenuResize  
 有効または無効 メニュー パネルのサイズを変更します。  
  
```  
void EnableMenuResize(
    BOOL bEnable = TRUE,  
    BOOL bVertcalOnly = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE`メニューをサイズ変更を有効にするにはそれ以外の場合、`FALSE`です。  
  
 [入力] `bVertcalOnly`  
 `TRUE`ギャラリーが垂直方向にのみ変更できるように指定するには`FALSE`ギャラリーができることを指定するサイズ変更両方方向と縦方向です。  
  
### <a name="remarks"></a>コメント  
 有効または無効のリボン ギャラリーのサイズを変更するのには、このメソッドを使用します。 サイズ変更を有効にすると、リボン ギャラリーは、ユーザーがサイズの変更に使用できるグリップを表示します。  
  
##  <a name="enablemenusidebar"></a>CMFCRibbonGallery::EnableMenuSideBar  
 有効またはポップアップ メニューの左側にサイド バーを無効にします。  
  
```  
void EnablMenuSideBar(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE`サイド バーが有効であるかを指定するにはそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 有効にするか、メニューの左側にある Office XP スタイル サイド バーを無効にするには、このメソッドを呼び出します。  
  
##  <a name="getcompactsize"></a>CMFCRibbonGallery::GetCompactSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getdroppeddown"></a>CMFCRibbonGallery::GetDroppedDown  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CMFCRibbonBaseElement* GetDroppedDown();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getgroupname"></a>CMFCRibbonGallery::GetGroupName  
 指定したインデックス位置にあるグループの名前を返します。  
  
```  
LPCTSTR GetGroupName(int nGroupIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nGroupIndex`  
 グループを取得する名前を持つの&0; から始まるインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 指定したインデックス位置にあるグループの名前。 無効なインデックスを渡すと、失敗したアサーションが発生します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getgroupoffset"></a>CMFCRibbonGallery::GetGroupOffset  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetGroupOffset() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="geticonsinrow"></a>CMFCRibbonGallery::GetIconsInRow  
 リボン ギャラリーの行の項目の数を返します。  
  
```  
int GetIconsInRow() const;  
```  
  
### <a name="return-value"></a>戻り値  
 行の項目の数。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getitemtooltip"></a>CMFCRibbonGallery::GetItemToolTip  
 ギャラリーの項目に関連付けられているツールヒント テキストを返します。  
  
```  
LPCTSTR GetItemToolTip(int nItemIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nItemIndex`  
 ツールヒント テキストを取得する対象の項目の&0; から始まるインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 リボン ギャラリー内の項目に割り当てられているツールヒント文字列へのポインター。 できます`NULL`ツールヒントがその項目に割り当てられていない場合。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getlastselecteditem"></a>CMFCRibbonGallery::GetLastSelectedItem  
 ユーザーが選択したリボン ギャラリーの最後の項目のインデックスを返します。  
  
```  
static int GetLastSelectedItem(UINT uiCmdID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmdID`  
 リボン ギャラリーを開くメニュー項目のコマンド ID を指定します。  
  
### <a name="return-value"></a>戻り値  
 ユーザーは、リボン ギャラリーのいずれかの項目を選択するときに、ライブラリから送信、`WM_COMMAND`リボン ギャラリーを開く メニューのボタンのコマンド ID とメッセージです。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getpaletteid"></a>CMFCRibbonGallery::GetPaletteID  
 現在のパレットのコマンド ID を返します。  
  
```  
int GetPaletteID() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在選択されているパレットのコマンド ID。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getregularsize"></a>CMFCRibbonGallery::GetRegularSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getselecteditem"></a>CMFCRibbonGallery::GetSelectedItem  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetSelectedItem() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="hasmenu"></a>CMFCRibbonGallery::HasMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isbuttonmode"></a>CMFCRibbonGallery::IsButtonMode  
 ギャラリー ボタンにパレットが含まれているかどうかを指定します。  
  
```  
BOOL IsButtonMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ドロップダウン メニュー ボタンとパレットが表示された場合`FALSE`場合は、リボン上で直接パレットが表示されます。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ismenuresizeenabled"></a>CMFCRibbonGallery::IsMenuResizeEnabled  
 メニューのサイズ変更が有効になっているかどうかを指定します。  
  
```  
BOOL IsMenuResizeEnabled() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メニューのサイズ変更が有効になって; 場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ismenuresizevertical"></a>CMFCRibbonGallery::IsMenuResizeVertical  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsMenuResizeVertical() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ismenusidebar"></a>CMFCRibbonGallery::IsMenuSideBar  
 サイド バーを有効または無効にするかどうかを指定します。  
  
```  
BOOL IsMenuSideBar() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`Office XP スタイルのサイド バーは、ポップアップ メニューの左側にあるで描画する場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onafterchangerect"></a>CMFCRibbonGallery::OnAfterChangeRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnAfterChangeRect(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ondraw"></a>CMFCRibbonGallery::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ondrawpaletteicon"></a>CMFCRibbonGallery::OnDrawPaletteIcon  
 ギャラリーのアイコンが描画されるときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnDrawPaletteIcon(
    CDC* pDC,  
    CRect rectIcon,  
    int nIconIndex,  
    CMFCRibbonGalleryIcon* pIcon,  
    COLORREF clrText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 描画のために使用されるデバイス コンテキストへのポインター。  
  
 [入力] `rectIcon`  
 描画するアイコンに外接する四角形を指定します。  
  
 [入力] `nIconIndex`  
 描画するアイコンのギャラリーのアイコンのイメージ リスト内の&0; から始まるインデックスを指定します。  
  
 [入力] `pIcon`  
 描画されるアイコンへのポインター。  
  
 [入力] `clrText`  
 描画する項目のテキストの色を指定します。  
  
### <a name="remarks"></a>コメント  
 リボン ギャラリーの外観をカスタマイズする派生クラスでは、このメソッドをオーバーライドすることができます。  
  
##  <a name="onenable"></a>CMFCRibbonGallery::OnEnable  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnEnable(BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onrtlchanged"></a>CMFCRibbonGallery::OnRTLChanged  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnRTLChanged(BOOL bIsRTL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bIsRTL`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="redrawicons"></a>CMFCRibbonGallery::RedrawIcons  
 ギャラリーを再描画します。  
  
```  
void RedrawIcons();
```  
  
### <a name="remarks"></a>コメント  
 この関数では、ギャラリーを再描画します。 実行時に、ギャラリーの内容を変更している場合は、このメソッドを呼び出す必要があります。  
  
##  <a name="removeitemtooltips"></a>CMFCRibbonGallery::RemoveItemToolTips  
 ギャラリー内のすべての項目からヒントを削除します。  
  
```  
void RemoveItemToolTips();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="selectitem"></a>CMFCRibbonGallery::SelectItem  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SelectItem(int nItemIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nItemIndex`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setaccdata"></a>CMFCRibbonGallery::SetACCData  
 リボン ギャラリーのユーザー補助データを使用して、指定された `CAccessibilityData` オブジェクトを設定します。  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,   
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pParent`  
 リボン ギャラリーのウィンドウの親ウィンドウです。  
  
 [出力] `data`  
 リボン ギャラリーのユーザー補助データを受信する `CAccessibilityData` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 このメソッドが成功した場合は `TRUE`。それ以外の場合は `FALSE`。  
  
##  <a name="setbuttonmode"></a>CMFCRibbonGallery::SetButtonMode  
 リボン上で直接パレットとして、またはドロップダウン ボタンとしてリボン ギャラリーを表示するかどうかを決定します。  
  
```  
void SetButtonMode(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bSet`  
 `TRUE`ドロップダウン メニュー ボタンとしてリボン ギャラリーを表示するには`FALSE`リボン上で直接リボン ギャラリーの内容を表示します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setgroupname"></a>CMFCRibbonGallery::SetGroupName  
 グループの名前を設定します。  
  
```  
void SetGroupName(
    int nGroupIndex,  
    LPCTSTR lpszGroupName);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nGroupIndex`  
 名前が変更されているグループの&0; から始まるインデックスを指定します。  
  
 [入力] `lpszGroupName`  
 グループの新しい名前を指定します。  
  
### <a name="remarks"></a>コメント  
 名前が変更されているグループが追加されているを使用して、 [CMFCRibbonGallery::AddGroup](#addgroup)メソッドです。  
  
##  <a name="seticonsinrow"></a>CMFCRibbonGallery::SetIconsInRow  
 ギャラリーでは、行ごとの項目の数を指定します。  
  
```  
void SetIconsInRow(int nIconsInRow);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIconsInRow`  
 ギャラリーの行ごとに表示する項目の数を指定します。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、リボン ギャラリーの幅を指定できます。  
  
##  <a name="setitemtooltip"></a>CMFCRibbonGallery::SetItemToolTip  
 ギャラリー項目のツールヒント テキストを設定します。  
  
```  
void SetItemToolTip(
    int nItemIndex,  
    LPCTSTR lpszToolTip);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nItemIndex`  
 ツールヒントを関連付けるパレット項目の&0; から始まるインデックス。  
  
 [入力] `lpszToolTip`  
 ツールヒントに表示するテキストです。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setpalette"></a>CMFCRibbonGallery::SetPalette  
 リボン ギャラリーをパレットをアタッチします。  
  
```  
void SetPalette(CMFCToolBarImages& imagesPalette);

 
void SetPalette(
    UINT uiImagesPaletteResID,  
    int cxPaletteImage);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `imagesPalette`  
 ギャラリーに表示するアイコンを格納するイメージの一覧を指定します。  
  
 [入力] `uiImagesPaletteResID`  
 ギャラリーに表示するアイコンを格納するイメージ リストのリソース ID を指定します。  
  
 [入力] `cxPaletteImage`  
 ギャラリーのイメージのピクセル単位の幅を指定します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setpaletteid"></a>CMFCRibbonGallery::SetPaletteID  
 送信されるコマンド ID を定義、 **WM_COMMAND**メッセージが表示される、ユーザーは、ギャラリー項目を選択します。  
  
```  
void SetPaletteID(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 送信されるコマンド ID を指定、 **WM_COMMAND**メッセージが表示される、ユーザーは、ギャラリー項目を選択します。  
  
### <a name="remarks"></a>コメント  
 ギャラリーから、ユーザーが選択した特定の項目を確認するのには、呼び出し、 [CMFCRibbonGallery::GetLastSelectedItem](#getlastselecteditem)静的メソッドです。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonGalleryMenuButton クラス](../../mfc/reference/cmfcribbongallerymenubutton-class.md)

