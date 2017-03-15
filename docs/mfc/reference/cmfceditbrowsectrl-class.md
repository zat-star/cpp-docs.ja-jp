---
title: "CMFCEditBrowseCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCEditBrowseCtrl
dev_langs:
- C++
helpviewer_keywords:
- CMFCEditBrowseCtrl::PreTranslateMessage method
- CMFCEditBrowseCtrl constructor
- CMFCEditBrowseCtrl class
ms.assetid: 69cfd886-3d35-4bee-8901-7c88fcf9520f
caps.latest.revision: 33
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
ms.openlocfilehash: 5c5650da677a442628049c9ef4b41c2142cfb2c2
ms.lasthandoff: 02/24/2017

---
# <a name="cmfceditbrowsectrl-class"></a>CMFCEditBrowseCtrl クラス
`CMFCEditBrowseCtrl`クラスは、[参照] ボタンを含む (オプション) を編集可能なテキスト ボックスにある編集参照コントロールをサポートしています。 ユーザーが参照ボタンをクリックすると、このコントロールはカスタム動作を実行するか、ファイル参照またはフォルダー参照を含む標準ダイアログ ボックスを表示します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCEditBrowseCtrl : public CEdit  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCEditBrowseCtrl::CMFCEditBrowseCtrl`|既定のコンストラクター|  
|`CMFCEditBrowseCtrl::~CMFCEditBrowseCtrl`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton)|有効または無効 (非表示にします)、[参照] ボタンをクリックします。|  
|[CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton)|[参照] ボタンを有効し、参照機能付きコントロールを*ファイル参照*モードです。|  
|[CMFCEditBrowseCtrl::EnableFolderBrowseButton](#enablefolderbrowsebutton)|[参照] ボタンを有効し、参照機能付きコントロールを*フォルダー参照*モードです。|  
|[CMFCEditBrowseCtrl::GetMode](#getmode)|現在のブラウズ モードを返します。|  
|[CMFCEditBrowseCtrl::OnAfterUpdate](#onafterupdate)|参照機能付きコントロールを参照アクションの結果で更新した後に、フレームワークによって呼び出されます。|  
|[CMFCEditBrowseCtrl::OnBrowse](#onbrowse)|[参照] ボタンをクリックした後に、フレームワークによって呼び出されます。|  
|[CMFCEditBrowseCtrl::OnChangeLayout](#onchangelayout)|現在の参照機能付きコントロールを再描画します。|  
|[CMFCEditBrowseCtrl::OnDrawBrowseButton](#ondrawbrowsebutton)|[参照] ボタンを描画するためにフレームワークによって呼び出されます。|  
|[CMFCEditBrowseCtrl::OnIllegalFileName](#onillegalfilename)|無効なファイル名は、エディット コントロールに入力されたときに、フレームワークによって呼び出されます。|  
|`CMFCEditBrowseCtrl::PreTranslateMessage`|ウィンドウのメッセージの変換にディスパッチされる前に、 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 関数です。 構文と詳細については、次を参照してください。 [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)します。|  
|[CMFCEditBrowseCtrl::SetBrowseButtonImage](#setbrowsebuttonimage)|[参照] ボタンのカスタム イメージを設定します。|  
  
## <a name="remarks"></a>コメント  
 参照機能付きコントロールを使用すると、ファイルまたはフォルダー名を選択します。 必要に応じて、コントロールを使用して、ダイアログ ボックスを表示するようにカスタム アクションを実行します。 表示したり、[参照] ボタンは表示されませんし、ボタンにカスタム ラベルやイメージを適用することができます。  
  
 *ブラウズ モード*[参照] ボタンを表示するかどうかと、ボタンがクリックされたときに発生する動作の参照機能付きコントロールを決定します。 詳細については、次を参照してください。、 [GetMode](#getmode)メソッドです。  
  
 `CMFCEditBrowseCtrl`クラスは、次のモードをサポートします。  
  
 `custom mode`  
 [参照] ボタンをクリックして、カスタム アクションが実行されます。 たとえば、アプリケーション固有のダイアログ ボックスを表示することができます。  
  
 `file mode`  
 ユーザーが 参照 ボタンをクリックすると、標準的なファイルの選択 ダイアログ ボックスが表示されます。  
  
 `folder mode`  
 ユーザーが 参照 ボタンをクリックすると、標準的なフォルダーの選択 ダイアログ ボックスが表示されます。  
  
## <a name="how-to-specify-an-edit-browse-control"></a>方法: 参照機能付きコントロールを指定します。  
 アプリケーションで参照機能付きコントロールを組み込むように、次の手順を実行します。  
  
1.  カスタムのブラウズ モードを実装する場合は、派生クラスから、`CMFCEditBrowseCtrl`クラスをその後、オーバーライド、 [CMFCEditBrowseCtrl::OnBrowse](#onbrowse)メソッドです。 オーバーライド メソッドでカスタム参照アクションを実行し、結果と参照機能付きコントロールを更新します。  
  
2.  いずれかを埋め込む、`CMFCEditBrowseCtrl`オブジェクトまたは親ウィンドウのオブジェクトには、派生編集参照コントロール オブジェクトです。  
  
3.  使用する場合、**クラス ウィザード** ダイアログ ボックスを作成するには、エディット コントロールを追加 ( `CEdit`) ダイアログ ボックスのフォームにします。 また、ヘッダー ファイルでコントロールにアクセスする変数を追加します。 変数の型を変更すると、ヘッダー ファイルで`CEdit`に`CMFCEditBrowseCtrl`します。 参照機能付きコントロールが自動的に作成されます。 使用しない場合、**クラス ウィザード**、追加、`CMFCEditBrowseCtrl`変数ヘッダー ファイルと、呼び出しをその`Create`メソッドです。  
  
4.  参照機能付きコントロールをダイアログ ボックスに追加する場合に使用して、 **ClassWizard**データ交換を設定するツールです。  
  
5.  呼び出す、 [EnableFolderBrowseButton](#enablefolderbrowsebutton)、 [EnableFileBrowseButton](#enablefilebrowsebutton)、または[EnableBrowseButton](#enablebrowsebutton)ブラウズ モードを設定し、[参照] ボタンを表示します。 呼び出す、 [GetMode](#getmode)現在ブラウズ モードを取得します。  
  
6.  で [参照] ボタンをカスタム イメージを指定するを呼び出す、 [SetBrowseButtonImage](#setbrowsebuttonimage)メソッドやオーバーライド、 [OnDrawBrowseButton](#ondrawbrowsebutton)メソッドです。  
  
7.  参照機能付きコントロールから、[参照] ボタンを削除するには、呼び出し、 [EnableBrowseButton](#enablebrowsebutton)メソッドを`bEnable`パラメーターを設定する`FALSE`です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [CMFCEditBrowseCtrl](../../mfc/reference/cmfceditbrowsectrl-class.md)  
  
## <a name="example"></a>例  
 次の例では、2 つのメソッドを使用して、`CMFCEditBrowseCtrl`クラス:`EnableFolderBrowseButton`と`EnableFileBrowseButton`です。 この例は、[新しいコントロールのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_NewControls&6;](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#7;](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_2.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxeditbrowsectrl.h  
  
##  <a name="a-nameenablebrowsebuttona--cmfceditbrowsectrlenablebrowsebutton"></a><a name="enablebrowsebutton"></a>CMFCEditBrowseCtrl::EnableBrowseButton  
 表示または現在の参照機能付きコントロールの [参照] ボタンは表示されません。  
  
```  
void EnableBrowseButton(
    BOOL bEnable=TRUE,  
    LPCTSTR szLabel=_T("..."));
