---
title: "CLinkCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CLinkCtrl
dev_langs:
- C++
helpviewer_keywords:
- CLinkCtrl class
- Web pages, link control
- controls [MFC], links
- links [C++], link control
- SysLink control
ms.assetid: d1cd876a-ecca-42db-8ac4-9cd327df0cd4
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
ms.openlocfilehash: 710fef79306c906e13e99beac15401835422ecbe
ms.lasthandoff: 02/24/2017

---
# <a name="clinkctrl-class"></a>CLinkCtrl クラス
Windows コモン SysLink コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CLinkCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CLinkCtrl::CLinkCtrl](#clinkctrl)|`CLinkCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CLinkCtrl::Create](#create)|リンク コントロールを作成し、それをアタッチ、`CLinkCtrl`オブジェクトです。|  
|[適用](#createex)|拡張スタイルを使用してリンク コントロールを作成し、それをアタッチ、`CLinkCtrl`オブジェクトです。|  
|[CLinkCtrl::GetIdealHeight](#getidealheight)|リンク コントロールの適切な高さを取得します。|  
|[CLinkCtrl::GetIdealSize](#getidealsize)|リンクの指定した幅に応じて、現在のリンク コントロールのリンク テキストの適切な高さを計算します。|  
|[CLinkCtrl::GetItem](#getitem)|リンク コントロールの項目の属性の状態を取得します。|  
|[CLinkCtrl::GetItemID](#getitemid)|リンク コントロールの項目の ID を取得します。|  
|[CLinkCtrl::GetItemState](#getitemstate)|リンク コントロールの項目の状態を取得します。|  
|[CLinkCtrl::GetItemUrl](#getitemurl)|リンク コントロールの項目で表される URL を取得します。|  
|[CLinkCtrl::HitTest](#hittest)|ユーザーが、指定されたリンクをクリックするかどうかを決定します。|  
|[CLinkCtrl::SetItem](#setitem)|状態とリンク コントロールの項目の属性を設定します。|  
|[CLinkCtrl::SetItemID](#setitemid)|リンク コントロールの項目の ID を設定します。|  
|[CLinkCtrl::SetItemState](#setitemstate)|リンク コントロールの項目の状態を設定します。|  
|[CLinkCtrl::SetItemUrl](#setitemurl)|リンク コントロールの項目で表される URL を設定します。|  
  
## <a name="remarks"></a>コメント  
 「リンク コントロール」をウィンドウにハイパー テキスト リンクを埋め込むには便利な方法を提供します。 実際のコントロールは、テキストをレンダリングし、ユーザーが埋め込まれたリンクをクリックすると、適切なアプリケーションを起動するウィンドウです。 複数のリンクは、1 つのコントロール内ではサポートされ、0 から始まるインデックスによってアクセスできることができます。  
  
 このコントロール (つまり、`CLinkCtrl`クラス) 以降では、Windows XP を実行中のプログラムにのみ有効です。  
  
 詳細については、次を参照してください。 [SysLink コントロール](http://msdn.microsoft.com/library/windows/desktop/bb760706)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CLinkCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="a-nameclinkctrla--clinkctrlclinkctrl"></a><a name="clinkctrl"></a>CLinkCtrl::CLinkCtrl  
 `CLinkCtrl` オブジェクトを構築します。  
  
```  
CLinkCtrl();
```  
  
##  <a name="a-namecreatea--clinkctrlcreate"></a><a name="create"></a>CLinkCtrl::Create  
 リンク コントロールを作成し、それをアタッチ、`CLinkCtrl`オブジェクトです。  
  
```  
virtual BOOL Create(
    LPCTSTR lpszLinkMarkup,   
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);

 
virtual BOOL Create(DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszLinkMarkup`  
 マークされた項目を表示するテキストを含む&0; で終わる文字列へのポインター。 詳細については、」の「マークアップとリンクのアクセス」セクションを参照してください。 [SysLink コントロールの概要](http://msdn.microsoft.com/library/windows/desktop/bb760706)で、 [MSDN ライブラリ](http://go.microsoft.com/fwlink/linkid=556)します。  
  
 `dwStyle`  
 リンク コントロールのスタイルを指定します。 コントロールのスタイルの任意の組み合わせを適用します。 参照してください[コモン コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775498)で、`Windows SDK`の詳細。  
  
 `rect`  
 リンク コントロールのサイズと位置を指定します。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](../../mfc/reference/rect-structure1.md)構造体。  
  
 `pParentWnd`  
 リンク コントロールの親ウィンドウを指定します。 ことはできません`NULL`します。  
  
 `nID`  
 リンク コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 `true`初期化が成功した場合それ以外の場合`false`します。  
  
### <a name="remarks"></a>コメント  
 構築する、 `CLinkCtrl`&2; つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出すし、まず`Create`、リンク コントロールを作成およびそれにアタッチする、`CLinkCtrl`オブジェクトです。 コントロールで拡張ウィンドウ スタイルを使用する場合は、呼び出す[適用](#createex)の代わりに`Create`します。  
  
 2 番目の形式、`Create`メソッドは使用されなくなりました。 指定する最初のフォームを使用して、`lpszLinkMarkup`パラメーター。  
  
### <a name="example"></a>例  
 次のコード例は、という&2; つの変数を定義`m_Link1`と`m_Link2`、2 つのリンク コントロールのアクセスに使用されます。  
  
 [!code-cpp[NVC_MFC_CLinkCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/clinkctrl-class_1.h)]  
  
### <a name="example"></a>例  
 次のコード例では、別のリンク コントロールの場所に基づいて&1; つのリンク コントロールを作成します。 リソース ローダーは、アプリケーションの起動時に、最初のリンク コントロールを作成します。 OnInitDialog メソッドに入ると、アプリケーションとき、に、最初のリンク コントロールの位置を基準とした&2; つ目のリンク コントロールを作成します。 表示されるテキストに合わせて&2; 番目のリンク コントロールがサイズ変更します。  
  
 [!code-cpp[NVC_MFC_CLinkCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/clinkctrl-class_2.cpp)]  
  
##  <a name="a-namecreateexa--clinkctrlcreateex"></a><a name="createex"></a>適用  
 拡張スタイルを使用してリンク コントロールを作成し、それをアタッチ、`CLinkCtrl`オブジェクトです。  
  
```  
virtual BOOL CreateEx(
    LPCTSTR lpszLinkMarkup,   
    DWORD dwExStyle,  
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);

 
virtual BOOL CreateEx(DWORD  dwExStyle,
    DWORD  dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT  nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszLinkMarkup`  
 マークされた項目を表示するテキストを含む&0; で終わる文字列へのポインター。 詳細については、」の「マークアップとリンクのアクセス」セクションを参照してください。 [SysLink コントロールの概要](http://msdn.microsoft.com/library/windows/desktop/bb760706)で、 [MSDN ライブラリ](http://go.microsoft.com/fwlink/linkid=556)します。  
  
 `dwExStyle`  
 リンク コントロールの拡張スタイルを指定します。 拡張ウィンドウ スタイルの一覧は、次を参照してください。、`dwExStyle`パラメーター [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `dwStyle`  
 リンク コントロールのスタイルを指定します。 コントロールのスタイルの任意の組み合わせを適用します。 詳細については、次を参照してください。[コモン コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775498)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `rect`  
 リンク コントロールのサイズと位置を指定します。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](../../mfc/reference/rect-structure1.md)構造体。  
  
 `pParentWnd`  
 リンク コントロールの親ウィンドウを指定します。 ことはできません`NULL`します。  
  
 `nID`  
 リンク コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 `true`初期化が成功した場合それ以外の場合`false`します。  
  
### <a name="remarks"></a>コメント  
 使用`CreateEx`の代わりに[作成](#create)拡張ウィンドウ スタイルの定数を適用します。  
  
 2 番目の形式、`CreateEx`メソッドは使用されなくなりました。 指定する最初のフォームを使用して、`lpszLinkMarkup`パラメーター。  
  
##  <a name="a-namegetidealheighta--clinkctrlgetidealheight"></a><a name="getidealheight"></a>CLinkCtrl::GetIdealHeight  
 リンク コントロールの適切な高さを取得します。  
  
```  
int GetIdealHeight() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ピクセル単位でのコントロールの適切な高さ。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[LM_GETIDEALHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb760716)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetidealsizea--clinkctrlgetidealsize"></a><a name="getidealsize"></a>CLinkCtrl::GetIdealSize  
 リンクの指定した幅に応じて、現在のリンク コントロールのリンク テキストの適切な高さを計算します。  
  
```  
int GetIdealSize(
    int cxMaxWidth,   
    SIZE* pSize) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `cxMaxWidth`|ピクセル単位でのリンクの最大幅。|  
|[out] *`pSize`|Windows へのポインター[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造体。 このメソッドが戻るとき、`cy`のメンバー、`SIZE`構造体には、理想のリンク テキストの高さで指定されたリンク テキストの幅が含まれています。`cxMaxWidth`します。 `cx`構造体のメンバーには、実際に必要なリンク テキストの幅が含まれています。|  
  
### <a name="return-value"></a>戻り値  
 ピクセル単位でのリンク テキストの適切な高さ。 戻り値は、の値と同じ、`cy`のメンバー、`SIZE`構造体。  
  
### <a name="remarks"></a>コメント  
 例については、`GetIdealSize`メソッドの例を参照[CLinkCtrl::Create](#create)します。  
  
 このメソッドは、送信、 [LM_GETIDEALSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760718)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetitema--clinkctrlgetitem"></a><a name="getitem"></a>CLinkCtrl::GetItem  
 リンク コントロールの項目の属性の状態を取得します。  
  
```  
BOOL GetItem(PLITEM pItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 ポインター、 [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710)項目情報を受け取る構造です。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、 **FALSE**失敗します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetitemida--clinkctrlgetitemid"></a><a name="getitemid"></a>CLinkCtrl::GetItemID  
 リンク コントロールの項目の ID を取得します。  
  
```  
BOOL GetItemID(
    int iLink,  
    CString& strID) const;  
  
BOOL GetItemID(
    int iLink,  
    LPWSTR szID,  
    UINT cchID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `iLink`  
 リンク コントロールの項目のインデックス。  
  
 *strID*  
 A [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)指定した項目の ID を表すオブジェクト。  
  
 *szID*  
 指定した項目の ID を表す null で終わる文字列。  
  
 *cchID*  
 サイズの文字、 *szID*バッファー。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、 **FALSE**失敗します。  
  
> [!NOTE]
>  この関数も返します**FALSE**場合のバッファー *szID または strID*よりも小さい**MAX_LINKID_TEXT**します。  
  
### <a name="remarks"></a>コメント  
 特定のリンク コントロールの項目の ID を取得します。 詳細については、Win32 メッセージを参照してください。 [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetitemstatea--clinkctrlgetitemstate"></a><a name="getitemstate"></a>CLinkCtrl::GetItemState  
 リンク コントロールの項目の状態を取得します。  
  
```  
BOOL GetItemState(
    int iLink,  
    UINT* pnState,  
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `iLink`  
 リンク コントロールの項目のインデックス。  
  
 `pnState`  
 指定した状態の項目の値。  
  
 `stateMask`  
 取得するには、どのステート項目を記述したフラグの組み合わせ。 値の一覧の説明を参照して、**状態**内のメンバー、 [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710)構造体。 使用可能な項目で許可されているものと同じ**状態**します。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、 **FALSE**失敗します。  
  
### <a name="remarks"></a>コメント  
 特定のリンク コントロールの項目の状態を指定した項目の値を取得します。 詳細については、Win32 メッセージを参照してください。 [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetitemurla--clinkctrlgetitemurl"></a><a name="getitemurl"></a>CLinkCtrl::GetItemUrl  
 リンク コントロールの項目で表される URL を取得します。  
  
```  
BOOL GetItemUrl(
    int iLink,  
    CString& strUrl) const;  
  
BOOL GetItemUrl(
    int iLink,  
    LPWSTR szUrl,  
    UINT cchUrl) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `iLink`  
 リンク コントロールの項目のインデックス。  
  
 `strUrl`  
 A [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトの指定した項目によって表される URL を含む  
  
 `szUrl`  
 指定した項目によって表される URL を含む null で終わる文字列  
  
 *cchUrl*  
 サイズの文字、 *szURL*バッファー。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、 **FALSE**失敗します。  
  
> [!NOTE]
>  この関数も返します**FALSE**場合のバッファー *szUrl または strUrl*よりも小さい**MAX_LINKID_TEXT**します。  
  
### <a name="remarks"></a>コメント  
 指定したリンク コントロールの項目で表される URL を取得します。 詳細については、Win32 メッセージを参照してください。 [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namehittesta--clinkctrlhittest"></a><a name="hittest"></a>CLinkCtrl::HitTest  
 ユーザーが、指定されたリンクをクリックしたかどうかを判断します。  
  
```  
BOOL HitTest(PLHITTESTINFO phti) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *phti*  
 ポインター、**すべて保持**ユーザーがクリックされたリンクに関する情報を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、 **FALSE**失敗します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[LM_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb760722)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetitema--clinkctrlsetitem"></a><a name="setitem"></a>CLinkCtrl::SetItem  
 状態とリンク コントロールの項目の属性を設定します。  
  
```  
BOOL SetItem(PLITEM pItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 ポインター、 [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710)設定情報を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、 **FALSE**失敗します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetitemida--clinkctrlsetitemid"></a><a name="setitemid"></a>CLinkCtrl::SetItemID  
 リンク コントロールの項目の ID を取得します。  
  
```  
BOOL SetItemID(
    int iLink,  
    LPCWSTR szID);
```  
  
### <a name="parameters"></a>パラメーター  
 `iLink`  
 リンク コントロールの項目のインデックス。  
  
 *szID*  
 指定した項目の ID を表す null で終わる文字列。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、 **FALSE**失敗します。  
  
### <a name="remarks"></a>コメント  
 特定のリンク コントロールの項目の ID を設定します。 詳細については、Win32 メッセージを参照してください。 [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetitemstatea--clinkctrlsetitemstate"></a><a name="setitemstate"></a>CLinkCtrl::SetItemState  
 リンク コントロールの項目の状態を取得します。  
  
```  
BOOL SetItemState(
    int iLink,  
    UINT state,  
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED);
```  
  
### <a name="parameters"></a>パラメーター  
 `iLink`  
 リンク コントロールの項目のインデックス。  
  
 `pnState`  
 指定した状態のアイテムの設定の値。  
  
 `stateMask`  
 設定されている状態のアイテムを記述したフラグの組み合わせ。 値の一覧の説明を参照して、**状態**内のメンバー、 [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710)構造体。 使用可能な項目で許可されているものと同じ**状態**します。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、 **FALSE**失敗します。  
  
### <a name="remarks"></a>コメント  
 特定のリンク コントロールの項目の状態を指定した項目の値を設定します。 詳細については、Win32 メッセージを参照してください。 [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetitemurla--clinkctrlsetitemurl"></a><a name="setitemurl"></a>CLinkCtrl::SetItemUrl  
 リンク コントロールの項目で表される URL を設定します。  
  
```  
BOOL SetItemUrl(
    int iLink,  
    LPCWSTR szUrl);
```  
  
### <a name="parameters"></a>パラメーター  
 `iLink`  
 リンク コントロールの項目のインデックス。  
  
 `szUrl`  
 指定した項目によって表される URL を含む null で終わる文字列  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、 **FALSE**失敗します。  
  
### <a name="remarks"></a>コメント  
 指定したリンク コントロールの項目で表される URL を設定します。 詳細については、Win32 メッセージを参照してください。 [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)

