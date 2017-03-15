---
title: "CMFCRibbonPanel クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonPanel
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonPanel class
ms.assetid: 51d70749-1140-4386-b103-f14082049ba6
caps.latest.revision: 34
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
ms.openlocfilehash: 1f833e1fa59f733734da321718d5db73377fa4bd
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonpanel-class"></a>CMFCRibbonPanel クラス
一連のリボン要素を含むパネルを実装します。 このパネルが描画されると、そのパネルに指定されたサイズに対して可能な限り多くの要素が表示されます。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonPanel : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonPanel::CMFCRibbonPanel](#cmfcribbonpanel)|`CMFCRibbonPanel` オブジェクトを構築して初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonPanel::Add](#add)|パネルにリボン要素を追加します。|  
|[CMFCRibbonPanel::AddSeparator](#addseparator)|リボン パネルに、区切り記号を追加します。|  
|[CMFCRibbonPanel::AddToolBar](#addtoolbar)|リボン パネルにツールバーを追加します。|  
|[CMFCRibbonPanel::FindByData](#findbydata)||  
|[CMFCRibbonPanel::FindByID](#findbyid)|指定されたコマンド ID によって識別される要素を返します|  
|[CMFCRibbonPanel::GetCaptionHeight](#getcaptionheight)||  
|[CMFCRibbonPanel::GetCount](#getcount)|リボン パネルに要素の数を返します。|  
|[CMFCRibbonPanel::GetData](#getdata)|パネルに関連付けられているユーザー定義データを返します。|  
|[CMFCRibbonPanel::GetDefaultButton](#getdefaultbutton)||  
|[CMFCRibbonPanel::GetDroppedDown](#getdroppeddown)||  
|[CMFCRibbonPanel::GetElement](#getelement)|指定したインデックス位置にあるリボン要素を返します。|  
|[CMFCRibbonPanel::GetElements](#getelements)|リボン パネルに格納されているすべての要素を取得します。|  
|[CMFCRibbonPanel::GetElementsByID](#getelementsbyid)||  
|[CMFCRibbonPanel::GetFocused](#getfocused)|フォーカスされた要素を返します。|  
|[CMFCRibbonPanel::GetGalleryRect](#getgalleryrect)|ギャラリーの要素の外接する四角形を返します。|  
|[CMFCRibbonPanel::GetHighlighted](#gethighlighted)||  
|[CMFCRibbonPanel::GetIndex](#getindex)||  
|[CMFCRibbonPanel::GetItemIDsList](#getitemidslist)||  
|[CMFCRibbonPanel::GetName](#getname)||  
|[CMFCRibbonPanel::GetParentButton](#getparentbutton)||  
|[CMFCRibbonPanel::GetParentCategory](#getparentcategory)|リボン パネルの親カテゴリを返します。|  
|[CMFCRibbonPanel::GetParentMenuBar](#getparentmenubar)||  
|[CMFCRibbonPanel::GetPreferedMenuLocation](#getpreferedmenulocation)||  
|[CMFCRibbonPanel::GetPressed](#getpressed)||  
|[CMFCRibbonPanel::GetRect](#getrect)||  
|[CMFCRibbonPanel::GetVisibleElements](#getvisibleelements)|表示される要素の配列を取得します。|  
|[CMFCRibbonPanel::HasElement](#haselement)||  
|[CMFCRibbonPanel::HitTest](#hittest)||  
|[CMFCRibbonPanel::HitTestEx](#hittestex)||  
|[CMFCRibbonPanel::Insert](#insert)|指定された位置にリボン要素を挿入します。|  
|[CMFCRibbonPanel::InsertSeparator](#insertseparator)|指定された位置に、区切り記号を挿入します。|  
|[CMFCRibbonPanel::IsCenterColumnVert](#iscentercolumnvert)|列かどうかすべてのパネル要素を中央揃えする) 縦方向を指定します。|  
|[CMFCRibbonPanel::IsCollapsed](#iscollapsed)||  
|[CMFCRibbonPanel::IsHighlighted](#ishighlighted)||  
|[CMFCRibbonPanel::IsJustifyColumns](#isjustifycolumns)|パネルのすべての列の幅が同じかどうかを指定します。|  
|[CMFCRibbonPanel::IsMainPanel](#ismainpanel)||  
|[CMFCRibbonPanel::IsMenuMode](#ismenumode)||  
|[CMFCRibbonPanel::MakeGalleryItemVisible](#makegalleryitemvisible)|指定したリボン要素を表示するギャラリーをスクロールします。|  
|[CMFCRibbonPanel::OnKey](#onkey)||  
|[CMFCRibbonPanel::RecalcWidths](#recalcwidths)||  
|[CMFCRibbonPanel::Remove](#remove)|削除し、必要に応じて指定したインデックス位置にある要素を削除します。|  
|[CMFCRibbonPanel::RemoveAll](#removeall)|リボン パネルからすべての要素を削除します。|  
|[CMFCRibbonPanel::Replace](#replace)|対応するインデックス値に基づいた別には、1 つの要素を置き換えます。|  
|[CMFCRibbonPanel::ReplaceByID](#replacebyid)|指定されたコマンド ID に基づいて別の&1; つの要素を置き換えます|  
|[CMFCRibbonPanel::SetCenterColumnVert](#setcentercolumnvert)|列単位で要素を縦方向に配置するパネルに指示します。|  
|[CMFCRibbonPanel::SetData](#setdata)|ユーザー定義データをリボン パネルに関連付けます。|  
|[CMFCRibbonPanel::SetElementMenu](#setelementmenu)|指定されたコマンド ID を持つ要素にポップアップ メニューを割り当てる|  
|[CMFCRibbonPanel::SetElementRTC](#setelementrtc)|リボン パネルに指定したランタイム クラス情報で指定したリボン要素を追加します。|  
|[CMFCRibbonPanel::SetElementRTCByID](#setelementrtcbyid)|リボン パネルに指定したランタイム クラス情報で指定したリボン要素を追加します。|  
|[CMFCRibbonPanel::SetFocused](#setfocused)|指定されたリボン要素にフォーカスを設定します。|  
|[CMFCRibbonPanel::SetJustifyColumns](#setjustifycolumns)|有効または列の位置合わせを無効にします。|  
|[CMFCRibbonPanel::SetKeys](#setkeys)|リボン パネルを表示するショートカット キーを設定します。|  
|[CMFCRibbonPanel::ShowPopup](#showpopup)||  
  
## <a name="remarks"></a>コメント  
 リボン パネルは、リボン カテゴリ内で作成した関連するタスクの論理的なグループです。 リボンの変更のサイズと、パネルのレイアウトは自動的に可能な限り多くの要素を表示を調整します。  
  
 呼び出してリボン カテゴリに含まれているパネルをリボンに取得できます、 [CMFCRibbonCategory::GetPanel](../../mfc/reference/cmfcribboncategory-class.md#getpanel)メソッドです。  
  
## <a name="example"></a>例  
 次の例では、構成、`CMFCRibbonPanel`オブジェクトのさまざまなメソッドを使用して、`CMFCRibbonPanel`クラスです。 この例では、リボン パネルを表示するショートカット キーを設定し、列で、パネル内の要素を縦に揃える、列の位置合わせを有効にする方法を示します。 このコード スニペットの一部である、 [MS Office 2007 デモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo&#10;](../../mfc/reference/codesnippet/cpp/cmfcribbonpanel-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxRibbonPanel.h  
  
##  <a name="a-nameadda--cmfcribbonpaneladd"></a><a name="add"></a>CMFCRibbonPanel::Add  
 リボン パネルに含まれているリボン要素の配列を指定したリボン要素を追加します。  
  
```  
virtual void Add(CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力] `pElem`  
 リボン要素へのポインター。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameaddseparatora--cmfcribbonpaneladdseparator"></a><a name="addseparator"></a>CMFCRibbonPanel::AddSeparator  
 リボン パネルに、区切り記号を追加します。  
  
```  
virtual void AddSeparator();
```  
  
### <a name="remarks"></a>コメント  
 リボン パネルに、区切り記号を追加するには、このメソッドを呼び出します。 以前の呼び出しによって追加されたリボン要素の横にある、区切り記号が追加されます[CMFCRibbonPanel::Add](#add)します。 指定位置にある区分線を挿入するには、呼び出す[CMFCRibbonPanel::InsertSeparator](#insertseparator)します。  
  
##  <a name="a-nameaddtoolbara--cmfcribbonpaneladdtoolbar"></a><a name="addtoolbar"></a>CMFCRibbonPanel::AddToolBar  
 リボン パネルにツールバーを追加します。  
  
```  
CMFCRibbonButtonsGroup* AddToolBar(
UINT uiToolbarResID,  
UINT uiColdResID = 0,  
UINT uiHotResID = 0,  
UINT uiDisabledResID = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiToolbarResID`  
 追加するツールバーのリソース ID を指定します。  
  
 [入力] `uiColdResID`  
 ツールバーのコールド イメージのリソース ID を指定します。  
  
 [入力] `uiHotResID`  
 ツールバーのホット イメージのリソース ID を指定します。  
  
 [入力] `uiDisabledResID`  
 ツールバーの無効なイメージのリソース ID を指定します。  
  
### <a name="return-value"></a>戻り値  
 リボン パネルにツールバーを追加するには、このメソッドを呼び出します。 前の呼び出しによって追加されたリボン要素の横にあるツールバーを追加します。 [CMFCRibbonPanel::Add](#add)します。  
  
### <a name="remarks"></a>コメント  
 ツールバー、ホット イメージ、コールド イメージ、および無効なイメージの詳細については、次を参照してください。 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)します。  
  
##  <a name="a-namecmfcribbonpanela--cmfcribbonpanelcmfcribbonpanel"></a><a name="cmfcribbonpanel"></a>CMFCRibbonPanel::CMFCRibbonPanel  
 構築して初期化、 [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)オブジェクトです。  
  
```  
CMFCRibbonPanel(
LPCTSTR lpszName = NULL,  
HICON hIcon = NULL);  
  
CMFCRibbonPanel(CMFCRibbonGallery* pPaletteButton);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszName`  
 リボン パネルの名前です。  
  
 [入力] `hIcon`  
 リボン パネルの既定のボタンのアイコンへのハンドルします。  
  
 [入力] `pPaletteButton`  
 リボン パネルをリボン ギャラリーへのポインター。  
  
##  <a name="a-namefindbydataa--cmfcribbonpanelfindbydata"></a><a name="findbydata"></a>CMFCRibbonPanel::FindByData  
 指定されたデータに関連付けられているリボン要素を取得します。  
  
```  
CMFCRibbonBaseElement* FindByData(DWORD_PTR dwData) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwData`  
 リボン要素に関連付けられたデータ。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、リボン要素へのポインターそれ以外の場合`NULL`します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namefindbyida--cmfcribbonpanelfindbyid"></a><a name="findbyid"></a>CMFCRibbonPanel::FindByID  
 指定されたコマンド ID によって識別されるリボン要素を取得します。  
  
```  
CMFCRibbonBaseElement* FindByID(UINT uiCmdID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmdID`  
 リボン要素のコマンド ID。  
  
### <a name="return-value"></a>戻り値  
 指定されたコマンド ID で識別されるリボン要素それ以外の場合`NULL`指定されたコマンド ID を持つリボン要素が指定されていない場合  
  
##  <a name="a-namegetcaptionheighta--cmfcribbonpanelgetcaptionheight"></a><a name="getcaptionheight"></a>CMFCRibbonPanel::GetCaptionHeight  
 リボン パネルのキャプションの高さを取得します。  
  
```  
int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>戻り値  
 (ピクセル単位) のリボン パネルのキャプションの高さ。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetcounta--cmfcribbonpanelgetcount"></a><a name="getcount"></a>CMFCRibbonPanel::GetCount  
 リボン パネルに含まれるリボン要素の数を取得します。  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リボン パネルに格納されているリボン要素の数。  
  
##  <a name="a-namegetdataa--cmfcribbonpanelgetdata"></a><a name="getdata"></a>CMFCRibbonPanel::GetData  
 パネルに関連付けられているユーザー定義データを返します。  
  
```  
DWORD_PTR GetData() const;  
```  
  
### <a name="return-value"></a>戻り値  
 パネルに関連付けられているユーザー定義データ。  
  
##  <a name="a-namegetdefaultbuttona--cmfcribbonpanelgetdefaultbutton"></a><a name="getdefaultbutton"></a>CMFCRibbonPanel::GetDefaultButton  
 リボン パネルの既定のボタンを取得します。  
  
```  
CMFCRibbonButton& GetDefaultButton();
```  
  
### <a name="return-value"></a>戻り値  
 リボン パネルの既定のボタンです。  
  
### <a name="remarks"></a>コメント  
 リボン パネルにリボン要素を表示する十分な領域がある場合は、既定のボタンが表示されます。  
  
##  <a name="a-namegetdroppeddowna--cmfcribbonpanelgetdroppeddown"></a><a name="getdroppeddown"></a>CMFCRibbonPanel::GetDroppedDown  
 のポップアップ メニューが削除される場合は、リボン要素へのポインターを取得します。  
  
```  
CMFCRibbonBaseElement* GetDroppedDown() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポップアップ メニューがドロップダウン; されてリボン要素へのポインターそれ以外の場合`NULL`リボン要素には、ポップアップ メニューがドロップダウンされていない場合。  
  
### <a name="remarks"></a>コメント  
 リボン パネルに格納されているリボン要素のみがテストされます。  
  
##  <a name="a-namegetelementa--cmfcribbonpanelgetelement"></a><a name="getelement"></a>CMFCRibbonPanel::GetElement  
 指定したインデックス位置にあるリボン要素を返します。  
  
```  
CMFCRibbonBaseElement* GetElement(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 取得する要素の&0; から始まるインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 基本のリボン要素への有効なポインターが位置にある`nIndex`リボン パネルまたは`NULL`指定したインデックス位置に要素が存在しない場合。  
  
##  <a name="a-namegetelementsa--cmfcribbonpanelgetelements"></a><a name="getelements"></a>CMFCRibbonPanel::GetElements  
 リボン パネルに含まれているすべてのリボン要素を取得します。  
  
```  
void GetElements(CArray<CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `arElements`  
 リボン パネルに含まれているすべてのリボン要素を格納する配列。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetelementsbyida--cmfcribbonpanelgetelementsbyid"></a><a name="getelementsbyid"></a>CMFCRibbonPanel::GetElementsByID  
 指定した配列に指定されたコマンド ID を持つリボン要素を追加します。  
  
```  
void GetElementsByID(
UINT uiCmdID,  
CArray<CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmdID`  
 リボン要素のコマンド ID。  
  
 [入力] `arElements`  
 リボン要素の配列。  
  
### <a name="remarks"></a>コメント  
 リボン パネルに格納されているリボン要素のみがテストされます。  
  
##  <a name="a-namegethighlighteda--cmfcribbonpanelgethighlighted"></a><a name="gethighlighted"></a>CMFCRibbonPanel::GetHighlighted  
 リボン パネルに強調表示されているリボン要素を取得します。  
  
```  
CMFCRibbonBaseElement* GetHighlighted() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リボン パネルに強調表示されているリボン要素へのポインター。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetindexa--cmfcribbonpanelgetindex"></a><a name="getindex"></a>CMFCRibbonPanel::GetIndex  
 リボン パネルに含まれるリボン要素の配列から指定されたリボン要素の&0; から始まるインデックスを取得します。  
  
```  
virtual int GetIndex(CMFCRibbonBaseElement* pElem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pElem`  
 リボン要素へのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、指定したリボン要素の&0; から始まるインデックスそれ以外の場合は-1。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetitemidslista--cmfcribbonpanelgetitemidslist"></a><a name="getitemidslist"></a>CMFCRibbonPanel::GetItemIDsList  
 リボン パネル内のすべてのリボン要素のコマンド Id を取得します。  
  
```  
void GetItemIDsList(CList<UINT, UINT>& lstItems) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `lstItems`  
 リボン パネルに格納されているリボン要素のコマンド Id の一覧。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetnamea--cmfcribbonpanelgetname"></a><a name="getname"></a>CMFCRibbonPanel::GetName  
 リボン パネルの名前を取得します。  
  
```  
LPCTSTR GetName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リボン パネルの名前です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetparentbuttona--cmfcribbonpanelgetparentbutton"></a><a name="getparentbutton"></a>CMFCRibbonPanel::GetParentButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCRibbonBaseElement* GetParentButton() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetparentcategorya--cmfcribbonpanelgetparentcategory"></a><a name="getparentcategory"></a>CMFCRibbonPanel::GetParentCategory  
 リボン パネルの親カテゴリを返します。  
  
```  
CMFCRibbonCategory* GetParentCategory() const;  
```  
  
### <a name="return-value"></a>戻り値  
 このリボン パネルを含むリボン カテゴリへのポインター。  
  
##  <a name="a-namegetparentmenubara--cmfcribbonpanelgetparentmenubar"></a><a name="getparentmenubar"></a>CMFCRibbonPanel::GetParentMenuBar  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCRibbonPanelMenuBar* GetParentMenuBar() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetpreferedmenulocationa--cmfcribbonpanelgetpreferedmenulocation"></a><a name="getpreferedmenulocation"></a>CMFCRibbonPanel::GetPreferedMenuLocation  
 リボン パネルのポップアップ メニューを表示する適切な四角形を取得します。  
  
```  
virtual BOOL GetPreferedMenuLocation(CRect& rect);
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `rect`  
 このパラメーターは使用されません。  
  
### <a name="return-value"></a>戻り値  
 常に `FALSE` を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは常に `FALSE` を返します。 リボン パネルのポップアップ メニューを表示する適切な四角形を取得するには、このメソッドをオーバーライドします。  
  
##  <a name="a-namegetpresseda--cmfcribbonpanelgetpressed"></a><a name="getpressed"></a>CMFCRibbonPanel::GetPressed  
 ユーザーが現在押した場合は、リボン パネルにリボン要素へのポインターを取得します。  
  
```  
CMFCRibbonBaseElement* GetPressed() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ユーザーが現在それを押した場合は、リボン要素へのポインターそれ以外の場合`NULL`します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetrecta--cmfcribbonpanelgetrect"></a><a name="getrect"></a>CMFCRibbonPanel::GetRect  
 リボン パネルを表示する四角形を取得します。  
  
```  
const CRect& GetRect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リボン パネルを表示する四角形。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namehaselementa--cmfcribbonpanelhaselement"></a><a name="haselement"></a>CMFCRibbonPanel::HasElement  
 リボン パネルに指定したリボン要素が含まれるかどうかを示します。  
  
```  
BOOL HasElement(const CMFCRibbonBaseElement* pElem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pElem`  
 リボン要素へのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`リボン パネルには、指定したリボン要素が含まれている場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namehighlighta--cmfcribbonpanelhighlight"></a><a name="highlight"></a>CMFCRibbonPanel::Highlight  
 選択されたリボン パネル、およびポイントによって指定されたリボン要素の強調表示色を設定します。  
  
```  
virtual void Highlight(
BOOL bHighlight,  
CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bHighlight`  
 `TRUE`リボン パネルを強調表示するには`FALSE`をリボン パネルの強調表示を解除します。  
  
 [入力] `point`  
 ウィンドウの左上隅に対して相対的では、ポインターの x 座標と y を調整します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namehittesta--cmfcribbonpanelhittest"></a><a name="hittest"></a>CMFCRibbonPanel::HitTest  
 指定した点が含まれる場合は、リボン要素を取得します。  
  
```  
virtual CMFCRibbonBaseElement* HitTest(
CPoint point,  
BOOL bCheckPanelCaption = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 ウィンドウの左上隅に対して相対的では、ポインターの x 座標と y を調整します。  
  
 [入力] `bCheckPanelCaption`  
 `TRUE`リボン パネルのキャプションをテストするにはそれ以外の場合`FALSE`します。  
  
### <a name="return-value"></a>戻り値  
 指定したポイントがそれにある場合は、リボン要素へのポインターそれ以外の場合`NULL`します。  
  
### <a name="remarks"></a>コメント  
 リボン パネルに格納されているリボン要素のみがテストされます。  
  
##  <a name="a-namehittestexa--cmfcribbonpanelhittestex"></a><a name="hittestex"></a>CMFCRibbonPanel::HitTestEx  
 含まれている指定したポイントを持つリボン要素の&0; から始まるインデックスを取得します。  
  
```  
virtual int HitTestEx(CPoint point) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 ウィンドウの左上隅に対して相対的では、ポインターの x 座標と y を調整します。  
  
### <a name="return-value"></a>戻り値  
 含まれている、指定したポイントを持つリボン要素の&0; から始まるインデックスそれ以外の場合は-1。  
  
### <a name="remarks"></a>コメント  
 リボン パネルに格納されているリボン要素のみがテストされます。  
  
##  <a name="a-nameinserta--cmfcribbonpanelinsert"></a><a name="insert"></a>CMFCRibbonPanel::Insert  
 リボン パネルに含まれているリボン要素の配列の指定位置にある指定したリボン要素を挿入します。  
  
```  
virtual BOOL Insert(
CMFCRibbonBaseElement* pElem,  
int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力] `pElem`  
 リボン要素へのポインター。  
  
 [入力] `nIndex`  
 0 から始まる値は、-1 から配列に格納されているリボン要素の数までです。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`リボン要素が正常に挿入された場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 場合の値`nIndex`-1 で、または`nIndex`配列内のリボン要素の数に等しく、指定されたリボン要素が配列の末尾に追加します。 場合の値`nIndex`が範囲外にこのメソッドは失敗します。  
  
##  <a name="a-nameinsertseparatora--cmfcribbonpanelinsertseparator"></a><a name="insertseparator"></a>CMFCRibbonPanel::InsertSeparator  
 指定された位置に、区切り記号を挿入します。  
  
```  
virtual BOOL InsertSeparator(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 区切り記号が挿入される位置の&0; から始まるインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`区切り記号が正常に挿入されている場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 指定された位置にある区分線を挿入するには、このメソッドを呼び出す`nIndex`します。 最後に追加されたリボン要素の横にある区分線を挿入するには、呼び出す[CMFCRibbonPanel::AddSeparator](#addseparator)します。  
  
##  <a name="a-nameiscentercolumnverta--cmfcribbonpaneliscentercolumnvert"></a><a name="iscentercolumnvert"></a>CMFCRibbonPanel::IsCenterColumnVert  
 リボン要素の垂直方向の位置が、表示する四角形の中央に配置するかどうかを示します。  
  
```  
BOOL IsCenterColumnVert() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`リボン要素が、表示領域の四角形の中央に配置、垂直方向の配置の場合それ以外の場合`FALSE`します。  
  
##  <a name="a-nameiscollapseda--cmfcribbonpaneliscollapsed"></a><a name="iscollapsed"></a>CMFCRibbonPanel::IsCollapsed  
 水平方向に、リボン パネルの表示サイズが最小化されているかどうかを示します。  
  
```  
BOOL IsCollapsed() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`リボン パネルの表示サイズが、水平方向に最小化されている場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 リボン パネルが折りたたまれている場合、既定のボタン、その名前、および下向きの矢印がのみ表示します。  
  
##  <a name="a-nameishighlighteda--cmfcribbonpanelishighlighted"></a><a name="ishighlighted"></a>CMFCRibbonPanel::IsHighlighted  
 リボン パネルの表示が強調表示されているかどうかを示します。  
  
```  
BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は、リボン パネルの表示が強調表示されます。それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 リボン パネルの表示は、ポインターが上にあるときに強調表示されます。  
  
##  <a name="a-nameisjustifycolumnsa--cmfcribbonpanelisjustifycolumns"></a><a name="isjustifycolumns"></a>CMFCRibbonPanel::IsJustifyColumns  
 リボン パネルに同じ列にあるリボン要素の表示サイズが同じ幅に設定するかどうかを示します。  
  
```  
BOOL IsJustifyColumns() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`リボン パネルに同じ列にあるリボン要素の表示サイズが同一の幅に設定されている場合それ以外の場合`FALSE`します。  
  
##  <a name="a-nameismainpanela--cmfcribbonpanelismainpanel"></a><a name="ismainpanel"></a>CMFCRibbonPanel::IsMainPanel  
 リボン パネルがリボンのメイン パネルであるかどうかを示します。  
  
```  
virtual BOOL IsMainPanel() const;  
```  
  
### <a name="return-value"></a>戻り値  
 常に `FALSE` を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは常に `FALSE` を返します。 リボン パネルが、メインのリボン パネルであるかどうかを示すためには、このメソッドをオーバーライドします。  
  
 ユーザーがアプリケーション ボタンを選択すると、メインのリボン パネルが表示されます。  
  
##  <a name="a-nameismenumodea--cmfcribbonpanelismenumode"></a><a name="ismenumode"></a>CMFCRibbonPanel::IsMenuMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsMenuMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonkeya--cmfcribbonpanelonkey"></a><a name="onkey"></a>CMFCRibbonPanel::OnKey  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnKey(UINT nChar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nChar`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namerecalcwidthsa--cmfcribbonpanelrecalcwidths"></a><a name="recalcwidths"></a>CMFCRibbonPanel::RecalcWidths  
 リボン パネルの各表示レイアウトの構成の幅を再計算します。  
  
```  
virtual void RecalcWidths(
CDC* pDC,  
int nHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 リボン パネル用のデバイス コンテキストへのポインター。  
  
 [入力] `nHeight`  
 リボン パネルの高さ。  
  
### <a name="remarks"></a>コメント  
 リボン パネルは、使用可能な幅の変化に応じてそのレイアウトの構成を変更します。  
  
##  <a name="a-nameremovea--cmfcribbonpanelremove"></a><a name="remove"></a>CMFCRibbonPanel::Remove  
 削除し、必要に応じて指定したインデックス位置にある要素を削除します。  
  
```  
BOOL Remove(
int nIndex,  
BOOL bDelete = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 リボン パネルから削除される要素の&0; から始まるインデックスを指定します。  
  
 [入力] `bDelete`  
 `TRUE`削除される要素を削除するにはそれ以外の場合、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`要素を削除し、削除された場合 (場合`bDelete`は`TRUE`) です。`FALSE`要素が削除されなかったかどうか、またはにリボン要素が存在しない場合がある`nIndex`です。  
  
### <a name="remarks"></a>コメント  
 リボン パネルから要素を削除するには、このメソッドを呼び出します。  
  
##  <a name="a-nameremovealla--cmfcribbonpanelremoveall"></a><a name="removeall"></a>CMFCRibbonPanel::RemoveAll  
 リボン パネルからすべてのリボン要素を削除します。  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>コメント  
 すべてのリボン要素は、リボン パネルから削除され、破棄されます。  
  
##  <a name="a-namereplacea--cmfcribbonpanelreplace"></a><a name="replace"></a>CMFCRibbonPanel::Replace  
 他のインデックス値に基づいて&1; つの要素を置き換えます。  
  
```  
BOOL Replace(
int nIndex,  
CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 置換する要素の&0; から始まるインデックスを指定します。  
  
 [in][out]`pElem`  
 元の要素を置換する要素に有効なポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`元のリボン要素は、新しいリボン要素が正常に交換している場合`FALSE`リボン要素を交換がない場合、または指定したインデックス位置に要素が存在しない場合。  
  
### <a name="remarks"></a>コメント  
 コマンド ID を使用してリボン要素を置換するには、呼び出す[CMFCRibbonPanel::ReplaceByID](#replacebyid)します。  
  
##  <a name="a-namereplacebyida--cmfcribbonpanelreplacebyid"></a><a name="replacebyid"></a>CMFCRibbonPanel::ReplaceByID  
 指定されたコマンド ID に基づいて別の&1; つの要素を置き換えます  
  
```  
BOOL ReplaceByID(
UINT uiCmdID,  
CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmdID`  
 置き換える要素のコマンド ID を指定します。  
  
 [in][out]`pElem`  
 元の要素を置換する要素に有効なポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`元のリボン要素は、新しいリボン要素が正常に交換している場合`FALSE`リボン要素が置き換えられない場合、または指定されたコマンド ID を持つ要素は存在しません。  
  
### <a name="remarks"></a>コメント  
 位置に基づいてリボン要素を交換するには、呼び出す[CMFCRibbonPanel::Replace](#replace)します。  
  
##  <a name="a-namesetcentercolumnverta--cmfcribbonpanelsetcentercolumnvert"></a><a name="setcentercolumnvert"></a>CMFCRibbonPanel::SetCenterColumnVert  
 有効または無効、表示する四角形内のリボン要素の垂直方向の位置の中心の位置します。  
  
```  
void SetCenterColumnVert(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bSet`  
 `TRUE`リボン要素の表示領域の四角形内の垂直方向の位置を中央に配置します。`FALSE`この機能を無効にします。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetdataa--cmfcribbonpanelsetdata"></a><a name="setdata"></a>CMFCRibbonPanel::SetData  
 ユーザー定義データをリボン パネルに関連付けます。  
  
```  
void SetData(DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwData`  
 設定するユーザー定義データを指定します。  
  
### <a name="remarks"></a>コメント  
 リボン パネルにユーザー定義データを関連付けるには、このメソッドを呼び出します。  
  
##  <a name="a-namesetelementmenua--cmfcribbonpanelsetelementmenu"></a><a name="setelementmenu"></a>CMFCRibbonPanel::SetElementMenu  
 指定されたコマンド ID を持つ要素にポップアップ メニューを割り当てる  
  
```  
BOOL SetElementMenu(
UINT uiCmdID,  
HMENU hMenu,  
BOOL bIsDefautCommand = FALSE,  
BOOL bRightAlign = FALSE);

 
BOOL SetElementMenu(
UINT uiCmdID,  
UINT uiMenuResID,  
BOOL bIsDefautCommand = FALSE,  
BOOL bRightAlign = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmdID`  
 メニューが追加リボン要素のコマンド ID を指定します。  
  
 [入力] `hMenu`  
 リボン パネルに追加する Windows メニューへのハンドルを指定します。  
  
 [入力] `bIsDefautCommand`  
 `TRUE`リボン要素をクリックすると、そのリボン要素に関連付けられているコマンドを実行すべきことを指定します。 この場合、ユーザーがリボン要素の横の矢印をクリックするとメニューが開いたのみです。 `FALSE`リボン要素をクリックするとリボン要素に関連付けられているコマンドが実行しないことを指定します。 この場合、ユーザーが要素上をクリックしてに関係なく、ポップアップ メニューが表示されます。  
  
 [入力] `bRightAlign`  
 `TRUE`ポップアップ メニューが右揃えになります。 にはそれ以外の場合、`FALSE`です。  
  
 [入力] `uiMenuResID`  
 リボン パネルに追加するメニューのリソース ID を指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メニューがリボン要素に割り当てられている場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 指定されたコマンド ID を持つリボン要素にポップアップ メニューを割り当てるには、このメソッドを呼び出す  
  
##  <a name="a-namesetelementrtca--cmfcribbonpanelsetelementrtc"></a><a name="setelementrtc"></a>CMFCRibbonPanel::SetElementRTC  
 リボン パネルに指定したランタイム クラス情報で指定されているリボン要素を追加します。  
  
```  
CMFCRibbonBaseElement* SetElementRTC(
int nIndex,  
CRuntimeClass* pRTC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 追加するリボン要素の&0; から始まるインデックスを指定します。  
  
 [in][out]`pRTC`  
 リボン パネルに追加されるリボン要素のランタイム クラス情報へのポインター。  
  
### <a name="return-value"></a>戻り値  
 指定したランタイム クラス情報を使用して作成されたリボン要素。  
  
### <a name="remarks"></a>コメント  
 リボン パネルにカスタム要素 (たとえば、色のボタン) を追加する場合は、カスタム要素のランタイム クラス情報を指定する必要があります。 リボンは、この情報を格納し、カスタム要素を作成 (で識別される) に配置される既存の要素を置き換えます指定されたコマンド id。 リボンは、新しく作成した要素にポインターを返します。  
  
##  <a name="a-namesetelementrtcbyida--cmfcribbonpanelsetelementrtcbyid"></a><a name="setelementrtcbyid"></a>CMFCRibbonPanel::SetElementRTCByID  
 リボン パネルに指定したランタイム クラス情報で指定されているリボン要素を追加します。  
  
```  
CMFCRibbonBaseElement* SetElementRTCByID(
UINT uiCmdID,  
CRuntimeClass* pRTC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmdID`  
 追加するリボン要素のコマンド ID を指定します。  
  
 [in][out]`pRTC`  
 リボン パネルに追加されるリボン要素に関連付けられているランタイム クラス情報へのポインター。  
  
### <a name="return-value"></a>戻り値  
 指定したランタイム クラス情報を使用して作成されたリボン要素。  
  
### <a name="remarks"></a>コメント  
 リボン パネルにカスタム要素 (たとえば、色のボタン) を追加する場合は、カスタム要素のランタイム クラス情報を指定する必要があります。 リボンのこの情報を格納、カスタム要素を作成、および指定されたコマンド ID によって検索された既存の要素を置き換えます 新しく作成された要素へのポインターを返します。  
  
### <a name="example"></a>例  
 次の例では、使用する方法、`SetElementRTCByID`メソッド。  
  
```  
 
// Load and add toolbar with standard buttons. This toolbar  
// should display a custom color button with id ID_CHAR_COLOR:  
 
pPanel->AddToolBar(IDR_MAINFRAME,
    IDB_MAINFRAME256);

CMFCRibbonColorButton* pColorButton = 
(CMFCRibbonColorButton*)pPanel->SetElementRTCByID(
ID_CHAR_COLOR,
    RUNTIME_CLASS (CMFCRibbonColorButton));

 
// SetElementRTCByID sets runtime class and returns a pointer  
// to the newly created custom button,
    which can be set up immediately:  
pColorButton->EnableAutomaticButton(_T("Automatic"),
    RGB (0,
    0,
    0));  
```  
  
##  <a name="a-namesetjustifycolumnsa--cmfcribbonpanelsetjustifycolumns"></a><a name="setjustifycolumns"></a>CMFCRibbonPanel::SetJustifyColumns  
 有効または同じ列内のリボン要素の幅の調整を無効にします。  
  
```  
void SetJustifyColumns(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bSet`  
 `TRUE`列にある最大のリボン要素の幅に同じ列内のリボン要素の幅を調整するには`FALSE`この幅の調整を無効にします。  
  
### <a name="remarks"></a>コメント  
 この機能は、リボン パネルに有効な場合、同じ列の最大のリボン要素の幅に同じ列内のリボン要素の幅が調整されます。  
  
##  <a name="a-namesetkeysa--cmfcribbonpanelsetkeys"></a><a name="setkeys"></a>CMFCRibbonPanel::SetKeys  
 リボン パネルの既定のボタンの keytip を設定します。  
  
```  
void SetKeys(LPCTSTR lpszKeys);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszKeys`  
 リボン パネルの既定のボタンの keytip します。  
  
### <a name="remarks"></a>コメント  
 リボン パネルにリボン要素を表示する十分な領域がある場合は、既定のボタンが表示されます。  
  
##  <a name="a-nameshowpopupa--cmfcribbonpanelshowpopup"></a><a name="showpopup"></a>CMFCRibbonPanel::ShowPopup  
 作成し、リボン パネルのポップアップ メニューを表示します。  
  
```  
CMFCRibbonPanelMenu* ShowPopup(CMFCRibbonDefaultPanelButton* pButton = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pButton`  
 既定のボタンをリボン パネルへのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、リボン パネル用のポップアップ メニューへのポインターそれ以外の場合`NULL`します。  
  
### <a name="remarks"></a>コメント  
 リボン パネルのポップアップ メニューを使用できるは、リボン パネルの表示が折りたたまれている場合だけです。  
  
##  <a name="a-namesetfocuseda--cmfcribbonpanelsetfocused"></a><a name="setfocused"></a>CMFCRibbonPanel::SetFocused  
 指定されたリボン要素にフォーカスを設定します。  
  
```  
void SetFocused(CMFCRibbonBaseElement* pNewFocus);
```  
  
### <a name="parameters"></a>パラメーター  
 `pNewFocus`  
 フォーカスを受け取るリボン要素へのポインター。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namemakegalleryitemvisiblea--cmfcribbonpanelmakegalleryitemvisible"></a><a name="makegalleryitemvisible"></a>CMFCRibbonPanel::MakeGalleryItemVisible  
 指定したリボン要素を表示するギャラリーをスクロールします。  
  
```  
void MakeGalleryItemVisible(CMFCRibbonBaseElement* pItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 表示するリボン要素へのポインター。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameiswindows7looka--cmfcribbonpaneliswindows7look"></a><a name="iswindows7look"></a>CMFCRibbonPanel::IsWindows7Look  
 親リボンが Windows 7 (小さい四角形のアプリケーションのボタン) の形式を持つかどうかを示します。  
  
```  
BOOL IsWindows7Look() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`親のリボンに表示します。 Windows 7 がある場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetvisibleelementsa--cmfcribbonpanelgetvisibleelements"></a><a name="getvisibleelements"></a>CMFCRibbonPanel::GetVisibleElements  
 表示される要素の配列を取得します。  
  
```  
void GetVisibleElements(
CArray<CMFCRibbonBaseElement*,  
CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>パラメーター  
 `arElements`  
 関数から制御が戻るとき、このパラメーターには、表示される要素の配列が含まれています。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetgalleryrecta--cmfcribbonpanelgetgalleryrect"></a><a name="getgalleryrect"></a>CMFCRibbonPanel::GetGalleryRect  
 ギャラリーの要素の外接する四角形を返します。  
  
```  
CRect GetGalleryRect();
```  
  
### <a name="return-value"></a>戻り値  
 サイズとこのパネル内のギャラリー要素の位置。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetfocuseda--cmfcribbonpanelgetfocused"></a><a name="getfocused"></a>CMFCRibbonPanel::GetFocused  
 フォーカスされた要素を返します。  
  
```  
CMFCRibbonBaseElement* GetFocused() const;  
```  
  
### <a name="return-value"></a>戻り値  
 フォーカスのある要素へのポインターまたは`NULL`です。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [CMFCRibbonCategory クラス](../../mfc/reference/cmfcribboncategory-class.md)   
 [CMFCRibbonBaseElement クラス](../../mfc/reference/cmfcribbonbaseelement-class.md)

