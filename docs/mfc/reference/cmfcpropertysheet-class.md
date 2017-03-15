---
title: "CMFCPropertySheet クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertySheet
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertySheet::PreTranslateMessage method
- CMFCPropertySheet::OnInitDialog method
- CMFCPropertySheet class
ms.assetid: 01d93573-9698-440f-a6a4-5bebbee879dc
caps.latest.revision: 35
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
ms.openlocfilehash: a157a0afa4542bc023ba4d7149e78a71bbd56e74
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpropertysheet-class"></a>CMFCPropertySheet クラス
`CMFCPropertySheet` クラスは、各プロパティ ページがページ タブ、ツール バー ボタン、ツリー コントロールのノード、またはリスト項目で示されるプロパティ シートをサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCPropertySheet : public CPropertySheet  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCPropertySheet::CMFCPropertySheet](#cmfcpropertysheet)|`CMFCPropertySheet` オブジェクトを構築します。|  
|`CMFCPropertySheet::~CMFCPropertySheet`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCPropertySheet::AddPage](#addpage)|プロパティ シートにページを追加します。|  
|[CMFCPropertySheet::AddPageToTree](#addpagetotree)|ツリー コントロールに新しいプロパティ ページを追加します。|  
|[CMFCPropertySheet::AddTreeCategory](#addtreecategory)|ツリー コントロールに新しいノードを追加します。|  
|[CMFCPropertySheet::EnablePageHeader](#enablepageheader)|カスタム ヘッダーを描画する領域を各ページの上部に確保します。|  
|[CMFCPropertySheet::GetHeaderHeight](#getheaderheight)|現在のヘッダーの高さを取得します。|  
|[CMFCPropertySheet::GetLook](#getlook)|現在のプロパティ シートの外観を指定する列挙値を取得します。|  
|[CMFCPropertySheet::GetNavBarWidth](#getnavbarwidth)|ナビゲーション バーの幅をピクセル単位で取得します。|  
|[CMFCPropertySheet::GetTab](#gettab)|現在のプロパティ シート コントロールをサポートする内部タブ コントロール オブジェクトを取得します。|  
|`CMFCPropertySheet::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol)|現在のプロパティ シート コントロールの外観を初期化します。|  
|[CMFCPropertySheet::OnActivatePage](#onactivatepage)|プロパティ ページが有効になったときにフレームワークによって呼び出されます。|  
|[CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader)|カスタム プロパティ ページのヘッダーを描画するためにフレームワークによって呼び出されます。|  
|`CMFCPropertySheet::OnInitDialog`|処理、 [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428)メッセージです。 (上書き[CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog))。|  
|[CMFCPropertySheet::OnRemoveTreePage](#onremovetreepage)|ツリー コントロールからプロパティ ページを削除するためにフレームワークによって呼び出されます。|  
|`CMFCPropertySheet::PreTranslateMessage`|ウィンドウのメッセージの変換にディスパッチされる前に、 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 関数です。 (`CPropertySheet::PreTranslateMessage` をオーバーライドします)。|  
|[CMFCPropertySheet::RemoveCategory](#removecategory)|ツリー コントロールからノードを削除します。|  
|[CMFCPropertySheet::RemovePage](#removepage)|プロパティ シートからプロパティ ページを削除します。|  
|[CMFCPropertySheet::SetIconsList](#seticonslist)|Outlook ウィンドウのナビゲーション コントロールで使用されるイメージの一覧を指定します。|  
|[CMFCPropertySheet::SetLook](#setlook)|プロパティ シートの外観を指定します。|  
  
## <a name="remarks"></a>コメント  
 `CMFCPropertySheet` クラスは、プロパティ シート (タブ ダイアログ ボックスとも呼ばれます) を表します。 `CMFCPropertySheet` クラスは、さまざまな方法でプロパティ ページを表示できます。  
  
 アプリケーションで `CMFCPropertySheet` クラスを使用するには、次の手順を実行します。  
  
1.  `CMFCPropertySheet` クラスから派生クラスを作成し、名前 (CMyPropertySheet など) を付けます。  
  
2.  構築、 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)の各プロパティ ページのオブジェクト。  
  
3.  呼び出す、 [CMFCPropertySheet::SetLook](#setlook) CMyPropertySheet コンス トラクター内のメソッドです。 このメソッドのパラメーターで、プロパティ ページの表示方法として、プロパティ シートの上部または左側のタブ、Microsoft OneNote プロパティ シート スタイルのタブ、Microsoft Outlook ツール バー コントロールのボタン、ツリー コントロールのノード、プロパティ シートの左側の項目リストのいずれかを指定します。  
  
4.  Microsoft Outlook のツールバーのスタイルのプロパティ シートを作成する場合、 [CMFCPropertySheet::SetIconsList](#seticonslist)プロパティ ページとイメージ リストを関連付けるメソッド。  
  
5.  呼び出す、 [CMFCPropertySheet::AddPage](#addpage)各プロパティ ページのメソッドです。  
  
6.  `CMFCPropertySheet` コントロールを作成し、その `DoModal` メソッドを呼び出します。  
  
## <a name="illustrations"></a>図  
 次の図は、埋め込みの Microsoft Outlook ツール バー スタイルのプロパティ シートを示しています。 プロパティ シートの左側に Outlook ツール バーが表示されます。  
  
 ![CMFCPropertySheet カラー コントロール](../../mfc/reference/media/cmfcpropertysheet_color.png "cmfcpropertysheet_color")  
  
 次の図を含むプロパティ シートを示しています、 [CMFCPropertyGridCtrl クラス](../../mfc/reference/cmfcpropertygridctrl-class.md)オブジェクトです。 このオブジェクトは、標準のコモン コントロール スタイルのプロパティ シートです。  
  
 ![CMFCPropertySheet リストおよびプロパティ コントロール](../../mfc/reference/media/cmfcpropertysheet_list.png "cmfcpropertysheet_list")  
  
 次の図は、ツリー コントロール スタイルのプロパティ シートを示しています。  
  
 ![プロパティ ツリー](../../mfc/reference/media/proptree.png "proptree")  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxpropertysheet.h  
  
##  <a name="a-nameaddpagea--cmfcpropertysheetaddpage"></a><a name="addpage"></a>CMFCPropertySheet::AddPage  
 プロパティ シートにページを追加します。  
  
```  
void AddPage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pPage`  
 Page オブジェクトへのポインター。 このパラメーターを指定できません`NULL`します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、プロパティ シートの一番右のタブとして指定したプロパティ ページを追加します。 そのため、このメソッドを使用して、左から右へ順番でページを追加します。  
  
 プロパティ シートが Microsoft Outlook のスタイルの場合は、フレームワークでは、プロパティ シートの左のナビゲーション ボタンの一覧が表示されます。 このメソッドは、プロパティ ページを追加後、は、リストに対応するボタンが追加されます。 プロパティ ページを表示するには、その対応するボタンをクリックします。 プロパティ シートのスタイルの詳細については、次を参照してください。 [CMFCPropertySheet::SetLook](#setlook)します。  
  
##  <a name="a-nameaddpagetotreea--cmfcpropertysheetaddpagetotree"></a><a name="addpagetotree"></a>CMFCPropertySheet::AddPageToTree  
 ツリー コントロールに新しいプロパティ ページを追加します。  
  
```  
void AddPageToTree(
    CMFCPropertySheetCategoryInfo* pCategory,  
    CMFCPropertyPage* pPage,  
    int nIconNum=-1,  
    int nSelIconNum=-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pCategory`  
 ツリーのノードへのポインターまたは`NULL`に指定したページを最上位のノードに関連付けます。 呼び出す、 [CMFCPropertySheet::AddTreeCategory](#addtreecategory)このポインターを取得します。  
  
 [入力] `pPage`  
 プロパティ ページのオブジェクトへのポインター。  
  
 [入力] `nIconNum`  
 アイコン、または-1 のアイコンを使用しない場合の&0; から始まるインデックス。 ページが選択されていない場合は、ツリー コントロールのプロパティ ページの横にあるアイコンが表示されます。 既定値は -1 です。  
  
 [入力] `nSelIconNum`  
 アイコン、または-1 のアイコンを使用しない場合の&0; から始まるインデックス。 ページを選択すると、ツリー コントロールのプロパティ ページの横にあるアイコンが表示されます。 既定値は -1 です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ツリー コントロールのリーフとしてプロパティ ページを追加します。 プロパティ ページを追加するには、作成、`CMFCPropertySheet`オブジェクトを呼び出す、 [CMFCPropertySheet::SetLook](#setlook)メソッドを`look`パラメーターを設定する`CMFCPropertySheet::PropSheetLook_Tree`、し、このメソッドを使用してプロパティ ページを追加します。  
  
##  <a name="a-nameaddtreecategorya--cmfcpropertysheetaddtreecategory"></a><a name="addtreecategory"></a>CMFCPropertySheet::AddTreeCategory  
 ツリー コントロールに新しいノードを追加します。  
  
```  
CMFCPropertySheetCategoryInfo* AddTreeCategory(
    LPCTSTR lpszLabel,  
    int nIconNum=-1,  
    int nSelectedIconNum=-1,  
    const CMFCPropertySheetCategoryInfo* pParentCategory=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszLabel`  
 ノードの名前。  
  
 [入力] `nIconNum`  
 アイコン、または-1 のアイコンを使用しない場合の&0; から始まるインデックス。 ページが選択されていない場合は、ツリー コントロールのプロパティ ページの横にあるアイコンが表示されます。 既定値は -1 です。  
  
 [入力] `nSelectedIconNum`  
 アイコン、または-1 のアイコンを使用しない場合の&0; から始まるインデックス。 ページを選択すると、ツリー コントロールのプロパティ ページの横にあるアイコンが表示されます。 既定値は -1 です。  
  
 [入力] `pParentCategory`  
 ツリーのノードへのポインターまたは`NULL`に指定したページを最上位のノードに関連付けます。 このパラメーターを設定、 [CMFCPropertySheet::AddTreeCategory](#addtreecategory)メソッドです。  
  
### <a name="return-value"></a>戻り値  
 ツリー コントロールの新しいノードへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、ツリー コントロールにカテゴリとも呼ばれる、新しいノードを追加できます。 ノードを追加するには、作成、`CMFCPropertySheet`オブジェクトを呼び出す、 [CMFCPropertySheet::SetLook](#setlook)メソッドを`look`パラメーターを設定する`CMFCPropertySheet::PropSheetLook_Tree`、し、このメソッドを使用してノードを追加します。  
  
 このメソッドの戻り値を使用して、後続の呼び出しで[CMFCPropertySheet::AddPageToTree](#addpagetotree)と[CMFCPropertySheet::AddTreeCategory](#addtreecategory)します。  
  
##  <a name="a-namecmfcpropertysheeta--cmfcpropertysheetcmfcpropertysheet"></a><a name="cmfcpropertysheet"></a>CMFCPropertySheet::CMFCPropertySheet  
 `CMFCPropertySheet` オブジェクトを構築します。  
  
```  
CMFCPropertySheet(
    UINT nIDCaption,  
    CWnd* pParentWnd=NULL,  
    UINT iSelectPage=0);

CMFCPropertySheet(
    LPCTSTR pszCaption,  
    CWnd* pParentWnd=NULL,  
    UINT iSelectPage=0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pszCaption`  
 プロパティ シートのキャプションを表す文字列。 ことはできません`NULL`します。  
  
 [入力] `nIDCaption`  
 プロパティ シートのキャプションを含むリソース ID です。  
  
 [入力] `pParentWnd`  
 プロパティ シートの親ウィンドウへのポインターまたは`NULL`親ウィンドウが、アプリケーションのメイン ウィンドウの場合。 既定値は `NULL` です。  
  
 [入力] `iSelectPage`  
 最上位のプロパティ ページの&0; から始まるインデックス。 既定値は 0 です。  
  
### <a name="remarks"></a>コメント  
 詳細については、パラメーターを参照してください、[呼び出します](../../mfc/reference/cpropertysheet-class.md#cpropertysheet)コンス トラクターです。  
  
##  <a name="a-nameenablepageheadera--cmfcpropertysheetenablepageheader"></a><a name="enablepageheader"></a>CMFCPropertySheet::EnablePageHeader  
 カスタム ヘッダーを描画する領域を各ページの上部に確保します。  
  
```  
void EnablePageHeader(int nHeaderHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nHeaderHeight`  
 ピクセル単位で、ヘッダーの高さ。  
  
### <a name="remarks"></a>コメント  
 値を使用して、`nHeaderHeight`カスタム ヘッダーを描画するパラメーターを上書きする、 [CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader)メソッドです。  
  
##  <a name="a-namegetheaderheighta--cmfcpropertysheetgetheaderheight"></a><a name="getheaderheight"></a>CMFCPropertySheet::GetHeaderHeight  
 現在のヘッダーの高さを取得します。  
  
```  
int GetHeaderHeight() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ピクセル単位で、ヘッダーの高さ。  
  
### <a name="remarks"></a>コメント  
 呼び出す、 [CMFCPropertySheet::EnablePageHeader](#enablepageheader)メソッドがこのメソッドを呼び出す前にします。  
  
##  <a name="a-namegetlooka--cmfcpropertysheetgetlook"></a><a name="getlook"></a>CMFCPropertySheet::GetLook  
 現在のプロパティ シートの外観を指定する列挙値を取得します。  
  
```  
PropSheetLook GetLook() const;  
```  
  
### <a name="return-value"></a>戻り値  
 プロパティ シートの外観を指定する列挙値の&1; つ。 使用可能な値の一覧は、「解説」の列挙型の表を参照して[CMFCPropertySheet::SetLook](#setlook)します。  
  
##  <a name="a-namegetnavbarwidtha--cmfcpropertysheetgetnavbarwidth"></a><a name="getnavbarwidth"></a>CMFCPropertySheet::GetNavBarWidth  
 ナビゲーション バーの幅を取得します。  
  
```  
int GetNavBarWidth() const;  
```  
  
### <a name="return-value"></a>戻り値  
 軸スクロール バーの幅 (ピクセル単位)。  
  
##  <a name="a-namegettaba--cmfcpropertysheetgettab"></a><a name="gettab"></a>CMFCPropertySheet::GetTab  
 現在のプロパティ シート コントロールをサポートする内部タブ コントロール オブジェクトを取得します。  
  
```  
CMFCTabCtrl& GetTab() const;  
```  
  
### <a name="return-value"></a>戻り値  
 [内部] タブ コントロール オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 ナビゲーション ボタン、または一連のタブ付きページの一覧、ツリー コントロールなどのさまざまなスタイルで表示されるように、プロパティ シートを設定できます。  
  
 このメソッドを呼び出す前に呼び出し、 [CMFCPropertySheet::SetLook](#setlook)プロパティ シート コントロールの外観を設定します。 まず、 [CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol)内部タブ コントロール オブジェクトを初期化します。 タブ コントロール オブジェクトを取得し、そのオブジェクトを使用して、プロパティ シートで、タブを使用するには、このメソッドを使用します。  
  
 このメソッドは、プロパティ シート コントロールに表示される Microsoft OneNote のスタイルが設定されていない場合、デバッグ モードでアサートします。  
  
##  <a name="a-nameinitnavigationcontrola--cmfcpropertysheetinitnavigationcontrol"></a><a name="initnavigationcontrol"></a>CMFCPropertySheet::InitNavigationControl  
 現在のプロパティ シート コントロールの外観を初期化します。  
  
```  
virtual CWnd* InitNavigationControl();
```  
  
### <a name="return-value"></a>戻り値  
 プロパティ シート コントロールのウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
 プロパティ シート コントロールは、一連のタブ付きページ、ツリー コントロール、または、ナビゲーション ボタンの一覧など、いくつかの異なる形式で表示できます。 使用して、 [CMFCPropertySheet::SetLook](#setlook)プロパティ シート コントロールの外観を指定します。  
  
##  <a name="a-nameonactivatepagea--cmfcpropertysheetonactivatepage"></a><a name="onactivatepage"></a>CMFCPropertySheet::OnActivatePage  
 プロパティ ページが有効になったときにフレームワークによって呼び出されます。  
  
```  
virtual void OnActivatePage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pPage`  
 有効なプロパティ ページを表すプロパティ ページのオブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 既定では、このメソッドは、有効なプロパティ ページをスクロールして表示を確認します。 現在のプロパティ シートのスタイルに Microsoft Outlook のウィンドウが含まれている場合、このメソッドは、Outlook の対応するボタンをチェックされた状態に設定します。  
  
##  <a name="a-nameondrawpageheadera--cmfcpropertysheetondrawpageheader"></a><a name="ondrawpageheader"></a>CMFCPropertySheet::OnDrawPageHeader  
 カスタム プロパティ ページのヘッダーを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDrawPageHeader(
    CDC* pDC,  
    int nPage,  
    CRect rectHeader);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `nPage`  
 0 から始まるプロパティのページ番号です。  
  
 [入力] `rectHeader`  
 ヘッダーを描画する場所を指定する外接する四角形。  
  
### <a name="remarks"></a>コメント  
 既定では、このメソッドは何もしません。 このメソッドをオーバーライドする場合、 [CMFCPropertySheet::EnablePageHeader](#enablepageheader)フレームワークがこのメソッドを呼び出す前にします。  
  
##  <a name="a-nameonremovetreepagea--cmfcpropertysheetonremovetreepage"></a><a name="onremovetreepage"></a>CMFCPropertySheet::OnRemoveTreePage  
 ツリー コントロールからプロパティ ページを削除するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnRemoveTreePage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pPage`  
 プロパティ ページのオブジェクトを削除するプロパティ ページを表すへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このメソッドが成功した場合それ以外の場合、`FALSE`です。  
  
##  <a name="a-nameremovecategorya--cmfcpropertysheetremovecategory"></a><a name="removecategory"></a>CMFCPropertySheet::RemoveCategory  
 ツリー コントロールからノードを削除します。  
  
```  
void RemoveCategory(CMFCPropertySheetCategoryInfo* pCategory);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pCategory`  
 削除するカテゴリ (ノード) へのポインター。  
  
### <a name="remarks"></a>コメント  
 呼ばれるカテゴリでは、ツリー コントロールからノードを削除するのにには、このメソッドを使用します。 使用して、 [CMFCPropertySheet::AddTreeCategory](#addtreecategory)ツリー コントロール ノードを追加するメソッドです。  
  
##  <a name="a-nameremovepagea--cmfcpropertysheetremovepage"></a><a name="removepage"></a>CMFCPropertySheet::RemovePage  
 プロパティ シートからプロパティ ページを削除します。  
  
```  
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pPage`  
 削除するプロパティ ページを表す page オブジェクトのプロパティへのポインター。 ことはできません`NULL`します。  
  
 [入力] `nPage`  
 削除するページの&0; から始まるインデックス。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、指定したプロパティ ページを削除し、その関連するウィンドウを破棄します。 オブジェクトのプロパティ ページ、`pPage`パラメーターを指定するまで破棄されませんが、 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)期間が終了します。  
  
##  <a name="a-nameseticonslista--cmfcpropertysheetseticonslist"></a><a name="seticonslist"></a>CMFCPropertySheet::SetIconsList  
 Outlook ウィンドウのナビゲーション コントロールで使用されるイメージの一覧を指定します。  
  
```  
BOOL SetIconsList(
    UINT uiImageListResID,  
    int cx,  
    COLORREF clrTransparent=RGB(255, 0, 255));
void SetIconsList(HIMAGELIST hIcons);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiImageListResID`  
 イメージ リストのリソース ID です。  
  
 [入力] `cx`  
 イメージ リストのアイコンのピクセル単位の幅。  
  
 [入力] `clrTransparent`  
 透明な画像の色。 この色であるイメージの部分は透明になります。 既定値は、マゼンタ、RGB(255,0,255) です。  
  
 [入力] `hIcons`  
 既存のイメージ リストへのハンドル。  
  
### <a name="return-value"></a>戻り値  
 最初のメソッド オーバー ロード構文、`TRUE`場合、このメソッドは正常でない場合は`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 プロパティ シートは、Microsoft Outlook のスタイルでは、フレームワークは、プロパティ シートの左側にある Outlook ウィンドウ コントロールと呼ばれるナビゲーション ボタンの一覧を表示します。 このメソッドを使用すると、Outlook ウィンドウ コントロールで使用するのにイメージのリストを設定できます。  
  
 このメソッドをサポートする方法の詳細については、次を参照してください。 [CImageList::Create](../../mfc/reference/cimagelist-class.md#create)と[CImageList::Add](../../mfc/reference/cimagelist-class.md#add)します。 プロパティ シートのスタイルを設定する方法の詳細については、次を参照してください。 [CMFCPropertySheet::SetLook](#setlook)します。  
  
##  <a name="a-namesetlooka--cmfcpropertysheetsetlook"></a><a name="setlook"></a>CMFCPropertySheet::SetLook  
 プロパティ シートの外観を指定します。  
  
```  
void SetLook(
    PropSheetLook look,  
    int nNavControlWidth=100);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `look`  
 プロパティ シートの外観を指定する列挙値の&1; つ。 プロパティ シートの既定のスタイルは`CMFCPropertySheet::PropSheetLook_Tabs`です。 詳細については、このトピックの「解説」セクションの表を参照してください。  
  
 [入力] `nNavControlWidth`  
 ピクセル単位でのナビゲーション コントロールの幅。 既定値は 100 です。  
  
### <a name="remarks"></a>コメント  
 プロパティ シートを既定とは異なるスタイルを表示するには、プロパティ シートのウィンドウを作成する前に、このメソッドを呼び出します。  
  
 次の表に、列挙値で指定できる、`look`パラメーター。  
  
|値|説明|  
|-----------|-----------------|  
|`CMFCPropertySheet::PropSheetLook_Tabs`|(既定値)各プロパティ ページのタブが表示されます。 タブは、プロパティ シートの上部に表示されるられ、1 つの行に格納できる数以上のタブがある場合に積み重ねられます。|  
|`CMFCPropertySheet::PropSheetLook_OutlookBar`|プロパティ シートの左側にある、Microsoft Outlook バーのスタイルで、ナビゲーション ボタンの一覧を表示します。 リスト内の各ボタンは、プロパティ ページに対応します。 フレームワークでは、一覧の表示領域に収まるより多くのボタンがある場合、スクロール バーの矢印が表示されます。|  
|`CMFCPropertySheet::PropSheetLook_Tree`|プロパティ シートの左側にあるツリー コントロールが表示されます。 各ツリー コントロールのノードの親または子ノードは、プロパティ ページに対応します。 フレームワークでは、ツリー コントロールの可視領域に格納できる以上のノードがある場合、スクロール バーの矢印が表示されます。|  
|`CMFCPropertySheet::PropSheetLook_OneNoteTabs`|Microsoft OneNote の各プロパティ ページのスタイルで、タブが表示されます。 フレームワークでは、プロパティ シートの最上部にタブを表示し、スクロール矢印よりも多くのタブがある場合に&1; 行にできます。|  
|`CMFCPropertySheet::PropSheetLook_List`|プロパティ シートの左側にある一覧を表示します。 各リスト項目は、プロパティ ページに対応します。 フレームワークでは、一覧の表示領域に収まるリスト項目がある場合、スクロール バーの矢印が表示されます。|  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyPage クラス](../../mfc/reference/cmfcpropertypage-class.md)   
 [あります。](../../mfc/reference/cmfcoutlookbar-class.md)

