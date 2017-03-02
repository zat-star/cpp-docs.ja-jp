---
title: "CMFCToolBarsCustomizeDialog クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarsCustomizeDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarsCustomizeDialog class
ms.assetid: 78e2cddd-4f13-4097-afc3-1ad646a113f1
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 069498d958dd5d9c3befc2a179c67636ce0ac9ae
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarscustomizedialog-class"></a>CMFCToolBarsCustomizeDialog クラス
モードレス タブ ダイアログ ボックス ( [CPropertySheet クラス](../../mfc/reference/cpropertysheet-class.md)) ユーザーがツールバー、メニューのショートカット キー、ユーザー定義のツールおよびアプリケーションで visual スタイルをカスタマイズできるようにします。 通常、このダイアログ ボックスを表示するには、 **[ツール]** メニューの **[ユーザー設定]** をクリックします。  
  
 **カスタマイズ**ダイアログ ボックスには&6; つのタブ:**コマンド**、**ツールバー**、**ツール**、**キーボード**、**メニュー**、および**オプション**します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCToolBarsCustomizeDialog : public CPropertySheet  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog](#cmfctoolbarscustomizedialog)|`CMFCToolBarsCustomizeDialog` オブジェクトを構築します。|  
|`CMFCToolBarsCustomizeDialog::~CMFCToolBarsCustomizeDialog`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::AddButton](#addbutton)|コマンドの一覧にツール バー ボタンを挿入、**コマンド**ページ|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::AddMenu](#addmenu)|リソースとの呼び出しからメニューを読み込み[CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)にコマンドの一覧にそのメニューを追加する、**コマンド**ページです。|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)|リソースとの呼び出しからメニューを読み込み[CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)にコマンドの一覧にそのメニューを追加する、**コマンド**ページです。|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar)|リソースからツールバーを読み込みます。 次に、メニューの呼び出し内の各コマンド、 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton)にコマンドの一覧にあるボタンを挿入するメソッド、**コマンド**指定したカテゴリのページです。|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::Create](#create)|表示、**カスタマイズ** ダイアログ ボックス。|  
|`CMFCToolBarsCustomizeDialog::EnableTools`|将来使用するために予約されています。|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars](#enableuserdefinedtoolbars)|有効またはを使用して新しいツールバーの作成を無効にします**カスタマイズ** ダイアログ ボックス。|  
|[CMFCToolBarsCustomizeDialog::FillAllCommandsList](#fillallcommandslist)|指定された設定`CListBox`なコマンドでオブジェクト、**すべてのコマンド**カテゴリ。|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox)|指定された設定`CComboBox`の各コマンドのカテゴリの名前を持つオブジェクト、**カスタマイズ** ダイアログ ボックス。|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox)|指定された設定`CListBox`の各コマンドのカテゴリの名前を持つオブジェクト、**カスタマイズ** ダイアログ ボックス。|  
|[CMFCToolBarsCustomizeDialog::GetCommandName](#getcommandname)|指定されたコマンド ID に関連付けられている名前を取得します。|  
|[CMFCToolBarsCustomizeDialog::GetCountInCategory](#getcountincategory)|指定したテキスト ラベルを持つ指定されたリスト内の項目の数を取得します。|  
|[CMFCToolBarsCustomizeDialog::GetFlags](#getflags)|ダイアログ ボックスの動作に影響するフラグのセットを取得します。|  
|`CMFCToolBarsCustomizeDialog::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage](#onedittoolbarmenuimage)|イメージ エディターを起動し、ユーザーがツール バー ボタンやメニュー項目のアイコンをカスタマイズすることができます。|  
|[CMFCToolBarsCustomizeDialog::OnInitDialog](#oninitdialog)|プロパティ シートの初期化処理を強化するよりも優先されます。 (上書き[CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog))。|  
|[CMFCToolBarsCustomizeDialog::PostNcDestroy](#postncdestroy)|ウィンドウが破棄された後に、フレームワークによって呼び出されます。 (`CPropertySheet::PostNcDestroy` をオーバーライドします)。|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::RemoveButton](#removebutton)|指定したカテゴリまたはすべてのカテゴリは、指定されたコマンド ID を持つボタンを削除します。|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory)|カテゴリのリスト ボックスでカテゴリの名前を変更、**コマンド** タブをクリックします。|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton)|コマンドの一覧内のボタンが置き換えられます、**コマンド**新規ツール バー ボタン オブジェクトを持つタブです。|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::SetUserCategory](#setusercategory)|表示されるカテゴリの一覧にカテゴリを追加、**コマンド** タブをクリックします。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity)|ユーザー定義のツールの一覧が有効かどうかを判断するためにフレームワークによって呼び出されます。|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnAfterChangeTool](#onafterchangetool)|ユーザー定義のツールのプロパティを変更するときに、フレームワークによって呼び出されます。|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnAssignKey](#onassignkey)|アクションに指定されたキーボード ショートカットを割り当てることがあるかどうかを決定します。|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnBeforeChangeTool](#onbeforechangetool)|ユーザー定義のツールを変更できるかどうかを決定します。|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnInitToolsPage](#oninittoolspage)|選択すると、フレームワークが呼び出します、**ツール** タブを要求します。|  
  
## <a name="remarks"></a>コメント  
 表示する、**カスタマイズ** ダイアログ ボックスで、作成、`CMFCToolBarsCustomizeDialog`オブジェクトと呼び出し、 [CMFCToolBarsCustomizeDialog::Create](#create)メソッドです。  
  
 中に、**カスタマイズ** ダイアログ ボックスがアクティブで、アプリケーションのカスタマイズのタスクにユーザーを制限する特殊なモードで動作します。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCToolBarsCustomizeDialog`クラスです。 例では、コマンドのリスト ボックスにツール バー ボタンを交換する方法を示しています、**コマンド** ページを使用して新しいツールバーの作成を有効にする、**カスタマイズ** ダイアログ ボックスで、表示、**カスタマイズ** ダイアログ ボックス。 このコード スニペットの一部である、 [IE のデモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_IEDemo&4;](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 `CMFCToolBarsCustomizeDialog`   
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxToolBarsCustomizeDialog.h  
  
##  <a name="a-nameaddbuttona--cmfctoolbarscustomizedialogaddbutton"></a><a name="addbutton"></a>CMFCToolBarsCustomizeDialog::AddButton  
 コマンドの一覧にツール バー ボタンを挿入、**コマンド**ページです。  
  
```  
void AddButton(
    UINT uiCategoryId,  
    const CMFCToolBarButton& button,  
    int iInsertBefore=-1);

void AddButton(
    LPCTSTR lpszCategory,  
    const CMFCToolBarButton& button,  
    int iInsertBefore=-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCategoryId`  
 ボタンを挿入するカテゴリの ID を指定します。  
  
 [入力] `button`  
 挿入するボタンを指定します。  
  
 [入力] `iInsertBefore`  
 ボタンの挿入位置の前に、ツール バー ボタンの&0; から始まるインデックスを指定します。  
  
 [入力] `lpszCategory`  
 ボタンを挿入するカテゴリ文字列を指定します。  
  
### <a name="remarks"></a>コメント  
 `AddButton`メソッド (ID_FILE_MRU_FILE1) などの標準コマンド Id を持つボタンを無視する、コマンドは使用できません (を参照してください[CMFCToolBar::IsCommandPermitted](../../mfc/reference/cmfctoolbar-class.md#iscommandpermitted)) ボタンのダミーとします。  
  
 このメソッドと同じ型の新しいオブジェクトを作成する`button`(通常、 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)) ボタンのランタイム クラスを使用しています。 順に呼び出して[CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom)  ボタンのデータ メンバーをコピーし、指定したカテゴリに、コピーを挿入します。  
  
 新しいボタンが挿入されると、受信、`OnAddToCustomizePage`通知します。  
  
 場合`iInsertBefore`-1 で、カテゴリの一覧に、ボタンが追加されます。 それ以外の場合、指定したインデックス項目の前に挿入されます。  
  
### <a name="example"></a>例  
 次の例では、使用して、`AddButton`のメソッド、`CMFCToolBarsCustomizeDialog`クラスです。 このコード スニペットの一部である、[スライダー サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_Slider&#1;](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_2.cpp)]  
  
##  <a name="a-nameaddmenua--cmfctoolbarscustomizedialogaddmenu"></a><a name="addmenu"></a>CMFCToolBarsCustomizeDialog::AddMenu  
 リソースとの呼び出しからメニューを読み込み[CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)にコマンドの一覧にそのメニューを追加する、**コマンド**ページです。  
  
```  
BOOL AddMenu(UINT uiMenuResId);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiMenuResId`  
 読み込むメニューのリソース ID を指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メニューが正常に追加された場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 呼び出しで`AddMenuCommands`、`bPopup`は`FALSE`です。 その結果、そのメソッドでは、コマンドの一覧にサブメニューを含むメニュー項目は追加されません。 このメソッドは、コマンドの一覧に、サブメニューのメニュー項目を追加は。  
  
##  <a name="a-nameaddmenucommandsa--cmfctoolbarscustomizedialogaddmenucommands"></a><a name="addmenucommands"></a>CMFCToolBarsCustomizeDialog::AddMenuCommands  
 コマンドの一覧に項目を追加、**コマンド**ページを指定したメニュー内のすべての項目を表します。  
  
```  
void AddMenuCommands(
    const CMenu* pMenu,  
    BOOL bPopup,  
    LPCTSTR lpszCategory=NULL,  
    LPCTSTR lpszMenuPath=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMenu`  
 追加する CMenu オブジェクトへのポインター。  
  
 [入力] `bPopup`  
 コマンドの一覧に、ポップアップ メニュー項目を挿入するかどうかを指定します。  
  
 [入力] `lpszCategory`  
 メニューを挿入するカテゴリの名前。  
  
 [入力] `lpszMenuPath`  
 コマンドが表示されている場合、名前に追加されるプレフィックス、**すべてのカテゴリ** ボックスの一覧です。  
  
### <a name="remarks"></a>コメント  
 `AddMenuCommands`のすべてのメニュー項目の上のメソッドに対してループ`pMenu`します。 サブメニューが含まれていないメニュー項目ごとに、このメソッドを作成、 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)オブジェクトと呼び出し、 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton)で、コマンドの一覧にツール バー ボタンとメニュー項目を追加する方法、**コマンド**ページです。 区切り記号は、このプロセスで無視されます。  
  
 場合`bPopup`は`TRUE`、サブメニューを持つメニュー項目ごとに、このメソッドを作成、 [CMFCToolBarMenuButton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)オブジェクトし、コマンドの一覧に呼び出すことによって挿入`AddButton`します。 それ以外の場合をサブメニューを持つメニュー項目は、コマンドの一覧には表示されません。 いずれの場合と`AddMenuCommands`メニュー項目を検出したサブメニューに自身を呼び出したのポインターとしてサブメニューを渡して、再帰的に、`pMenu`パラメーターとサブメニューのラベルを追加`lpszMenuPath`します。  
  
##  <a name="a-nameaddtoolbara--cmfctoolbarscustomizedialogaddtoolbar"></a><a name="addtoolbar"></a>CMFCToolBarsCustomizeDialog::AddToolBar  
 リソースからツールバーを読み込みます。 次に、メニューの呼び出し内の各コマンド、 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton)にコマンドの一覧にあるボタンを挿入するメソッド、**コマンド**指定したカテゴリのページです。  
  
```  
BOOL AddToolBar(
    UINT uiCategoryId,  
    UINT uiToolbarResId);

BOOL AddToolBar(
    LPCTSTR lpszCategory,  
    UINT uiToolbarResId);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCategoryId`  
 ツールバーを追加するカテゴリのリソース ID を指定します。  
  
 [入力] `uiToolbarResId`  
 コマンドの一覧に挿入するコマンドがツールバーのリソース ID を指定します。  
  
 [入力] `lpszCategory`  
 ツールバーを追加するカテゴリの名前を指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メソッドが成功した場合それ以外の場合`FALSE`します。  
  
### <a name="example"></a>例  
 次の例では、使用して、`AddToolBar`メソッドで、`CMFCToolBarsCustomizeDialog`クラスです。 このコード スニペットの一部である、 [Word パッド サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_WordPad&#11;](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_3.cpp)]  
  
### <a name="remarks"></a>コメント  
 各コマンドを表すために使用するコントロールが、 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)オブジェクトです。 ツールバーを追加した後に置き換えることができます、ボタンの派生型のコントロールを呼び出して[CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton)します。  
  
##  <a name="a-namechecktoolsvaliditya--cmfctoolbarscustomizedialogchecktoolsvalidity"></a><a name="checktoolsvalidity"></a>CMFCToolBarsCustomizeDialog::CheckToolsValidity  
 ユーザー ツールの一覧の有効性を確認します。  
  
```  
virtual BOOL CheckToolsValidity(const CObList& lstTools);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lstTools`  
 確認するためのツールのユーザー定義の一覧。  
  
### <a name="return-value"></a>戻り値  
 返します。`TRUE`ツールのユーザー定義の一覧が有効な場合`FALSE`します。 既定の実装を常に`TRUE`します。  
  
### <a name="remarks"></a>コメント  
 フレームワークによって返されるユーザー定義のツールを表すオブジェクトの有効性を確認するには、このメソッドを呼び出して[CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity)します。  
  
 オーバーライド、`CheckToolsValidity`から派生したクラスのメソッドに`CMFCToolBarsCustomizeDialog`をユーザーがダイアログ ボックスを閉じる前にユーザー ツールを検証するかどうか。 このメソッドが戻る場合`FALSE`、ユーザーがいずれかをクリックしたとき、**閉じる** ダイアログ ボックスまたはというラベルの付いたボタンの右上隅のボタン**閉じる**ダイアログ ボックスを表示 ダイアログ ボックスの右下隅にある、**ツール**終了ではなくタブをクリックします。 このメソッドが戻る場合`FALSE`、ユーザーがから移動しようとするタブをクリックすると、**ツール**タブで、移動は実行されません。 検証が失敗する原因となった問題をユーザーに通知する適切なメッセージ ボックスを表示する必要があります。  
  
##  <a name="a-namecmfctoolbarscustomizedialoga--cmfctoolbarscustomizedialogcmfctoolbarscustomizedialog"></a><a name="cmfctoolbarscustomizedialog"></a>CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog  
 `CMFCToolBarsCustomizeDialog` オブジェクトを構築します。  
  
```  
CMFCToolBarsCustomizeDialog(
    CFrameWnd* pWndParentFrame,  
    BOOL bAutoSetFromMenus = FALSE,  
    UINT uiFlags = (AFX_CUSTOMIZE_MENU_SHADOWS | AFX_CUSTOMIZE_TEXT_LABELS | AFX_CUSTOMIZE_MENU_ANIMATIONS | AFX_CUSTOMIZE_NOHELP),  
    CList <CRuntimeClass*, CRuntimeClass*>* p listCustomPages = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndParentFrame`  
 親のフレームへのポインター。 このパラメーターは `NULL` にすることはできません。  
  
 [入力] `bAutoSetFromMenus`  
 すべてのメニューからメニュー コマンドをコマンドの一覧に追加するかどうかを指定するブール値、**コマンド**ページです。 このパラメーターは場合`TRUE`、メニュー コマンドが追加されます。 それ以外の場合、メニュー コマンドは追加されません。  
  
 [入力] `uiFlags`  
 ダイアログ ボックスの動作に影響するフラグの組み合わせ。 このパラメーターには、次の値の&1; つ以上を指定できます。  
  
- `AFX_CUSTOMIZE_MENU_SHADOWS`  
  
- `AFX_CUSTOMIZE_TEXT_LABELS`  
  
- `AFX_CUSTOMIZE_MENU_ANIMATIONS`  
  
- `AFX_CUSTOMIZE_NOHELP`  
  
- `AFX_CUSTOMIZE_CONTEXT_HELP`  
  
- `AFX_CUSTOMIZE_NOTOOLS`  
  
- `AFX_CUSTOMIZE_MENUAMPERS`  
  
- `AFX_CUSTOMIZE_NO_LARGE_ICONS`  
  
 [入力] `plistCustomPages`  
 リストへのポインター`CRuntimeClass`追加のカスタム ページを指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 `plistCustomPages`パラメーターの一覧を参照`CRuntimeClass`追加のカスタム ページを指定するオブジェクト。 コンス トラクターを使用して、ダイアログ ボックスに複数のページを追加、 [CRuntimeClass::CreateObject](../../mfc/reference/cruntimeclass-structure.md#createobject)メソッドです。 CustomPages のサンプルをより多くのページに追加する例を参照してください、**カスタマイズ** ダイアログ ボックス。  
  
 渡すことができる値の詳細については、`uiFlags`パラメーターを参照してください[CMFCToolBarsCustomizeDialog::GetFlags](#getflags)します。  
  
### <a name="example"></a>例  
 次の例のオブジェクトを構築する方法、`CMFCToolBarsCustomizeDialog`クラスです。 このコード スニペットの一部である、[カスタム ページ サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_CustomPages&#3;](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_4.cpp)]  
  
##  <a name="a-namecreatea--cmfctoolbarscustomizedialogcreate"></a><a name="create"></a>CMFCToolBarsCustomizeDialog::Create  
 表示、**カスタマイズ** ダイアログ ボックス。  
  
```  
virtual BOOL Create();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`カスタマイズのプロパティ シートが正常に作成された場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 呼び出す、`Create`メソッド、クラスを完全に初期化した後でのみです。  
  
##  <a name="a-nameenableuserdefinedtoolbarsa--cmfctoolbarscustomizedialogenableuserdefinedtoolbars"></a><a name="enableuserdefinedtoolbars"></a>CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars  
 有効またはを使用して新しいツールバーの作成を無効にします**カスタマイズ** ダイアログ ボックス。  
  
```  
void EnableUserDefinedToolbars(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE`ユーザー定義のツールバーを有効にするには`FALSE`ツールバーを無効にします。  
  
### <a name="remarks"></a>コメント  
 場合`bEnable`は`TRUE`、**新規**、**の名前を変更**と**削除**にボタンが表示される、**ツールバー**ページです。  
  
 既定では、または`bEnable`は`FALSE`、これらのボタンは表示されず、ユーザーは、新しいツールバーを定義できません。  
  
##  <a name="a-namefillallcommandslista--cmfctoolbarscustomizedialogfillallcommandslist"></a><a name="fillallcommandslist"></a>CMFCToolBarsCustomizeDialog::FillAllCommandsList  
 指定された設定`CListBox`なコマンドでオブジェクト、**すべてのコマンド**カテゴリ。  
  
```  
virtual void FillAllCommandsList(CListBox& wndListOfCommands) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `wndListOfCommands`  
 参照、`CListBox`が設定されるオブジェクト。  
  
### <a name="remarks"></a>コメント  
 **コマンドはすべて**カテゴリには、すべてのカテゴリのコマンドが含まれています。 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton)メソッドに提供されているボタンに関連付けられているコマンドが追加、**コマンドはすべて**のカテゴリ。  
  
 このメソッドが用意されている内容をクリア`CListBox`なコマンドで設定する前にオブジェクト、**コマンドはすべて**カテゴリ。  
  
 `CMFCMousePropertyPage`クラスでは、このメソッドを使用して、ダブルクリック イベントのリスト ボックスに入力します。  
  
##  <a name="a-namefillcategoriescomboboxa--cmfctoolbarscustomizedialogfillcategoriescombobox"></a><a name="fillcategoriescombobox"></a>CMFCToolBarsCustomizeDialog::FillCategoriesComboBox  
 指定された設定`CComboBox`の各コマンドのカテゴリの名前を持つオブジェクト、**カスタマイズ** ダイアログ ボックス。  
  
```  
void FillCategoriesComboBox(
    CComboBox& wndCategory,  
    BOOL bAddEmpty = TRUE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `wndCategory`  
 参照、`CComboBox`が設定されるオブジェクト。  
  
 [入力] `bAddEmpty`  
 コマンドがないコンボ ボックスにカテゴリを追加するかどうかを指定するブール値。 このパラメーターは場合`TRUE`、空のカテゴリは、コンボ ボックスに追加します。 それ以外の場合、空のカテゴリは追加されません。  
  
### <a name="remarks"></a>コメント  
 ように、このメソッドは、 [CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox)メソッドでこのメソッドが動作する点を除いて、`CComboBox`オブジェクトです。  
  
 このメソッドの内容を消去していない、`CComboBox`値を設定する前にオブジェクトです。 保証される、**コマンドはすべて**カテゴリは、コンボ ボックス内の最後の項目。  
  
 新しいコマンドのカテゴリを追加するにを使用して、 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton)メソッドです。 既存のカテゴリの名前を変更するにを使用して、 [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory)メソッドです。  
  
 `CMFCToolBarsKeyboardPropertyPage`と`CMFCKeyMapDialog`クラスでは、このメソッドを使用して、キーボード マップを分類します。  
  
##  <a name="a-namefillcategorieslistboxa--cmfctoolbarscustomizedialogfillcategorieslistbox"></a><a name="fillcategorieslistbox"></a>CMFCToolBarsCustomizeDialog::FillCategoriesListBox  
 指定された設定`CListBox`の各コマンドのカテゴリの名前を持つオブジェクト、**カスタマイズ** ダイアログ ボックス。  
  
```  
void FillCategoriesListBox(
    CListBox& wndCategory,  
    BOOL bAddEmpty = TRUE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `wndCategory`  
 参照、`CListBox`が設定されるオブジェクト。  
  
 [入力] `bAddEmpty`  
 コマンドがないリスト ボックスにカテゴリを追加するかどうかを指定するブール値。 このパラメーターは場合`TRUE`、空のカテゴリは、リスト ボックスに追加します。 それ以外の場合、空のカテゴリは追加されません。  
  
### <a name="remarks"></a>コメント  
 ように、このメソッドは、 [CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox)メソッドでこのメソッドが動作する点を除いて、`CListBox`オブジェクトです。  
  
 このメソッドの内容を消去していない、`CListBox`値を設定する前にオブジェクトです。 保証される、**コマンドはすべて**カテゴリは、リスト ボックスの最後の項目。  
  
 新しいコマンドのカテゴリを追加するにを使用して、 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton)メソッドです。 既存のカテゴリの名前を変更するにを使用して、 [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory)メソッドです。  
  
 `CMFCToolBarsCommandsPropertyPage`クラスでは、このメソッドを使用して、各コマンドのカテゴリに関連付けられているコマンドの一覧を表示します。  
  
##  <a name="a-namegetcommandnamea--cmfctoolbarscustomizedialoggetcommandname"></a><a name="getcommandname"></a>CMFCToolBarsCustomizeDialog::GetCommandName  
 指定されたコマンド ID に関連付けられている名前を取得します。  
  
```  
LPCTSTR GetCommandName(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmd`  
 取得するコマンドの ID です。  
  
### <a name="return-value"></a>戻り値  
 指定されたコマンド ID に関連付けられている名前または`NULL`コマンドが存在しない場合。  
  
##  <a name="a-namegetcountincategorya--cmfctoolbarscustomizedialoggetcountincategory"></a><a name="getcountincategory"></a>CMFCToolBarsCustomizeDialog::GetCountInCategory  
 指定したテキスト ラベルを持つ指定されたリスト内の項目の数を取得します。  
  
```  
int GetCountInCategory(
    LPCTSTR lpszItemName,  
    const CObList& lstCommands) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszItemName`  
 一致するようにテキスト ラベル。  
  
 [入力] `lstCommands`  
 含むリストへの参照を`CMFCToolBarButton`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 提供されている項目の数の一覧をテキスト ラベル equals`lpszItemName`します。  
  
### <a name="remarks"></a>コメント  
 指定されたオブジェクトの一覧内の各要素は、型でなければなりません`CMFCToolBarButton`します。 このメソッドは比較`lpszItemName`で、 [CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext)データ メンバーです。  
  
##  <a name="a-namegetflagsa--cmfctoolbarscustomizedialoggetflags"></a><a name="getflags"></a>CMFCToolBarsCustomizeDialog::GetFlags  
 ダイアログ ボックスの動作に影響するフラグのセットを取得します。  
  
```  
UINT GetFlags() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスの動作に影響するフラグのセットです。  
  
### <a name="remarks"></a>コメント  
 このメソッドの値を取得、`uiFlags`コンス トラクターに渡されるパラメーター。 戻り値は、次の値の&1; つ以上になります。  
  
 `AFX_CUSTOMIZE_MENU_SHADOWS`  
 メニューの シャドウ表示形式を指定できます。  
  
 `AFX_CUSTOMIZE_TEXT_LABELS`  
 ツール バー ボタンのイメージの下にテキスト ラベルを表示するかどうかを指定できます。  
  
 `AFX_CUSTOMIZE_MENU_ANIMATIONS`  
 メニューのアニメーションのスタイルを指定できます。  
  
 `AFX_CUSTOMIZE_NOHELP`  
 カスタマイズ ダイアログ ボックスから [ヘルプ] ボタンを削除します。  
  
 `AFX_CUSTOMIZE_CONTEXT_HELP`  
 により、 `WS_EX_CONTEXTHELP` visual スタイル。  
  
 `AFX_CUSTOMIZE_NOTOOLS`  
 削除、**ツール**のカスタマイズ ダイアログ ボックスからのページです。 このフラグは、アプリケーションで使用する場合は有効、`CUserToolsManager`クラスです。  
  
 `AFX_CUSTOMIZE_MENUAMPERS`  
 により、アンパサンドを格納する、ボタンのキャプション ( ** & **) 文字です。  
  
 `AFX_CUSTOMIZE_NO_LARGE_ICONS`  
 削除、**大きいアイコン**のカスタマイズ ダイアログ ボックスからオプション。  
  
 詳細については、 `WS_EX_CONTEXTHELP` visual スタイルを参照してください[拡張ウィンドウ スタイル](../../mfc/reference/extended-window-styles.md)します。  
  
##  <a name="a-nameonafterchangetoola--cmfctoolbarscustomizedialogonafterchangetool"></a><a name="onafterchangetool"></a>CMFCToolBarsCustomizeDialog::OnAfterChangeTool  
 発生後すぐにユーザー ツールの変更に応答します。  
  
```  
virtual void OnAfterChangeTool(CUserTool* pSelTool);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力] `pSelTool`  
 変更されているユーザー ツールのオブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ユーザー定義のツールのプロパティを変更するときに、framework によって呼び出されます。 既定の実装では、何も行われません。 このメソッドから派生したクラスでオーバーライド`CMFCToolBarsCustomizeDialog`ユーザー ツールへの変更が発生した後の処理を実行します。  
  
##  <a name="a-nameonassignkeya--cmfctoolbarscustomizedialogonassignkey"></a><a name="onassignkey"></a>CMFCToolBarsCustomizeDialog::OnAssignKey  
 ユーザーが定義には、キーボード ショートカットを検証します。  
  
```  
virtual BOOL OnAssignKey(ACCEL* pAccel);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力] `pAccel`  
 として表現される提案されたキーの割り当てへのポインター、 [ACCEL](http://msdn.microsoft.com/library/windows/desktop/ms646340)構造体。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`キーを割り当てることができる場合、または`FALSE`場合は、キーを割り当てることはできません。 既定の実装を常に`TRUE`します。  
  
### <a name="remarks"></a>コメント  
 ユーザーが新しいキーボード ショートカットを割り当てるか、またはユーザーとしてのキーボード ショートカットを検証するには、それを定義するときに、余分な処理を実行する派生クラスでは、このメソッドをオーバーライドします。 ショートカットが割り当てられていることを防ぐために返す`FALSE`します。 またメッセージ ボックスを表示するか、それ以外の場合、ショートカット キーが拒否された理由のためのユーザーに通知してください。  
  
##  <a name="a-nameonbeforechangetoola--cmfctoolbarscustomizedialogonbeforechangetool"></a><a name="onbeforechangetool"></a>CMFCToolBarsCustomizeDialog::OnBeforeChangeTool  
 処理を実行しますカスタム ユーザー ツールに変更されたときに、ユーザーが変更を適用しようとしています。  
  
```  
virtual void OnBeforeChangeTool(CUserTool* pSelTool);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力] `pSelTool`  
 置き換えられるユーザー ツールのオブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 ユーザー定義のツールのプロパティを変更する場合、このメソッドはフレームワークによって呼び出されます。 既定の実装では、何も行われません。 オーバーライド、`OnBeforeChangeTool`から派生したクラスのメソッドに`CMFCToolBarsCustomizeDialog`リソースを解放するなど、ユーザー ツールへの変更が発生する前に、処理を実行する場合を`pSelTool`を使用します。  
  
##  <a name="a-nameonedittoolbarmenuimagea--cmfctoolbarscustomizedialogonedittoolbarmenuimage"></a><a name="onedittoolbarmenuimage"></a>CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage  
 イメージ エディターを起動し、ユーザーがツール バー ボタンやメニュー項目のアイコンをカスタマイズすることができます。  
  
```  
virtual BOOL OnEditToolbarMenuImage(
    CWnd* pWndParent,  
    CBitmap& bitmap,  
    int nBitsPerPixel);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndParent`  
 親ウィンドウへのポインター。  
  
 [入力] `bitmap`  
 編集しようとするビットマップ オブジェクトへの参照。  
  
 [入力] `nBitsPerPixel`  
 ビットマップのビット/ピクセルの色の解像度。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`変更がコミットされている場合それ以外の場合`FALSE`します。 既定の実装は、ダイアログ ボックスを表示しを返します`TRUE`、ユーザーがクリックした場合**ok**、または`FALSE`場合は、ユーザーがクリックした**キャンセル**または**閉じる** ボタンをクリックします。  
  
### <a name="remarks"></a>コメント  
 ユーザー イメージ エディターの実行時に、このメソッドは、フレームワークによって呼び出されます。 既定の実装で、表示[[CMFCImageEditorDialog クラス](../../mfc/reference/cmfcimageeditordialog-class.md)] ダイアログ ボックス。 オーバーライド`OnEditToolbarMenuImage`カスタム イメージ エディターを使用して派生クラスでします。  
  
##  <a name="a-nameoninitdialoga--cmfctoolbarscustomizedialogoninitdialog"></a><a name="oninitdialog"></a>CMFCToolBarsCustomizeDialog::OnInitDialog  
 プロパティ シートの初期化処理を強化するよりも優先されます。  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>戻り値  
 呼び出しの結果、 [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog)メソッドです。  
  
### <a name="remarks"></a>コメント  
 このメソッドが基本クラスの実装を拡張[CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog)、表示することによって、**閉じる**ボタン、ダイアログ ボックスが現在の画面サイズに収まることを確認することによって、移動することで、**ヘルプ** ダイアログ ボックスの左下隅にボタンをクリックします。  
  
##  <a name="a-nameoninittoolspagea--cmfctoolbarscustomizedialogoninittoolspage"></a><a name="oninittoolspage"></a>CMFCToolBarsCustomizeDialog::OnInitToolsPage  
 Framework から通知を処理する、**ツール**ページが初期化される直前にします。  
  
```  
virtual void OnInitToolsPage();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装では、何も行われません。 この通知を処理する派生クラスでは、このメソッドをオーバーライドします。  
  
##  <a name="a-namepostncdestroya--cmfctoolbarscustomizedialogpostncdestroy"></a><a name="postncdestroy"></a>CMFCToolBarsCustomizeDialog::PostNcDestroy  
 ウィンドウが破棄された後に、フレームワークによって呼び出されます。  
  
```  
virtual void PostNcDestroy();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドが基本クラスの実装を拡張`CPropertySheet::PostNcDestroy`、以前のモードにアプリケーションを復元しています。  
  
 [CMFCToolBarsCustomizeDialog::Create](#create)メソッドは、カスタマイズのタスクにユーザーを制限する特殊なモードでアプリケーションを配置します。  
  
##  <a name="a-nameremovebuttona--cmfctoolbarscustomizedialogremovebutton"></a><a name="removebutton"></a>CMFCToolBarsCustomizeDialog::RemoveButton  
 指定したカテゴリまたはすべてのカテゴリは、指定されたコマンド ID を持つボタンを削除します。  
  
```  
int RemoveButton(
    UINT uiCategoryId,  
    UINT uiCmdId);

int RemoveButton(
    LPCTSTR lpszCategory,  
    UINT uiCmdId);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCategoryId`  
 ボタンを削除するカテゴリの ID を指定します。  
  
 [入力] `uiCmdId`  
 ボタンのコマンド ID を指定します。  
  
 [入力] `lpszCategory`  
 ボタンを削除するカテゴリの名前を指定します。  
  
### <a name="return-value"></a>戻り値  
 削除 ボタンをクリックし、または指定されたコマンド ID が指定したカテゴリで見つからなかった場合は-1、0 から始まるインデックス。 場合`uiCategoryId`-1 で、戻り値は 0 です。  
  
### <a name="remarks"></a>コメント  
 ボタンすべてのカテゴリからを削除するには、このメソッドのセットの最初のオーバー ロードを呼び出す`uiCategoryId`を-1 にします。  
  
##  <a name="a-namerenamecategorya--cmfctoolbarscustomizedialogrenamecategory"></a><a name="renamecategory"></a>CMFCToolBarsCustomizeDialog::RenameCategory  
 カテゴリのリスト ボックスでカテゴリの名前を変更、**コマンド**ページです。  
  
```  
BOOL RenameCategory(
    LPCTSTR lpszCategoryOld,  
    LPCTSTR lpszCategoryNew);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszCategoryOld`  
 変更するカテゴリ名。  
  
 [入力] `lpszCategoryNew`  
 新しいカテゴリの名前。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メソッドが成功した場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 カテゴリ名は一意である必要があります。  
  
##  <a name="a-namereplacebuttona--cmfctoolbarscustomizedialogreplacebutton"></a><a name="replacebutton"></a>CMFCToolBarsCustomizeDialog::ReplaceButton  
 コマンドのリスト ボックスにツール バー ボタンが置き換えられます、**コマンド**ページです。  
  
```  
void ReplaceButton(
    UINT uiCmd,  
    const CMFCToolBarButton& button);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmd`  
 置き換えられる ボタンのコマンドを指定します。  
  
 [入力] `button`  
 A`const`古いボタンを置き換えるツール バー ボタンのオブジェクトへの参照。  
  
### <a name="remarks"></a>コメント  
 [CMFCToolBarsCustomizeDialog::AddMenu](#addmenu)、 [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)、または[CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar)するコマンドを追加、**コマンド**ページで、コマンドがの形式である、 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)オブジェクト (または[CMFCToolBarMenuButton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)によって追加されたサブメニューを持つメニュー項目のオブジェクトを`AddMenuCommands`)。 フレームワークでは、コマンドを自動的に追加する&3; つのメソッドも呼び出します。 代わりに派生型で表現するためのコマンドを実行する場合に、呼び出す`ReplaceButton`派生型のボタンを渡します。  
  
### <a name="example"></a>例  
 次の例では、使用して、`ReplaceButton`メソッドで、`CMFCToolBarsCustomizeDialog`クラスです。 このコード スニペットの一部である、 [Visual Studio のデモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&34;](../../mfc/codesnippet/cpp/cmfctoolbarscustomizedialog-class_5.cpp)]  
  
##  <a name="a-namesetusercategorya--cmfctoolbarscustomizedialogsetusercategory"></a><a name="setusercategory"></a>CMFCToolBarsCustomizeDialog::SetUserCategory  
 カテゴリの一覧でカテゴリを指定、**コマンド**ページは、ユーザーのカテゴリ。 呼び出す前に、この関数を呼び出す必要があります[CMFCToolBarsCustomizeDialog::Create](#create)します。  
  
```  
BOOL SetUserCategory(LPCTSTR lpszCategory);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszCategory`  
 カテゴリの名前。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メソッドが成功した場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 現在、ユーザーのカテゴリの設定は、フレームワークによって使用されていません。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CPropertySheet クラス](../../mfc/reference/cpropertysheet-class.md)

