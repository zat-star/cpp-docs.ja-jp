---
title: "クラスの関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COlePropertyPage
- AFXCTL/COlePropertyPage
- AFXCTL/COlePropertyPage::COlePropertyPage
- AFXCTL/COlePropertyPage::GetControlStatus
- AFXCTL/COlePropertyPage::GetObjectArray
- AFXCTL/COlePropertyPage::GetPageSite
- AFXCTL/COlePropertyPage::IgnoreApply
- AFXCTL/COlePropertyPage::IsModified
- AFXCTL/COlePropertyPage::OnEditProperty
- AFXCTL/COlePropertyPage::OnHelp
- AFXCTL/COlePropertyPage::OnInitDialog
- AFXCTL/COlePropertyPage::OnObjectsChanged
- AFXCTL/COlePropertyPage::OnSetPageSite
- AFXCTL/COlePropertyPage::SetControlStatus
- AFXCTL/COlePropertyPage::SetDialogResource
- AFXCTL/COlePropertyPage::SetHelpInfo
- AFXCTL/COlePropertyPage::SetModifiedFlag
- AFXCTL/COlePropertyPage::SetPageName
dev_langs:
- C++
helpviewer_keywords:
- OLE property pages
- custom controls [MFC], properties
- COlePropertyPage class
- properties [C++], displaying
- displaying properties
- property pages, OLE
ms.assetid: e9972872-8e6b-4550-905e-d36a274d64dc
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 20d70cc25305fc5d17860314d9cfbe927df65c70
ms.lasthandoff: 02/24/2017

---
# <a name="colepropertypage-class"></a>関数のクラス
ダイアログ ボックスのようなグラフィカルなインターフェイスでカスタム コントロールのプロパティを表示します。  
  
## <a name="syntax"></a>構文  
  
```  
class AFX_NOVTABLE COlePropertyPage : public CDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COlePropertyPage::COlePropertyPage](#colepropertypage)|`COlePropertyPage` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COlePropertyPage::GetControlStatus](#getcontrolstatus)|ユーザーがコントロールの値を変更するかどうかを示します。|  
|[COlePropertyPage::GetObjectArray](#getobjectarray)|プロパティ ページで編集されるオブジェクトの配列を返します。|  
|[COlePropertyPage::GetPageSite](#getpagesite)|プロパティ ページへのポインターを返します`IPropertyPageSite`インターフェイスです。|  
|[COlePropertyPage::IgnoreApply](#ignoreapply)|どのコントロールに適用 ボタンが有効にしないことを決定します。|  
|[COlePropertyPage::IsModified](#ismodified)|ユーザーが、プロパティ ページを変更するかどうかを示します。|  
|[COlePropertyPage::OnEditProperty](#oneditproperty)|プロパティを編集するときに、フレームワークによって呼び出されます。|  
|[COlePropertyPage::OnHelp](#onhelp)|ユーザーはヘルプを呼び出したときに、フレームワークによって呼び出されます。|  
|[COlePropertyPage::OnInitDialog](#oninitdialog)|プロパティ ページが初期化されるときに、フレームワークによって呼び出されます。|  
|[COlePropertyPage::OnObjectsChanged](#onobjectschanged)|新しいプロパティを持つ別の OLE コントロールがクリックされたときに、フレームワークによって呼び出されます。|  
|[COlePropertyPage::OnSetPageSite](#onsetpagesite)|プロパティのフレームは、ページのサイトを提供するときに、フレームワークによって呼び出されます。|  
|[COlePropertyPage::SetControlStatus](#setcontrolstatus)|ユーザーがコントロールの値を変更したかどうかを示すフラグを設定します。|  
|[COlePropertyPage::SetDialogResource](#setdialogresource)|プロパティ ページのダイアログ リソースを設定します。|  
|[COlePropertyPage::SetHelpInfo](#sethelpinfo)|プロパティ ページの簡単なヘルプ テキスト、そのヘルプ ファイルとそのヘルプ コンテキストの名前を設定します。|  
|[COlePropertyPage::SetModifiedFlag](#setmodifiedflag)|ユーザーが、プロパティ ページを変更したかどうかを示すフラグを設定します。|  
|[COlePropertyPage::SetPageName](#setpagename)|プロパティ ページの名前 (キャプション) を設定します。|  
  
## <a name="remarks"></a>コメント  
 たとえば、プロパティ ページには、ユーザーが表示およびコントロールの caption プロパティを変更できるエディット コントロールが含まれます。  
  
 各カスタムまたはストック コントロール プロパティには、コントロールのユーザーが現在のプロパティ値を表示し、必要な場合は、その値を変更できるようにするダイアログ コントロールを設定できます。  
  
 使用する方法について`COlePropertyPage`、記事を参照して[ActiveX コントロール: プロパティ ページ](../../mfc/mfc-activex-controls-property-pages.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `COlePropertyPage`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxctl.h  
  
##  <a name="colepropertypage"></a>COlePropertyPage::COlePropertyPage  
 `COlePropertyPage` オブジェクトを構築します。  
  
```  
COlePropertyPage(
    UINT idDlg,  
    UINT idCaption);