```  
  
### <a name="parameters"></a>パラメーター  
 `bEnable`  
 `TRUE`[参照] ボタンを表示するには`FALSE` [参照] ボタンを表示しないようにします。 既定値は `TRUE` です。  
  
 `szLabel`  
 [参照] ボタンに表示されるラベルです。 既定値は" **.**".  
  
### <a name="remarks"></a>コメント  
 場合、`bEnable`パラメーターは`TRUE`、[参照] ボタンがクリックされたときに実行するカスタム アクションを実装します。 カスタム動作を実装するのには、派生クラスを`CMFCEditBrowseCtrl`クラスをオーバーライドし、その[OnBrowse](#onbrowse)メソッドです。  
  
 場合、`bEnable`パラメーターは`TRUE`、コントロールのブラウズ モードは`BrowseMode_Default`しない場合は、ブラウズ モードは`BrowseMode_None`です。 ブラウズ モードの詳細については、次を参照してください。、 [GetMode](#getmode)メソッドです。  
  
##  <a name="a-nameenablefilebrowsebuttona--cmfceditbrowsectrlenablefilebrowsebutton"></a><a name="enablefilebrowsebutton"></a>CMFCEditBrowseCtrl::EnableFileBrowseButton  
 現在の参照機能付きコントロールで [参照] ボタンを表示し、コントロールを*ファイル参照*モードです。  
  
```  
void EnableFileBrowseButton(
    LPCTSTR lpszDefExt=NULL,  
    LPCTSTR lpszFilter=NULL,  
    DWORD dwFlags = OFN_HIDEREADONLY | OFN_OVERWRITEPROMPT);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszDefExt`  
 [ファイルの選択] ダイアログ ボックスで使用する既定のファイル名拡張子を指定します。 既定値は `NULL` です。  
  
 `lpszFilter`  
 [ファイルの選択] ダイアログ ボックスで使用する既定のフィルター文字列を指定します。 既定値は `NULL` です。  
  
 `dwFlags`  
 ダイアログ ボックスのフラグ。 既定値は OFN_HIDEREADONLY と OFN_OVERWRITEPROMPT のビットごとの組み合わせ (OR) です。  
  
### <a name="remarks"></a>コメント  
 参照機能付きコントロールがファイル参照モードのときにユーザーが [参照] ボタンをクリックすると、コントロールに標準的なファイル選択のダイアログ ボックスが表示されます。  
  
 使用可能なフラグの一覧については、次を参照してください。 [OPENFILENAME 構造](https://msdn.microsoft.com/library/ms646839.aspx)します。  
  
##  <a name="a-nameenablefolderbrowsebuttona--cmfceditbrowsectrlenablefolderbrowsebutton"></a><a name="enablefolderbrowsebutton"></a>CMFCEditBrowseCtrl::EnableFolderBrowseButton  
 現在の参照機能付きコントロールで [参照] ボタンを表示し、コントロールを*フォルダー参照*モードです。  
  
```  
void EnableFolderBrowseButton();
```  
  
### <a name="remarks"></a>コメント  
 参照機能付きコントロールは、フォルダーのブラウズ モードでは、ユーザーが 参照 ボタンをクリックして、ときに、コントロールは標準的なフォルダーの選択 ダイアログ ボックスを表示します。  
  
##  <a name="a-namegetmodea--cmfceditbrowsectrlgetmode"></a><a name="getmode"></a>CMFCEditBrowseCtrl::GetMode  
 現在の参照機能付きコントロールのブラウズ モードを取得します。  
  
```  
CMFCEditBrowseCtrl::BrowseMode GetMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 編集の現在のモードを指定する列挙値の&1; つは、コントロールを参照します。 ブラウズ モードは、フレームワークは、参照ボタンを表示するかどうかと、ユーザーがそのボタンをクリックしたときに発生する動作を決定します。  
  
 次の表は、可能性のある戻り値の一覧です。  
  