```  
  
### <a name="parameters"></a>パラメーター  
 *idDlg*  
 ダイアログ テンプレートのリソース ID です。  
  
 *idCaption*  
 プロパティ ページのキャプションのリソース ID です。  
  
### <a name="remarks"></a>コメント  
 サブクラスを実装するときに`COlePropertyPage`、サブクラスのコンス トラクターを使用する必要があります、`COlePropertyPage`コンス トラクターでダイアログ テンプレート リソースを識別するために、プロパティ ページが基盤として、キャプションを含む文字列リソースです。  
  
##  <a name="getcontrolstatus"></a>COlePropertyPage::GetControlStatus  
 ユーザーが指定されたリソース ID を持つプロパティ ページのコントロールの値を変更したかどうかを決定します。  
  
```  
BOOL GetControlStatus(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 プロパティ ページのコントロールのリソース ID です。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**変更された以外の場合、コントロール値が表示された場合に**FALSE**します。  
  
##  <a name="getobjectarray"></a>COlePropertyPage::GetObjectArray  
 プロパティ ページで編集されるオブジェクトの配列を返します。  
  
```  
LPDISPATCH* GetObjectArray(ULONG* pnObjects);
```  
  
### <a name="parameters"></a>パラメーター  
 `pnObjects`  
 ページが編集されているオブジェクトの数を受信する、符号なし長整数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 配列を指すポインター`IDispatch`ポインターで、[プロパティ] ページには、各コントロールのプロパティにアクセスするために使用します。 呼び出し元は、これらのインターフェイス ポインターを解放する必要があります。  
  
### <a name="remarks"></a>コメント  
 各プロパティ ページのオブジェクトへのポインターの配列を保持する、`IDispatch`のページが編集されているオブジェクトのインターフェイスです。 この関数を設定、`pnObjects`その配列内の要素の数の引数の配列の最初の要素へのポインターを返します。  
  
##  <a name="getpagesite"></a>COlePropertyPage::GetPageSite  
 プロパティ ページへのポインターを取得`IPropertyPageSite`インターフェイスです。  
  
```  
LPPROPERTYPAGESITE GetPageSite();
```  
  
### <a name="return-value"></a>戻り値  
 プロパティ ページへのポインター`IPropertyPageSite`インターフェイスです。  
  
### <a name="remarks"></a>コメント  
 コントロールとコンテナーは、ユーザーが参照してコントロール プロパティを編集できるように協調動作します。 コントロールは、それぞれが、関連する一連のプロパティを編集するユーザーをできるようにする OLE オブジェクトのプロパティ ページを提供します。 コンテナーは、プロパティ ページを表示するプロパティ フレームを提供します。 プロパティ フレームがサポートしているページのサイトを提供する各ページで、`IPropertyPageSite`インターフェイスです。  
  
##  <a name="ignoreapply"></a>COlePropertyPage::IgnoreApply  
 どのコントロールに適用 ボタンが有効にしないことを決定します。  
  
```  
void IgnoreApply(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 無視されるコントロールの ID です。  
  
### <a name="remarks"></a>コメント  
 プロパティ ページの [適用] ボタンは、ページ コントロールのプロパティの値が変更された場合にのみ有効です。 この関数を使用すると、その値が変わる場合に有効にするのに [適用] ボタンが発生しないコントロールを指定できます。  
  
##  <a name="ismodified"></a>COlePropertyPage::IsModified  
 ユーザーが、プロパティ ページで値を変更したかどうかを決定します。  
  
```  
BOOL IsModified();
```  
  
### <a name="return-value"></a>戻り値  
 **TRUE**プロパティ ページが変更された場合。  
  
##  <a name="oneditproperty"></a>COlePropertyPage::OnEditProperty  
 フレームワークは、特定のプロパティを編集しようとするときに、この関数を呼び出します。  
  
```  
virtual BOOL OnEditProperty(DISPID dispid);
```  
  
### <a name="parameters"></a>パラメーター  
 `dispid`  
 編集されるプロパティの ID をディスパッチします。  
  
### <a name="return-value"></a>戻り値  
 既定の実装**FALSE**します。 この関数のオーバーライドを返す必要があります**TRUE**します。  
  
### <a name="remarks"></a>コメント  
 ページで適切なコントロールにフォーカスを設定するメソッドをオーバーライドすることができます。 既定の実装では nothing を返します**FALSE**します。  
  
##  <a name="onhelp"></a>COlePropertyPage::OnHelp  
 フレームワークは、ユーザーは、オンライン ヘルプを要求すると、この関数を呼び出します。  
  
```  
virtual BOOL OnHelp(LPCTSTR lpszHelpDir);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszHelpDir*  
 プロパティ ページのヘルプ ファイルを含むディレクトリ。  
  
### <a name="return-value"></a>戻り値  
 既定の実装**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 プロパティ ページは、ユーザーがヘルプにアクセスするときに特別な操作を実行する必要がある場合は、それをオーバーライドします。 既定の実装では nothing を返します**FALSE**WinHelp を呼び出すために、フレームワークに指示します。  
  
##  <a name="oninitdialog"></a>COlePropertyPage::OnInitDialog  
 フレームワークは、プロパティ ページのダイアログの初期化時に、この関数を呼び出します。  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>戻り値  
 既定の実装**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 ダイアログの初期化時に、特別な操作が必要な場合は、それをオーバーライドします。 既定の実装`CDialog::OnInitDialog`返します**FALSE**します。  
  
##  <a name="onobjectschanged"></a>COlePropertyPage::OnObjectsChanged  
 新しいプロパティを持つ別の OLE コントロールがクリックされたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnObjectsChanged();
```  
  
### <a name="remarks"></a>コメント  
 OLE コントロールのプロパティを表示する、開発環境で、そのプロパティ ページを表示するモードレス ダイアログ ボックスが使用されます。 別のコントロールが選択されている場合は、新しい一連のプロパティの異なる一連のプロパティ ページを表示する必要があります。 フレームワークでは、変更のプロパティ ページに通知するには、この関数を呼び出します。  
  
 この操作の通知を受信し、特別な操作を実行するには、この関数をオーバーライドします。  
  
##  <a name="onsetpagesite"></a>COlePropertyPage::OnSetPageSite  
 フレームワークは、プロパティのフレームは、プロパティ ページのページのサイトを提供するときに、この関数を呼び出します。  
  
```  
virtual void OnSetPageSite();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装では、ページのキャプションを読み込み、ダイアログ リソースから、ページのサイズを決定しようとします。 プロパティ ページには、特別な操作が必要な場合は、この関数をオーバーライドします。オーバーライドした関数では、基本クラスの実装を呼び出す必要があります。  
  
##  <a name="setcontrolstatus"></a>COlePropertyPage::SetControlStatus  
 プロパティ ページのコントロールの状態を変更します。  
  
```  
BOOL SetControlStatus(
    UINT nID,  
    BOOL bDirty);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 プロパティ ページのコントロールの ID が含まれています。  
  
 `bDirty`  
 プロパティ ページのフィールドが変更されたかどうかを指定します。 設定**TRUE**フィールドが変更された場合**FALSE**変更されていない場合。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**場合、指定したコントロールが設定されているそれ以外の場合は、 **FALSE**します。  
  
### <a name="remarks"></a>コメント  
 プロパティ ページが閉じているか、[適用] ボタンを選択したときにプロパティ ページのコントロールの状態がダーティ場合は、コントロールのプロパティは、適切な値で更新します。  
  
##  <a name="setdialogresource"></a>COlePropertyPage::SetDialogResource  
 プロパティ ページのダイアログ リソースを設定します。  
  
```  
void SetDialogResource(HGLOBAL hDialog);
```  
  
### <a name="parameters"></a>パラメーター  
 *hDialog*  
 プロパティ ページのダイアログ リソースへのハンドルします。  
  
##  <a name="sethelpinfo"></a>COlePropertyPage::SetHelpInfo  
 ツールヒント情報、ヘルプ ファイル名、およびプロパティ ページのヘルプ コンテキストを指定します。  
  
```  
void SetHelpInfo(
    LPCTSTR lpszDocString,  
    LPCTSTR lpszHelpFile = NULL,  
    DWORD dwHelpContext = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszDocString*  
 ステータス バーまたは他の場所に表示する簡単なヘルプ情報を含む文字列。  
  
 `lpszHelpFile`  
 プロパティ ページのヘルプ ファイルの名前です。  
  
 *dwHelpContext*  
 プロパティ ページのヘルプ コンテキスト。  
  
##  <a name="setmodifiedflag"></a>COlePropertyPage::SetModifiedFlag  
 ユーザーが、プロパティ ページを変更するかどうかを示します。  
  
```  
void SetModifiedFlag(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bModified`  
 プロパティ ページの変更フラグの新しい値を指定します。  
  
##  <a name="setpagename"></a>COlePropertyPage::SetPageName  
 通常、プロパティのフレームは、ページのタブに表示されるプロパティ ページの名前を設定します。  
  
```  
void SetPageName(LPCTSTR lpszPageName);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszPageName*  
 プロパティ ページの名前を含む文字列へのポインター。  
  
## <a name="see-also"></a>関連項目  
 [MFC のサンプル CIRC3](../../visual-cpp-samples.md)   
 [MFC サンプル TESTHELP](../../visual-cpp-samples.md)   
 [CDialog クラス](../../mfc/reference/cdialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDialog クラス](../../mfc/reference/cdialog-class.md)