|値|説明|  
|-----------|-----------------|  
|`BrowseMode_Default`|`custom mode`。 プログラマが定義したアクションが実行されます。|  
|`BrowseMode_File`|`file mode`。 標準的なファイル ブラウザー ダイアログ ボックスが表示されます。|  
|`BrowseMode_Folder`|`folder mode`。 標準フォルダのブラウザーのダイアログ ボックスが表示されます。|  
|`BrowseMode_None`|[参照] ボタンは表示されません。|  
  
### <a name="remarks"></a>コメント  
 既定では、`CMFCEditBrowseCtrl`オブジェクトが初期化`BrowseMode_None`モードです。 ブラウズ モードでの変更、 [CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton)、 [CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton)、および[CMFCEditBrowseCtrl::EnableFolderBrowseButton](#enablefolderbrowsebutton)メソッドです。  
  
##  <a name="a-nameonafterupdatea--cmfceditbrowsectrlonafterupdate"></a><a name="onafterupdate"></a>CMFCEditBrowseCtrl::OnAfterUpdate  
 参照機能付きコントロールを参照アクションの結果で更新した後に、フレームワークによって呼び出されます。  
  
```  
virtual void OnAfterUpdate();
```  
  
### <a name="remarks"></a>コメント  
 カスタム アクションを実装する派生クラスでこのメソッドをオーバーライドします。  
  
##  <a name="a-nameonbrowsea--cmfceditbrowsectrlonbrowse"></a><a name="onbrowse"></a>CMFCEditBrowseCtrl::OnBrowse  
 参照機能付きコントロールの [参照] ボタンをクリックした後に、フレームワークによって呼び出されます。  
  
```  
virtual void OnBrowse();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、ユーザーが参照機能付きコントロールの [参照] ボタンをクリックすると、カスタム コードを実行します。 クラスを派生、`CMFCEditBrowseCtrl`クラスさせ、`OnBrowse`メソッドです。 このメソッドでカスタム参照アクションを実装し、必要に応じて参照機能付きコントロールのテキスト ボックスを更新します。 アプリケーションで使用して、 [EnableBrowseButton](#enablebrowsebutton)メソッドに参照機能付きコントロールを配置する*カスタム参照*モードです。  
  
##  <a name="a-nameonchangelayouta--cmfceditbrowsectrlonchangelayout"></a><a name="onchangelayout"></a>CMFCEditBrowseCtrl::OnChangeLayout  
 現在の参照機能付きコントロールを再描画します。  
  
```  
virtual void OnChangeLayout();
```  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ブラウズ モードの参照機能付きコントロール、変更されるときに、このメソッドを呼び出します。 詳細については、次を参照してください。 [CMFCEditBrowseCtrl::GetMode](#getmode)します。  
  
##  <a name="a-nameondrawbrowsebuttona--cmfceditbrowsectrlondrawbrowsebutton"></a><a name="ondrawbrowsebutton"></a>CMFCEditBrowseCtrl::OnDrawBrowseButton  
 参照機能付きコントロールに [参照] ボタンを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDrawBrowseButton(
    CDC* pDC,  
    CRect rect,  
    BOOL bIsButtonPressed,  
    BOOL bIsButtonHot);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 デバイス コンテキストへのポインター。  
  
 `Rect`  
 [参照] ボタンの外接する四角形。  
  
 `bIsButtonPressed`  
 `TRUE`場合は、ボタンが押されたとします。それ以外の場合、`FALSE`です。  
  
 `bIsButtonHot`  
 `TRUE`場合は、ボタンが強調表示されます。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 [参照] ボタンの外観をカスタマイズする派生クラスでオーバーライドします。  
  
##  <a name="a-namesetbrowsebuttonimagea--cmfceditbrowsectrlsetbrowsebuttonimage"></a><a name="setbrowsebuttonimage"></a>CMFCEditBrowseCtrl::SetBrowseButtonImage  
 参照機能付きコントロールの [参照] ボタンをカスタム イメージを設定します。  
  
```  
void SetBrowseButtonImage(
    HICON hIcon,  
    BOOL bAutoDestroy= TRUE);

 
void SetBrowseButtonImage(
    HBITMAP hBitmap,  
    BOOL bAutoDestroy= TRUE);  
  
void SetBrowseButtonImage(UINT uiBmpResId);
```  
  
### <a name="parameters"></a>パラメーター  
 `hIcon`  
 アイコンのハンドル。  
  
 `hBitmap`  
 ビットマップのハンドル。  
  
 `uiBmpResId`  
 ビットマップのリソース ID です。  
  
 `bAutoDestroy`  
 `TRUE`このメソッドを終了時に、指定されたアイコンまたはビットマップを削除するにはそれ以外の場合、`FALSE`です。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、[参照] ボタンをカスタム イメージを適用できます。 参照機能付きコントロールが、ときに既定では、フレームワークが標準のイメージを取得*ファイル参照*または*フォルダー参照*モードです。  
  
##  <a name="a-nameonillegalfilenamea--cmfceditbrowsectrlonillegalfilename"></a><a name="onillegalfilename"></a>CMFCEditBrowseCtrl::OnIllegalFileName  
 無効なファイル名は、エディット コントロールに入力されたときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnIllegalFileName(CString& strFileName);
```  
  
### <a name="parameters"></a>パラメーター  
 `strFileName`  
 無効なファイル名を指定します。  
  
### <a name="return-value"></a>戻り値  
 返す必要があります`FALSE`場合は、ファイル ダイアログをさらにこのファイル名を渡すことはできません。 この場合、エディット コントロールにフォーカスを戻す設定し、ユーザーが編集を続行する必要があります。 既定の実装に関する無効なファイル名をユーザーに示すメッセージ ボックスを表示し、返します`FALSE`します。 このメソッドをオーバーライドして、ファイル名を修正および返す`TRUE`さらに処理します。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)

