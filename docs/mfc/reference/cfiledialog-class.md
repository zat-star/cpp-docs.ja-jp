---
title: "CFileDialog クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFileDialog
dev_langs:
- C++
helpviewer_keywords:
- CFileDialog class
- common file dialog boxes
- dialog boxes, common
ms.assetid: fda4fd3c-08b8-4ce0-8e9d-7bab23f8c6c0
caps.latest.revision: 47
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
ms.openlocfilehash: 7cde10ee445a719bce6be4167698bd86c46a18c0
ms.lasthandoff: 02/24/2017

---
# <a name="cfiledialog-class"></a>CFileDialog クラス
ファイルを開くまたは保存する操作に使用される、コモン ダイアログ ボックスをカプセル化します。  
  
## <a name="syntax"></a>構文  
  
```  
class CFileDialog : public CCommonDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CFileDialog::CFileDialog](#cfiledialog)|`CFileDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFileDialog::AddCheckButton](#addcheckbutton)|ダイアログ ボックスに、チェック ボタンを追加します。|  
|[CFileDialog::AddComboBox](#addcombobox)|ダイアログ ボックスに、コンボ ボックスを追加します。|  
|[CFileDialog::AddControlItem](#addcontrolitem)|ダイアログ ボックスのコンテナー コントロールに項目を追加します。|  
|[CFileDialog::AddEditBox](#addeditbox)|ダイアログ ボックスを編集ボックスを追加します。|  
|[CFileDialog::AddMenu](#addmenu)|ダイアログ ボックスにメニューを追加します。|  
|[CFileDialog::AddPlace](#addplace)|オーバーロードされます。 一覧にフォルダーはユーザーが開くか、項目を保存するために使用できる場所を追加します。|  
|[CFileDialog::AddPushButton](#addpushbutton)|ダイアログ ボックスにボタンを追加します。|  
|[CFileDialog::AddRadioButtonList](#addradiobuttonlist)|ダイアログ ボックスにオプション ボタンとも呼ばれます) グループを追加します。|  
|[CFileDialog::AddSeparator](#addseparator)|ダイアログ ボックスに、区切り記号を追加します。|  
|[CFileDialog::AddText](#addtext)|ダイアログ ボックスにテキスト コンテンツを追加します。|  
|[CFileDialog::ApplyOFNToShellDialog](#applyofntoshelldialog)|状態を更新、`CFileDialog`パラメーターとに格納されているフラグが一致するように、`m_ofn`メンバー変数です。|  
|[CFileDialog::DoModal](#domodal)|ダイアログ ボックスを表示および選択を行うことができます。|  
|[CFileDialog::EnableOpenDropDown](#enableopendropdown)|ドロップダウン リストを有効に、**開く**または**保存** ダイアログ ボックスのボタンをクリックします。|  
|[CFileDialog::EndVisualGroup](#endvisualgroup)|ダイアログ ボックスのビジュアル グループに対する要素の追加を停止します。|  
|[CFileDialog::GetCheckButtonState](#getcheckbuttonstate)|ダイアログ ボックスで、チェック ボタン (チェック ボックス) の現在の状態を取得します。|  
|[CFileDialog::GetControlItemState](#getcontrolitemstate)|ダイアログ ボックスであるコンテナー コントロール内のアイテムの現在の状態を取得します。|  
|[CFileDialog::GetControlState](#getcontrolstate)|現在の可視性を取得し、特定のコントロールの状態を有効にします。|  
|[CFileDialog::GetEditBoxText](#geteditboxtext)|編集ボックス コントロールで現在のテキストを取得します。|  
|[CFileDialog::GetFileExt](#getfileext)|選択したファイルの拡張子を返します。|  
|[CFileDialog::GetFileName](#getfilename)|選択したファイルのファイル名を返します。|  
|[CFileDialog::GetFileTitle](#getfiletitle)|選択したファイルのタイトルを返します。|  
|[CFileDialog::GetFolderPath](#getfolderpath)|エクスプ ローラー スタイルの現在開いているフォルダーまたはディレクトリのパスを取得**開く**または**名前を付けて保存**コモン ダイアログ ボックス。|  
|[CFileDialog::GetIFileDialogCustomize](#getifiledialogcustomize)|カスタマイズされた内部 COM オブジェクトを取得`CFileDialog`オブジェクトです。|  
|[CFileDialog::GetIFileOpenDialog](#getifileopendialog)|内部の COM オブジェクトを取得、`CFileDialog`として使用される、**開く**ファイル ダイアログ ボックス。|  
|[CFileDialog::GetIFileSaveDialog](#getifilesavedialog)|内部の COM オブジェクトを取得、`CFileDialog`として使用される、**保存**ファイル ダイアログ ボックス。|  
|[CFileDialog::GetNextPathName](#getnextpathname)|次の選択したファイルの完全なパスを返します。|  
|[CFileDialog::GetOFN](#getofn)|取得、`OPENFILENAME`の構造、`CFileDialog`オブジェクトです。|  
|[CFileDialog::GetPathName](#getpathname)|選択したファイルの完全なパスを返します。|  
|[CFileDialog::GetReadOnlyPref](#getreadonlypref)|選択したファイルの読み取り専用の状態を返します。|  
|[CFileDialog::GetResult](#getresult)|ユーザーがダイアログ ボックスで行った選択を取得します。|  
|[CFileDialog::GetResults](#getresults)|複数選択が可能なダイアログで、ユーザーの選択肢を取得します。|  
|[CFileDialog::GetSelectedControlItem](#getselectedcontrolitem)|ダイアログ ボックスで指定されたコンテナー コントロールからの特定のアイテムを取得します。|  
|[CFileDialog::GetStartPosition](#getstartposition)|ファイル名の一覧の最初の要素の位置を返します。|  
|[CFileDialog::HideControl](#hidecontrol)|エクスプ ローラー スタイルで指定したコントロールの表示と非**開く**または**名前を付けて保存**コモン ダイアログ ボックス。|  
|[CFileDialog::IsPickFoldersMode](#ispickfoldersmode)|かどうかをフォルダー ピッカー モードの現在のダイアログ ボックス。|  
|[CFileDialog::MakeProminent](#makeprominent)|に比べてコントロールに配置 ダイアログで目立つように追加された他のコントロールにします。|  
|[CFileDialog::RemoveControlItem](#removecontrolitem)|コンテナー コントロール ダイアログ ボックスから項目を削除します。|  
|[CFileDialog::SetCheckButtonState](#setcheckbuttonstate)|ダイアログ ボックスで、チェック ボタン (チェック ボックス) の現在の状態を設定します。|  
|[CFileDialog::SetControlItemState](#setcontrolitemstate)|ダイアログ ボックスであるコンテナー コントロールの項目の現在の状態を設定します。|  
|[CFileDialog::SetControlItemText](#setcontrolitemtext)|コントロールの項目のテキストを設定します。 たとえば、ラジオ ボタンまたはメニュー内の項目に付随するテキストです。|  
|[CFileDialog::SetControlLabel](#setcontrollabel)|ボタンのテキストまたはエディット ボックスのラベルなどのコントロールに関連付けられているテキストを設定します。|  
|[CFileDialog::SetControlState](#setcontrolstate)|現在の可視性を設定し、特定のコントロールの状態を有効にします。|  
|[CFileDialog::SetControlText](#setcontroltext)|エクスプ ローラー スタイルの指定したコントロールのテキストを設定**開く**または**名前を付けて保存**コモン ダイアログ ボックス。|  
|[CFileDialog::SetDefExt](#setdefext)|エクスプ ローラー スタイルの既定のファイル名拡張子を設定**開く**または**名前を付けて保存**コモン ダイアログ ボックス。|  
|[CFileDialog::SetEditBoxText](#seteditboxtext)|編集ボックス コントロールで現在のテキストを設定します。|  
|[CFileDialog::SetProperties](#setproperties)|保存される項目に対して使用される既定値を定義するプロパティ ストアを提供します。|  
|[CFileDialog::SetSelectedControlItem](#setselectedcontrolitem)|オプション ボタン グループ、またはダイアログ ボックスで、特定の項目の選択状態を設定します。|  
|[CFileDialog::SetTemplate](#settemplate)|ダイアログ ボックスのテンプレートの設定、`CFileDialog`オブジェクトです。|  
|[CFileDialog::StartVisualGroup](#startvisualgroup)|ダイアログ ボックスでグループを宣言します。 以降、"add"メソッドを呼び出すは、それらの要素をこのグループに追加します。|  
|[CFileDialog::UpdateOFNFromShellDialog](#updateofnfromshelldialog)|格納されているデータを更新、`m_ofn`ファイル ダイアログ ボックスの現在の状態と一致するメンバー変数です。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFileDialog::OnButtonClicked](#onbuttonclicked)|ボタンがクリックされたときに呼び出されます。|  
|[CFileDialog::OnCheckButtonToggled](#oncheckbuttontoggled)|チェック ボックスがオンまたはオフにすると呼び出されます。|  
|[CFileDialog::OnControlActivating](#oncontrolactivating)|コントロールがアクティブになると呼び出されます。|  
|[CFileDialog::OnFileNameChange](#onfilenamechange)|処理、`WM_NOTIFY CDN_SELCHANGE`メッセージです。|  
|[CFileDialog::OnFileNameOK](#onfilenameok)|ダイアログ ボックスに入力したファイル名を検証します。|  
|[CFileDialog::OnFolderChange](#onfolderchange)|処理、`WM_NOTIFY CDN_FOLDERCHANGE`メッセージです。|  
|[CFileDialog::OnInitDone](#oninitdone)|処理、`WM_NOTIFY CDN_INITDONE`メッセージです。|  
|[CFileDialog::OnItemSelected](#onitemselected)|コンテナー アイテムが選択されているときに呼び出されます。|  
|[CFileDialog::OnLBSelChangedNotify](#onlbselchangednotify)|ファイルの選択が変更されたときに、カスタム アクションを実行できます。|  
|[CFileDialog::OnShareViolation](#onshareviolation)|共有違反を処理します。|  
|[CFileDialog::OnTypeChange](#ontypechange)|処理、`WM_NOTIFY CDN_TYPECHANGE`メッセージです。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[:M_ofn](#m_ofn)|Windows`OPENFILENAME`構造体。 基本的なファイル ダイアログ ボックスのパラメーターへのアクセスを提供します。|  
  
## <a name="remarks"></a>コメント  
 コモン ファイル ダイアログ ボックスでは、ファイルの選択 ダイアログ ボックス、たとえばを実装することによって**ファイルを開く**と**名前を付けて保存**Windows の標準に一致するようにします。  
  
 使用することができます`CFileDialog`ですが、コンス トラクターを持つか、独自のダイアログ ボックス クラスから派生させることができます`CFileDialog`と、ニーズに合わせてコンス トラクターを記述します。 いずれの場合、これらのダイアログ ボックスと同様に MFC の標準のダイアログ ボックスから派生しているため、 [CCommonDialog クラス](../../mfc/reference/ccommondialog-class.md)します。 `CFileDialog`COMMDLG に依存します。Windows に含まれている DLL ファイルです。  
  
 外観と機能の両方、`CFileDialog`と[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]Windows の以前のバージョンとは異なります。 既定値`CFileDialog`自動的には、新しい[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]せず、プログラムをコンパイルした場合、コードの変更と実行スタイル[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]します。 使用して、`bVistaStyle`を手動でこの自動更新をオーバーライドするコンス トラクターのパラメーターです。 自動更新の例外では、カスタマイズしたダイアログ ボックスです。 これらは新しいスタイルに変換されません。 コンス トラクターの詳細については、次を参照してください。 [CFileDialog::CFileDialog](#cfiledialog)します。  
  
> [!NOTE]
>  コントロールの ID システムの違いは[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]以前のバージョンの Windows を使用する場合、`CFileDialog`です。 すべての参照を更新する必要があります`CFileDialog`以前のバージョンの Windows からプロジェクトを移植する前に、コード内のコントロールです。  
  
 いくつか`CFileDialog`メソッドは、サポートされていません[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]します。 について、メソッドがサポートされているかどうかは個々 のメソッドのトピックを確認してください。 さらに、次の継承された関数はサポートされていません[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]:  
  
- [CDialog::OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog)  
  
- [CDialog::OnSetFont](../../mfc/reference/cdialog-class.md#onsetfont)  
  
 Windows メッセージ、`CFileDialog`クラスを使用しているオペレーティング システムによって異なります。 たとえば、Windows XP はサポートされません[CDialog::OnCancel](../../mfc/reference/cdialog-class.md#oncancel)と[CDialog::OnOK](../../mfc/reference/cdialog-class.md#onok)の`CFileDialog`クラスです。 ただし、[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]はそれらをサポートします。 生成されるさまざまなメッセージおよび受信される順序の詳細については、次を参照してください。 [CFileDialog サンプル: ログ記録イベントの順序](../../visual-cpp-samples.md)します。  
  
 使用する、`CFileDialog`オブジェクトを使用して、オブジェクトを作成して、`CFileDialog`コンス トラクターです。 ダイアログ ボックスが構築した後は、設定または任意の値を変更、 [::m_ofn](#m_ofn)値やダイアログ ボックスのコントロールの状態を初期化するためにします。 `m_ofn`型の構造は、`OPENFILENAME`です。 詳細については、次を参照してください。、 [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 ダイアログ ボックスのコントロールを初期化した後で呼び出し、 [CFileDialog::DoModal](#domodal)ダイアログ ボックスを表示するメソッドをボックス、ユーザーがパスとファイル名を入力できるようにします。 `DoModal`ユーザーには、[ok] (IDOK) またはキャンセル (IDCANCEL) ボタンがクリックしたかどうかを返します。 場合`DoModal`IDOK を返すのいずれかを使用することができます、`CFileDialog`にユーザーが情報を取得するパブリック メンバー関数を配置します。  
  
> [!NOTE]
>  [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]を複数回呼び出す[IFileDialog::SetFileTypes](http://msdn.microsoft.com/library/windows/desktop/bb775980)エラーが発生します。 2 番目の呼び出し`SetFileTypes`のすべてのインスタンス、`CFileDialog`戻ります`E_UNEXPECTED`で[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]します。 いくつか`CFileDialog`メソッドの関数呼び出し`SetFileTypes`します。 たとえば、2 回の呼び出しに`CFileDialog::DoModal`の同じインスタンスに対して、`CFileDialog`が生成されます[ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c)します。  
  
 `CFileDialog`共有違反、ファイル名の検証および変更通知のリスト ボックスのカスタム処理を実行できるいくつかの保護されたメンバーが含まれます。 これらのプロテクト メンバーは、ほとんどのアプリケーションは、既定の処理は自動的に行われるために使用する必要はありませんコールバック関数です。 標準の仮想関数であるために、これらの関数のメッセージ マップ エントリは必要ありません。  
  
 ウィンドウを使用できます[情報を得る](http://msdn.microsoft.com/library/windows/desktop/ms646916)関数 ダイアログ ボックスの初期化中にエラーが発生したかどうかを確認し、エラーについて説明します。  
  
 破棄`CFileDialog`オブジェクトが自動的に処理されます。 呼び出す必要はありません[CDialog::EndDialog](../../mfc/reference/cdialog-class.md#enddialog)します。  
  
 ユーザーが複数のファイルを選択できるように、設定、`OFN_ALLOWMULTISELECT`フラグを呼び出す前に`DoModal`します。 複数のファイル名のリストに合わせて独自ファイル名のバッファーを指定してください。 これには、置き換える`m_ofn.lpstrFile`バッファーへのポインターが割り当てられていれば、構築した後、`CFileDialog`を呼び出す前に、`DoModal`です。  
  
 さらに、設定する必要があります`m_ofn.nMaxFile`が指すバッファーに文字数を使用して、`m_ofn.lpstrFile`です。 選択するファイルの最大数を設定すると`n`、必要なバッファー サイズは`n * (_MAX_PATH + 1) + 1`です。 バッファーに返される最初の項目は、選択したファイル、フォルダーへのパスです。 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]のスタイルダイアログ ボックスでは、ディレクトリとファイル名の文字列が最後のファイル名の後、追加の null 文字で、null で終わる。 この形式は、スペースが含まれる長いファイル名を返すエクスプ ローラー スタイルのダイアログ ボックスを使用できます。 旧式のダイアログ ボックスのディレクトリとファイル名の文字列は、スペースで区切られ、関数がスペースを含むファイル名の短いファイル名を使用します。  
  
 次の例では、バッファーを使用して取得し、複数のファイル名を一覧表示する方法を示します。  
  
 [!code-cpp[NVC_MFCFiles 第&23;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiledialog-class_1.cpp)]  
  
 複数のファイル名を選択すると、ユーザーへの応答のバッファーのサイズを変更するから新しいクラスを派生する必要があります`CFileDialog`させ、 [CFileDialog::OnFileNameChange](#onfilenamechange)メソッドです。  
  
 新しいクラスを派生させる場合`CFileDialog`、すべてのメッセージを処理するメッセージ マップを使用することができます。 既定のメッセージ処理を拡張するには、派生クラスを`CFileDialog`メッセージ マップを新しいクラスに追加し、新しいメッセージのメンバー関数を提供します。 ダイアログ ボックスをカスタマイズするフック関数を用意する必要はありません。  
  
 ダイアログ ボックスをカスタマイズするには、派生クラスを`CFileDialog`拡張されたコントロールからの通知メッセージを処理するメッセージ マップを追加、カスタム ダイアログ ボックス テンプレートを使用します。 基本クラスに処理されないメッセージを渡します。 フック関数をカスタマイズする必要はありません。  
  
 使用する場合は、[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]のスタイル、 `CFileDialog`、メッセージ マップとダイアログ ボックスのテンプレートを使用することはできません。 代わりに、同様の機能を COM インターフェイスを使用する必要があります。  
  
 使用する方法の詳細についての`CFileDialog`を参照してください[コモン ダイアログ クラス](../../mfc/common-dialog-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFileDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdlgs.h  
  
##  <a name="a-nameaddcheckbuttona--cfiledialogaddcheckbutton"></a><a name="addcheckbutton"></a>CFileDialog::AddCheckButton  
 ダイアログ ボックスに、チェック ボタンを追加します。  
  
```  
HRESULT AddCheckButton(
    DWORD dwIDCtl,  
    const CString& strLabel,  
    BOOL bChecked);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 追加するチェック マークのボタンの ID。  
  
 `strLabel`  
 チェック ボタンの名前。  
  
 `bChecked`  
 チェック マークのボタンの現在の状態を示すブール値。 `TRUE`チェックされている場合`FALSE`それ以外の場合  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameaddcomboboxa--cfiledialogaddcombobox"></a><a name="addcombobox"></a>CFileDialog::AddComboBox  
 ダイアログ ボックスに、コンボ ボックスを追加します。  
  
```  
HRESULT AddComboBox(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 追加するコンボ ボックスの ID。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameaddcontrolitema--cfiledialogaddcontrolitem"></a><a name="addcontrolitem"></a>CFileDialog::AddControlItem  
 ダイアログ ボックスのコンテナー コントロールに項目を追加します。  
  
```  
HRESULT AddControlItem(
    DWORD dwIDCtl,  
    DWORD dwIDItem,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 項目を追加するコンテナー コントロールの ID。  
  
 `dwIDItem`  
 項目の ID です。  
  
 `strLabel`  
 項目のテキスト。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameaddeditboxa--cfiledialogaddeditbox"></a><a name="addeditbox"></a>CFileDialog::AddEditBox  
 ダイアログ ボックスを編集ボックスを追加します。  
  
```  
HRESULT AddEditBox(
    DWORD dwIDCtl,  
    const CString& strText);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 追加する編集ボックスの ID。  
  
 `strText`  
 編集ボックスの名前。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameaddmenua--cfiledialogaddmenu"></a><a name="addmenu"></a>CFileDialog::AddMenu  
 ダイアログ ボックスにメニューを追加します。  
  
```  
HRESULT AddMenu(
    DWORD dwIDCtl,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 追加するメニューの ID。  
  
 `strLabel`  
 メニューの名前。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameaddplacea--cfiledialogaddplace"></a><a name="addplace"></a>CFileDialog::AddPlace  
 一覧にフォルダーはユーザーが開くか、項目を保存するために使用できる場所を追加します。  
  
```  
void AddPlace(
    LPCWSTR lpszFolder,  
    FDAP fdap = FDAP_TOP) throw();

 
void AddPlace(
    IShellItem* psi,  
    FDAP fdap = FDAP_TOP) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFolder`  
 ユーザーに使用できるフォルダーへのパス。 フォルダーのみ指定できます。  
  
 `fdap`  
 リスト内でフォルダーを配置する場所を指定します。  
  
 `psi`  
 使用可能にするユーザーにフォルダーを表す IShellItem へのポインター。 フォルダーのみ指定できます。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameaddpushbuttona--cfiledialogaddpushbutton"></a><a name="addpushbutton"></a>CFileDialog::AddPushButton  
 ダイアログ ボックスにボタンを追加します。  
  
```  
HRESULT AddPushButton(
    DWORD dwIDCtl,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 追加するボタンの ID。  
  
 `strLabel`  
 ボタンの名前。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameaddradiobuttonlista--cfiledialogaddradiobuttonlist"></a><a name="addradiobuttonlist"></a>CFileDialog::AddRadioButtonList  
 ダイアログ ボックスにオプション ボタンとも呼ばれます) グループを追加します。  
  
```  
HRESULT AddRadioButtonList(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 追加するオプション ボタン グループの ID。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameaddseparatora--cfiledialogaddseparator"></a><a name="addseparator"></a>CFileDialog::AddSeparator  
 ダイアログ ボックスに、区切り記号を追加します。  
  
```  
HRESULT AddSeparator(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 区切り記号の ID を追加します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameaddtexta--cfiledialogaddtext"></a><a name="addtext"></a>CFileDialog::AddText  
 ダイアログ ボックスにテキストを追加します。  
  
```  
HRESULT AddText(
    DWORD dwIDCtl,  
    const CString& strText);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 追加するテキストの ID。  
  
 `strText`  
 テキストの名前。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameapplyofntoshelldialoga--cfiledialogapplyofntoshelldialog"></a><a name="applyofntoshelldialog"></a>CFileDialog::ApplyOFNToShellDialog  
 現在の状態を更新、 [CFileDialog](../../mfc/reference/cfiledialog-class.md)に格納された値に基づいて、`m_ofn`データ構造体。  
  
```  
void ApplyOFNToShellDialog();
```  
  
### <a name="remarks"></a>コメント  
 前に Windows のバージョンで[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]、メンバー [OPENFILENAME](https://msdn.microsoft.com/library/ms911906.aspx)の状態と、このデータ構造を常に同期、`CFileDialog`です。 変更、 [m_ofn](#m_ofn)メンバー変数が、ダイアログ ボックスの状態に直ちに反映されます。 ダイアログ ボックスの状態への変更が直ちに更新も、`m_ofn`メンバー変数です。  
  
 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]、内の値、`m_ofn`メンバー変数との状態、`CFileDialog`同期とは限りません。 この関数の状態の強制、`CFileDialog`一致するように更新する、`m_ofn`構造体。 Windows は時に自動的には、この関数を呼び出します[CFileDialog::DoModal](#domodal)します。  
  
 使用する方法の詳細についての`CFileDialog`クラスの下にある[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]を参照してください[CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)します。  
  
### <a name="example"></a>例  
  例を参照してください[CFileDialog::UpdateOFNFromShellDialog](#updateofnfromshelldialog)します。  
  
##  <a name="a-namecfiledialoga--cfiledialogcfiledialog"></a><a name="cfiledialog"></a>CFileDialog::CFileDialog  
 Windows の標準ファイル ダイアログ ボックスを作成するには、この関数を呼び出します。  
  
```  
explicit CFileDialog(
    BOOL bOpenFileDialog,  
    LPCTSTR lpszDefExt = NULL,  
    LPCTSTR lpszFileName = NULL,  
    DWORD dwFlags = OFN_HIDEREADONLY | OFN_OVERWRITEPROMPT,  
    LPCTSTR lpszFilter = NULL,  
    CWnd* pParentWnd = NULL,  
    DWORD dwSize = 0,  
    BOOL bVistaStyle = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bOpenFileDialog`  
 作成する ダイアログ ボックスの種類を指定するパラメーター。 設定`TRUE`を構築する、**ファイルを開く** ダイアログ ボックス。 設定`FALSE`を構築する、**ファイル名を付けて** ダイアログ ボックス。  
  
 [入力] `lpszDefExt`  
 既定のファイル名の拡張子です。 拡張機能が指定された場合は、ユーザーは、ファイル名 ボックス (ユーザーのコンピューターの関連付けのあるもの) 既知の拡張子を含まない、`lpszDefExt`ファイル名に自動的に追加します。 このパラメーターは場合`NULL`、拡張機能は追加されません。  
  
 [入力] `lpszFileName`  
 ファイル名 ボックスに表示される初期ファイル名。 場合`NULL`、初期ファイル名は表示されません。  
  
 [入力] `dwFlags`  
 ダイアログ ボックスをカスタマイズするのに使用できる&1; つまたは複数のフラグの組み合わせ。 これらのフラグの説明は、次を参照してください。、 [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 変更した場合、`m_ofn.Flags`メンバーを構造体、変更内容でビットごとの OR 演算子を使用して、既定の動作をそのまま維持されます。  
  
 [入力] `lpszFilter`  
 一連のフィルターを指定する文字列のペアをファイルに適用できます。 フィルターを指定する場合は、フィルター条件に一致するファイルのみがファイルの一覧に表示されます。 ファイル フィルターを操作する方法の詳細については、「解説」を参照してください。  
  
 [入力] `pParentWnd`  
 ファイル ダイアログ ボックスの親またはオーナー ウィンドウへのポインター。  
  
 [入力] `dwSize`  
 サイズ、`OPENFILENAME`構造体。 この値は、オペレーティング システムのバージョンによって異なります。 MFC を作成する ダイアログ ボックスの適切な種類は、このパラメーターを使用する (たとえば、この新しい[!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)]NT4 ダイアログ ボックスではなくダイアログ ボックス)。 0 の場合、MFC コードが適切なダイアログ ボックスのサイズを決定する既定のサイズは、プログラムが実行されるオペレーティング システムのバージョンに基づいています。  
  
 [入力] `bVistaStyle`  
 **注**このパラメーターは Visual Studio 2008 では使用し、後で、で実行している場合にのみ使用する新しいスタイル ダイアログが発生する[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]またはそれ以降。  
  
 このパラメーターは、ファイル ダイアログ ボックスのスタイルを指定します。 設定`TRUE`Vista スタイルの新しいファイル ダイアログを使用します。 それ以外の場合、古い形式のダイアログ ボックスが使用されます。 Vista で実行されているに関する詳細については「解説」セクションをを表示します。  
  
### <a name="remarks"></a>コメント  
 いずれか、**ファイルを開く**または**ファイル名を付けて**の値に応じて、ダイアログ ボックスが作成された`bOpenFileDialog`します。  
  
 使用して既定の拡張子を指定する`lpszDefExt`拡張機能については、ユーザーのコンピューターにファイルのアソシエーションを持つ予測可能ではめったにないために、予測どおりに動作をもたらさないことがあります。 独自のクラスを派生する既定の拡張機能の追加より詳細に制御する場合は、`CFileDialog`をオーバーライドし、`CFileDialog::OnFileNameOK`メソッドを自身の拡張機能の処理を実行します。  
  
 ユーザーが複数のファイルを選択できるように、設定、`OFN_ALLOWMULTISELECT`フラグを呼び出す前に[DoModal](#domodal)します。 複数のファイル名のリストを格納する独自ファイル名のバッファーを指定する必要があります。 これには、置き換える`m_ofn.lpstrFile`バッファーへのポインターが割り当てられていれば、構築した後、 [CFileDialog](../../mfc/reference/cfiledialog-class.md)を呼び出す前に、`DoModal`です。 さらに、設定する必要があります`m_ofn.nMaxFile`が指すバッファー内の文字数で`m_ofn.lpstrFile`します。 選択するファイルの最大数を設定すると`n`、必要なバッファー サイズは`n`*(_MAX_PATH + 1) + 1 です。 例:  
  
 [!code-cpp[NVC_MFCFiles 第&23;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiledialog-class_1.cpp)]  
  
 マウスまたはキーボードを使用して、[エクスプ ローラー スタイル] ダイアログ ボックスのサイズを変更するユーザーを有効にするには設定、`OFN_ENABLESIZING`フラグ。 このフラグを設定することは、フック プロシージャまたはカスタム テンプレートを指定する場合にのみ必要です。 フラグは、エクスプ ローラー スタイル ダイアログ ボックスでのみ動作します。旧式のダイアログ ボックスのサイズを変更できません。  
  
 `lpszFilter`ファイル名、ファイルの一覧に表示する必要のあるファイルの種類を決定するパラメーターを使用します。 文字列のペアの最初の文字列、フィルターを説明します。2 番目の文字列では、使用するファイル名拡張子を示します。 複数の拡張機能は、区切り記号としてセミコロン (';' の文字) を使用して指定できます。 2 つの文字列の末尾に ' |' 文字の後に、`NULL`文字です。 使用することも、 [CString](../../atl-mfc-shared/using-cstring.md)このパラメーターにします。  
  
 たとえば、[!INCLUDE[ofprexcel](../../mfc/reference/includes/ofprexcel_md.md)]他 .xlc (グラフ) の拡張機能または .xls (ワークシート) を持つファイルを開くことができます。 Excel 用のフィルターは、としてを記述できます。  
  
 [!code-cpp[NVC_MFCFiles #&24;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiledialog-class_2.cpp)]  
  
 ただし、この文字列は直接使用する予定の場合は更新、`OPENFILENAME`構造体、垂直バーではなく ' \0' での null 文字、文字列を区切る必要があります ('| ')。  
  
 `bVistaStyle`パラメーターで実行されている場合にのみ適用[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]します。 以前のバージョンの Windows では、このパラメーターは無視されます。 場合`bVistaStyle`に設定されている`TRUE`プログラムをコンパイルするときに、[!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)]またはそれ以降、新しい Vista スタイル**ファイル ダイアログ**が適用されます。 それ以外の場合、以前の MFC スタイル**ファイル ダイアログ**が適用されます。  
  
 ダイアログ テンプレートがに基づいてダイアログでサポートされていません`bVistaStyle`  
  
### <a name="example"></a>例  
  例を参照してください[CFileDialog::DoModal](#domodal)します。  
  
##  <a name="a-namedomodala--cfiledialogdomodal"></a><a name="domodal"></a>CFileDialog::DoModal  
 Windows コモン ファイル ダイアログ ボックスを表示し、ユーザーがファイルとディレクトリを参照して、ファイル名を入力できるようにするには、この関数を呼び出します。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 **IDOK**または**IDCANCEL**します。 場合**IDCANCEL**は、Windows を呼び出し、返される[情報を得る](http://msdn.microsoft.com/library/windows/desktop/ms646916)エラーが発生したかどうかを判断します。  
  
 **IDOK**と**IDCANCEL**をユーザーが [ok] または [キャンセル] ボタンを選択するかどうかを示す定数です。  
  
### <a name="remarks"></a>コメント  
 メンバーを設定して、さまざまなファイル ダイアログ ボックスのオプションを初期化する場合、 **m_ofn**構造体を呼び出す前に、これを行う必要があります`DoModal`はダイアログ オブジェクトを構築します。  
  
 たとえば、複数のファイルを選択できるようにする場合は、設定、`OFN_ALLOWMULTISELECT`フラグを呼び出す前に`DoModal`のこのトピックのコード例に示すようにします。  
  
 ダイアログ ボックスの [ok] または [キャンセル] ボタンか、または [閉じる] ダイアログ ボックスのオプションをユーザーがクリックしたコントロール、メニュー、コントロールは、アプリケーションに返されます。 関数を呼び出すことの他のメンバーの設定や情報を取得するユーザー入力 ダイアログ ボックスにします。  
  
 `DoModal`クラスからオーバーライドされた仮想関数は、`CDialog`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles&#25;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiledialog-class_3.cpp)]  
  
##  <a name="a-nameenableopendropdowna--cfiledialogenableopendropdown"></a><a name="enableopendropdown"></a>CFileDialog::EnableOpenDropDown  
 開くときにボタンまたは [保存] ダイアログ ボックスのドロップダウン リストを有効にします。  
  
```  
HRESULT EnableOpenDropDown(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 ドロップダウン リストの ID。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameendvisualgroupa--cfiledialogendvisualgroup"></a><a name="endvisualgroup"></a>CFileDialog::EndVisualGroup  
 ダイアログ ボックスのビジュアル グループに対する要素の追加を停止します。  
  
```  
HRESULT EndVisualGroup();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は S_OK を返します。それ以外の場合エラー値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetcheckbuttonstatea--cfiledialoggetcheckbuttonstate"></a><a name="getcheckbuttonstate"></a>CFileDialog::GetCheckButtonState  
 ダイアログ ボックスで、チェック ボタン (チェック ボックス) の現在の状態を取得します。  
  
```  
HRESULT GetCheckButtonState(
    DWORD dwIDCtl,  
    BOOL& bChecked);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 チェック ボックスの ID です。  
  
 `bChecked`  
 チェック ボックスの状態。 `TRUE`checked; を示します`FALSE`オンになっていないことを示します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetcontrolitemstatea--cfiledialoggetcontrolitemstate"></a><a name="getcontrolitemstate"></a>CFileDialog::GetControlItemState  
 ダイアログ ボックスであるコンテナー コントロール内のアイテムの現在の状態を取得します。  
  
```  
HRESULT GetControlItemState(
    DWORD dwIDCtl,  
    DWORD dwIDItem,  
    CDCONTROLSTATEF& dwState);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 コンテナー コントロールの ID。  
  
 `dwIDItem`  
 項目の ID です。  
  
 `dwState`  
 コントロールの現在の状態を示す CDCONTROLSTATE 列挙体からより多くの値のいずれかを受け取る変数への参照。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetcontrolstatea--cfiledialoggetcontrolstate"></a><a name="getcontrolstate"></a>CFileDialog::GetControlState  
 現在の可視性を取得し、特定のコントロールの状態を有効にします。  
  
```  
HRESULT GetControlState(
    DWORD dwIDCtl,  
    CDCONTROLSTATEF& dwState);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 コントロールの ID です。  
  
 `dwState`  
 コントロールの現在の状態を示す CDCONTROLSTATE 列挙体から&1; つまたは複数の値を受け取る変数への参照。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegeteditboxtexta--cfiledialoggeteditboxtext"></a><a name="geteditboxtext"></a>CFileDialog::GetEditBoxText  
 編集ボックス コントロールで現在のテキストを取得します。  
  
```  
HRESULT GetEditBoxText(
    DWORD dwIDCtl,  
    CString& strText);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 編集ボックスの ID です。  
  
 `strText`  
 テキスト値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetfileexta--cfiledialoggetfileext"></a><a name="getfileext"></a>CFileDialog::GetFileExt  
 この関数では、ダイアログ ボックスに入力されたファイル名の拡張子を取得します。  
  
```  
CString GetFileExt() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ファイル名の拡張子です。  
  
### <a name="remarks"></a>コメント  
 たとえば、ファイルの名前が入力した場合は、データです。TXT、 `GetFileExt` "TXT"を返します。  
  
 場合`m_ofn.Flags`が、`OFN_ALLOWMULTISELECT`フラグを設定、この文字列には、最初の文字列を選択すると、ファイル グループのディレクトリ パスの中で、null で終わる文字列のシーケンスが含まれています。 後に、ユーザーが選択したすべてのファイルの名前。 ファイルのパス名を取得する、[中](#getstartposition)と[に](#getnextpathname)メンバー関数。  
  
##  <a name="a-namegetfilenamea--cfiledialoggetfilename"></a><a name="getfilename"></a>CFileDialog::GetFileName  
 この関数では、ダイアログ ボックスに入力したファイル名の名前を取得します。  
  
```  
CString GetFileName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ファイルの名前です。  
  
### <a name="remarks"></a>コメント  
 ファイルの名前には、プレフィックスと拡張機能の両方が含まれています。 たとえば、`GetFileName`戻ります"テキストです。DAT"C:\FILES\TEXT.DAT ファイルです。  
  
 場合`m_ofn.Flags`が、`OFN_ALLOWMULTISELECT`フラグ設定、呼び出す必要があります[中](#getstartposition)と[に](#getnextpathname)ファイルのパス名を取得します。  
  
##  <a name="a-namegetfiletitlea--cfiledialoggetfiletitle"></a><a name="getfiletitle"></a>CFileDialog::GetFileTitle  
 ダイアログ ボックスに入力されたファイルのタイトルを取得するには、この関数を呼び出します。  
  
```  
CString GetFileTitle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ファイルのタイトルです。  
  
### <a name="remarks"></a>コメント  
 ファイルのタイトルには、パスまたは拡張機能なし、プレフィックスのみが含まれています。 たとえば、 `GetFileTitle` C:\FILES\TEXT.DAT ファイルの"TEXT"を返します。  
  
 場合`m_ofn.Flags`が、`OFN_ALLOWMULTISELECT`フラグを設定、この文字列には、最初の文字列を選択すると、ファイル グループのディレクトリ パスの中で、null で終わる文字列のシーケンスが含まれています。 後に、ユーザーが選択したすべてのファイルの名前。 このため、使用して、[中](#getstartposition)と[に](#getnextpathname)メンバー関数を一覧には、次のファイル名を取得します。  
  
### <a name="example"></a>例  
  例を参照してください[CFileDialog::DoModal](#domodal)します。  
  
##  <a name="a-namegetfolderpatha--cfiledialoggetfolderpath"></a><a name="getfolderpath"></a>CFileDialog::GetFolderPath  
 現在開いているフォルダーまたはエクスプ ローラー スタイルのオープンまたは名前を付けて保存の共通のダイアログ ボックスのディレクトリのパスを取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetFolderPath() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)現在開いているフォルダーまたはディレクトリを含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 ダイアログ ボックスが作成されている必要があります、 **OFN_EXPLORER**スタイル。 それ以外の場合、メソッドは、アサーションに失敗します。  
  
 ダイアログ ボックスが表示されている間にのみ、このメソッドを呼び出すことができます。 ダイアログ ボックスが閉じられると、この関数は機能しなくし、このメソッドは、アサーションに失敗します。  
  
##  <a name="a-namegetifiledialogcustomizea--cfiledialoggetifiledialogcustomize"></a><a name="getifiledialogcustomize"></a>CFileDialog::GetIFileDialogCustomize  
 内部の COM オブジェクトへのポインターを取得する指定された[CFileDialog](../../mfc/reference/cfiledialog-class.md)します。  
  
```  
IFileDialogCustomize* GetIFileDialogCustomize();
```  
  
### <a name="return-value"></a>戻り値  
 内部の COM オブジェクトへのポインター、`CFileDialog`です。 ユーザーの責任において、このポインターを適切に解放することをお勧めします。  
  
### <a name="remarks"></a>コメント  
 この関数は下位にのみ使用[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]を持つオブジェクトで`bVistaStyle`に設定`true`します。 この関数を使用する場合と`bVistaStyle`は`false`が返されます`NULL`リリース モードでデバッグ モードではアサーションをスローします。  
  
 詳細については、`IFileDialogCustomize`インターフェイスは、「 [IFileDialogCustomize](http://msdn.microsoft.com/library/windows/desktop/bb775912)します。  
  
### <a name="example"></a>例  
 この例では、内部の COM オブジェクトを取得します。 このコード例を実行する、下をコンパイルする必要があります[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]します。  
  
 [!code-cpp[NVC_MFC_CFileDialog&4;](../../mfc/reference/codesnippet/cpp/cfiledialog-class_4.cpp)]  
  
##  <a name="a-namegetifileopendialoga--cfiledialoggetifileopendialog"></a><a name="getifileopendialog"></a>CFileDialog::GetIFileOpenDialog  
 内部の COM オブジェクトへのポインターを取得する指定された`CFileDialog`します。  
  
```  
IFileOpenDialog* GetIFileOpenDialog();
```  
  
### <a name="return-value"></a>戻り値  
 内部の COM オブジェクトへのポインター、`CFileDialog`です。 ユーザーの責任において、このポインターを適切に解放することをお勧めします。  
  
### <a name="remarks"></a>コメント  
 この関数は下位にのみ使用[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]を持つオブジェクトで`bVistaStyle`に設定`true`します。 この関数を返します`NULL`場合、`CFileDialog`は、**開く** ダイアログ ボックスまたは`bVistaStyle`に設定されている`false`します。 後者の場合、関数のみを返し`NULL`リリース モードでデバッグ モードでこれはアサーションをスローします。  
  
 詳細については、`IFileOpenDialog`インターフェイスは、「 [IFileOpenDialog](http://msdn.microsoft.com/library/windows/desktop/bb775834)します。  
  
### <a name="example"></a>例  
 この例では、内部の COM オブジェクトを取得します。 このコードを実行するには、コンパイルする必要があります[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]します。  
  
 [!code-cpp[NVC_MFC_CFileDialog&#2;](../../mfc/reference/codesnippet/cpp/cfiledialog-class_5.cpp)]  
  
##  <a name="a-namegetifilesavedialoga--cfiledialoggetifilesavedialog"></a><a name="getifilesavedialog"></a>CFileDialog::GetIFileSaveDialog  
 内部の COM オブジェクトへのポインターを取得する指定された`CFileDialog`します。  
  
```  
IFileSaveDialog* GetIFileSaveDialog();
```  
  
### <a name="return-value"></a>戻り値  
 内部の COM オブジェクトへのポインター、`CFileDialog`です。 ユーザーの責任において、このポインターを適切に解放することをお勧めします。  
  
### <a name="remarks"></a>コメント  
 この関数は下位にのみ使用[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]を持つオブジェクトで`bVistaStyle`に設定`true`します。 この関数は`NULL`場合、`CFileDialog`は、**保存** ダイアログ ボックスまたは`bVistaStyle`に設定されている`false`します。 後者の場合、関数のみを返し`NULL`リリース モードでデバッグ モードでこれはアサーションをスローします。  
  
 詳細については、`IFileSaveDialog`インターフェイスは、「 [IFileSaveDialog](http://msdn.microsoft.com/library/windows/desktop/bb775688)します。  
  
### <a name="example"></a>例  
 この例では、内部の COM オブジェクトを取得します。 このコード例を実行する、下をコンパイルする必要があります[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]します。  
  
 [!code-cpp[NVC_MFC_CFileDialog&#3;](../../mfc/reference/codesnippet/cpp/cfiledialog-class_6.cpp)]  
  
##  <a name="a-namegetnextpathnamea--cfiledialoggetnextpathname"></a><a name="getnextpathname"></a>CFileDialog::GetNextPathName  
 ダイアログ ボックスで選択したグループから次のファイル名を取得するには、この関数を呼び出します。  
  
```  
CString GetNextPathName(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 参照、**位置**以前から返される値`GetNextPathName`または`GetStartPosition`関数の呼び出しです。 **NULL**リストの末尾に到達するとします。  
  
### <a name="return-value"></a>戻り値  
 ファイルの完全パス名を返します。  
  
### <a name="remarks"></a>コメント  
 ファイル名のパスには、ファイルのタイトルとディレクトリの完全パスが含まれています。 たとえば、 `GetNextPathName` "C:\FILES\TEXT を返します。DAT"C:\FILES\TEXT.DAT ファイルです。 使用する`GetNextPathName`への呼び出しでは、最初の位置を確立する場合は、順方向の反復ループで`GetStartPosition`します。  
  
 選択範囲は、1 つのファイルで構成され、そのファイル名が返されます。  
  
##  <a name="a-namegetofna--cfiledialoggetofn"></a><a name="getofn"></a>CFileDialog::GetOFN  
 関連付けられた取得**OPENFILENAME**構造体。  
  
```  
const OPENFILENAME& GetOFN() const;  
  
OPENFILENAME& GetOFN();
```  
  
### <a name="return-value"></a>戻り値  
 [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839)構造体。  
  
### <a name="remarks"></a>コメント  
 外観を初期化するためにこの関数の&2; 番目のバージョンを使用して、**ファイルを開く**または**ファイル名を付けて** ダイアログ ボックスに表示されるようにするが、構築した後、`DoModal`メンバー関数。 たとえば、設定、**キャプションを表示**のメンバー **m_ofn**ダイアログ ボックスにはキャプションにします。  
  
##  <a name="a-namegetpathnamea--cfiledialoggetpathname"></a><a name="getpathname"></a>CFileDialog::GetPathName  
 ダイアログ ボックスに入力したファイルの完全パスを取得するには、この関数を呼び出します。  
  
```  
CString GetPathName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ファイルの完全パス名を返します。  
  
### <a name="remarks"></a>コメント  
 ファイル名のパスには、ファイルのタイトルとディレクトリの完全パスが含まれています。 たとえば、 `GetPathName` "C:\FILES\TEXT を返します。DAT"C:\FILES\TEXT.DAT ファイルです。  
  
 場合`m_ofn.Flags`が、`OFN_ALLOWMULTISELECT`フラグを設定、この文字列は、一連の null で終わる文字列の最初の文字列を選択すると、ファイル グループのディレクトリ パスの中で、後に、ユーザーが選択したすべてのファイルの名前。 このため、使用して、[中](#getstartposition)と[に](#getnextpathname)メンバー関数を一覧には、次のファイル名を取得します。  
  
### <a name="example"></a>例  
  例を参照してください[CFileDialog::DoModal](#domodal)します。  
  
##  <a name="a-namegetreadonlyprefa--cfiledialoggetreadonlypref"></a><a name="getreadonlypref"></a>CFileDialog::GetReadOnlyPref  
 読み取り専用 チェック ボックスを Windows 標準的なファイルを開くとファイル名を付けて ダイアログ ボックスで選択されているかどうかを判断するには、この関数を呼び出します。  
  
```  
BOOL GetReadOnlyPref() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ゼロ以外の値 ダイアログ ボックスでの読み取り専用チェック ボックスがオンの場合それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 設定して、読み取り専用チェック ボックスを非表示にできます、`OFN_HIDEREADONLY`でスタイル設定、`CFileDialog`コンス トラクターです。  
  
> [!NOTE]
> [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]スタイル`CFileDialog`オブジェクトは、この関数をサポートしません。 この関数を使用すると、[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]スタイル`CFileDialog`をスロー[行わない](../../mfc/reference/cnotsupportedexception-class.md)します。   
  
##  <a name="a-namegetresulta--cfiledialoggetresult"></a><a name="getresult"></a>CFileDialog::GetResult  
 ユーザーがダイアログ ボックスで行った選択を取得します。  
  
```  
IShellItem* GetResult() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ユーザーの選択項目を表す IShellItem へのポインター。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetresultsa--cfiledialoggetresults"></a><a name="getresults"></a>CFileDialog::GetResults  
 複数選択が可能なダイアログで、ユーザーの選択肢を取得します。  
  
```  
IShellItemArray* GetResults() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスで選択した項目のアクセスを IShellItemArray へのポインター。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetselectedcontrolitema--cfiledialoggetselectedcontrolitem"></a><a name="getselectedcontrolitem"></a>CFileDialog::GetSelectedControlItem  
 ダイアログ ボックスで指定されたコンテナー コントロールからの特定のアイテムを取得します。  
  
```  
HRESULT GetSelectedControlItem(
    DWORD dwIDCtl,  
    DWORD& dwIDItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 コンテナー コントロールの ID。  
  
 `dwIDItem`  
 ユーザーがコントロールで選択した項目の ID。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetstartpositiona--cfiledialoggetstartposition"></a><a name="getstartposition"></a>CFileDialog::GetStartPosition  
 場合に、リスト内の最初のファイルのパス名の位置を取得するには、このメンバー関数を呼び出して`m_ofn.Flags`が、`OFN_ALLOWMULTISELECT`フラグが設定されます。  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A**位置**反復処理に使用できる値**NULL**リストが空の場合。  
  
##  <a name="a-namehidecontrola--cfiledialoghidecontrol"></a><a name="hidecontrol"></a>CFileDialog::HideControl  
 エクスプ ローラー スタイルのオープンまたは名前を付けて保存の共通のダイアログ ボックスで指定したコントロールを非表示にするには、このメンバー関数を呼び出します。  
  
```  
void HideControl(int nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 非表示にするコントロールの ID。  
  
### <a name="remarks"></a>コメント  
 ダイアログ ボックスが作成されている必要があります、 **OFN_EXPLORER**スタイル。 それ以外の場合、関数は、アサーションに失敗します。  
  
##  <a name="a-nameispickfoldersmodea--cfiledialogispickfoldersmode"></a><a name="ispickfoldersmode"></a>CFileDialog::IsPickFoldersMode  
 現在のダイアログ ボックスがフォルダー ピッカー モードのかどうかを判断します。  
  
```  
BOOL IsPickFoldersMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`フォルダー ピッカー モードの場合は、ダイアログ ボックスそれ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namemofna--cfiledialogmofn"></a><a name="m_ofn"></a>:M_ofn  
 `m_ofn`型の構造体は、`OPENFILENAME`です。 この構造体のデータの現在の状態を表す、`CFileDialog`です。  
  
### <a name="remarks"></a>コメント  
 外観を初期化するために、この構造体を使用して、**ファイルを開く**または**ファイル名を付けて** ダイアログ ボックスを表示する前にそれを作成した後、 [DoModal](#domodal)メソッドです。 たとえば、設定、`lpstrTitle`のメンバー`m_ofn`ダイアログ ボックスにはキャプションにします。  
  
 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]のスタイル[CFileDialog](../../mfc/reference/cfiledialog-class.md)、 `m_ofn`  ダイアログ ボックスの状態は常に一致する保証はありません。 以前のバージョンの Windows ダイアログ ボックスと同期します。 参照してください[CFileDialog::ApplyOFNToShellDialog](#applyofntoshelldialog)と[CFileDialog::UpdateOFNFromShellDialog](#updateofnfromshelldialog)の同期の詳細については、`m_ofn`構造および`CFileDialog`下にある状態[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]します。  
  
 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]スタイルのファイル ダイアログでは、特定のメンバーとのフラグがサポートされません、`CFileDialog`です。 その結果、この効果はありません。  
  
 サポートされていないメンバーの一覧を次に示します[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]:  
  
- `lpstrCustomFilter`  
  
- `lpstrInitialDir`  
  
- `lCustData`  
  
- `lpfnHook`  
  
- `lpTemplateName`  
  
 次のフラグはサポートされていませんので影響を与えませんを使用する場合、[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]のスタイル`CFileDialog`:  
  
-   OFN_ENABLEHOOK  
  
-   OFN_ENABLEINCLUDENOTIFY  
  
-   OFN_ENABLETEMPLATE  
  
-   OFN_ENABLETEMPLATEHANDLE  
  
-   OFN_EXPLORER  
  
-   OFN_EXTENSIONDIFFERENT  
  
-   OFN_HIDEREADONLY  
  
-   OFN_LONGNAMES - 常に効果的に上で[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
-   OFN_NOLONGNAMES - 常に効果的にオフします。[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
-   OFN_NONETWORKBUTTON - 常に効果的に上で[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
-   OFN_READONLY  
  
-   OFN_SHOWHELP  
  
 この構造体の詳細については、次を参照してください。、 [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namemakeprominenta--cfiledialogmakeprominent"></a><a name="makeprominent"></a>CFileDialog::MakeProminent  
 に比べてコントロールに配置 ダイアログで目立つように他のコントロールにします。  
  
```  
HRESULT MakeProminent(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 コントロールの ID です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonbuttonclickeda--cfiledialogonbuttonclicked"></a><a name="onbuttonclicked"></a>CFileDialog::OnButtonClicked  
 ボタンがクリックされたときに呼び出されます。  
  
```  
virtual void OnButtonClicked(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 ボタンの ID です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameoncheckbuttontoggleda--cfiledialogoncheckbuttontoggled"></a><a name="oncheckbuttontoggled"></a>CFileDialog::OnCheckButtonToggled  
 チェック ボックスがオンまたはオフに呼び出されます。  
  
```  
virtual void OnCheckButtonToggled(
    DWORD dwIDCtl,  
    BOOL bChecked);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 チェック ボックスの ID です。  
  
 `bChecked`  
 Checked または unchecked です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameoncontrolactivatinga--cfiledialogoncontrolactivating"></a><a name="oncontrolactivating"></a>CFileDialog::OnControlActivating  
 コントロールがアクティブになったときに呼び出されます。  
  
```  
virtual void OnControlActivating(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 コントロールの ID です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonfilenamechangea--cfiledialogonfilenamechange"></a><a name="onfilenamechange"></a>CFileDialog::OnFileNameChange  
 このメソッドをオーバーライドして、処理する場合、`WM_NOTIFY``CDN_SELCHANGE`メッセージです。  
  
```  
virtual void OnFileNameChange();
```  
  
### <a name="remarks"></a>コメント  
 システムは、送信、 `CDN_SELCHANGE` 、ユーザーのファイルの一覧で新しいファイルまたはフォルダーを選択する場合に、メッセージ、**開く**または**名前を付けて保存** ダイアログ ボックス。 このメッセージに応答アクションを実行する場合は、このメソッドをオーバーライドします。  
  
 システムは、OFN_EXPLORER フラグをオンにします ダイアログ ボックスが作成された場合にのみ、このメッセージを送信します。 通知の詳細については、次を参照してください。 [CDN_SELCHANGE](http://msdn.microsoft.com/library/windows/desktop/ms646865)します。 OFN_EXPLORER フラグについては、次を参照してください。、 [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839)構造と[開くとダイアログ ボックスとして保存](http://msdn.microsoft.com/library/windows/desktop/ms646960)します。  
  
##  <a name="a-nameonfilenameoka--cfiledialogonfilenameok"></a><a name="onfilenameok"></a>CFileDialog::OnFileNameOK  
 コモン ファイル ダイアログ ボックスに入力したファイル名のカスタム検証を提供する場合にのみ、この関数をオーバーライドします。  
  
```  
virtual BOOL OnFileNameOK();
```  
  
### <a name="return-value"></a>戻り値  
 ファイル名が有効なファイル名ではない場合は 1それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数では、何らかのアプリケーション固有のファイル名を拒否することができます。 通常、フレームワークは、ファイル名の既定の検証を提供し、無効なファイル名を入力した場合は、メッセージ ボックスを表示するために、この関数を使用する必要はありません。  
  
 1 が返されます ダイアログ ボックスが別のファイル名を入力するユーザーに対して表示されません。 ダイアログの手順は、戻り値が 0 の場合、ダイアログ ボックスを破棄します。 0 以外の値の他の値を返し予約されているので使わないでください。  
  
##  <a name="a-nameonfolderchangea--cfiledialogonfolderchange"></a><a name="onfolderchange"></a>CFileDialog::OnFolderChange  
 処理するには、この関数をオーバーライドして、 **WM_NOTIFYCDN_FOLDERCHANGE**メッセージです。  
  
```  
virtual void OnFolderChange();
```  
  
### <a name="remarks"></a>コメント  
 新しいフォルダーを開く または ファイル名を名前を付けて保存 ダイアログ ボックスで開いたときに、通知メッセージが送信されます。  
  
 ダイアログ ボックスが OFN_EXPLORER スタイルで作成された場合にのみ、通知が送信されます。 通知の詳細については、次を参照してください。 [CDN_FOLDERCHANGE](http://msdn.microsoft.com/library/windows/desktop/ms646859)します。 OFN_EXPLORER スタイルの詳細については、次を参照してください。、 [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839)構造と[開くとダイアログ ボックスとして保存](http://msdn.microsoft.com/library/windows/desktop/ms646960)します。  
  
##  <a name="a-nameoninitdonea--cfiledialogoninitdone"></a><a name="oninitdone"></a>CFileDialog::OnInitDone  
 処理するには、この関数をオーバーライドして、`WM_NOTIFY``CDN_INITDONE`メッセージです。  
  
```  
virtual void OnInitDone();
```  
  
### <a name="remarks"></a>コメント  
 システムのコントロールでの配置が完了すると、システムはこの通知メッセージを送信、**開く**または**名前を付けて保存**子 ダイアログ ボックスのコントロールを格納できるようにする ダイアログ ボックス。  
  
 ダイアログ ボックスが OFN_EXPLORER スタイルで作成された場合にのみ、システムはこの送信されます。 通知の詳細については、次を参照してください。 [CDN_INITDONE](http://msdn.microsoft.com/library/windows/desktop/ms646863)します。 OFN_EXPLORER スタイルの詳細については、次を参照してください。、 [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839)構造と[開くとダイアログ ボックスとして保存](http://msdn.microsoft.com/library/windows/desktop/ms646960)します。  
  
> [!NOTE]
> [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]スタイルのファイル ダイアログは、この関数をサポートしていません。 この関数を使用すると、[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]スタイル ファイル ダイアログがスローされます[行わない](../../mfc/reference/cnotsupportedexception-class.md)します。 
  
##  <a name="a-nameonitemselecteda--cfiledialogonitemselected"></a><a name="onitemselected"></a>CFileDialog::OnItemSelected  
 コンテナー アイテムが選択されているときに呼び出されます。  
  
```  
virtual void OnItemSelected(
    DWORD dwIDCtl,  
    DWORD dwIDItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 コンテナー コントロールの ID。  
  
 `dwIDItem`  
 項目の ID です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonlbselchangednotifya--cfiledialogonlbselchangednotify"></a><a name="onlbselchangednotify"></a>CFileDialog::OnLBSelChangedNotify  
 この関数は、リスト ボックスの現在の選択が変更されるたびに呼び出されます。  
  
```  
virtual void OnLBSelChangedNotify(
    UINT nIDBox,  
    UINT iCurSel,  
    UINT nCode);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIDBox*  
 リスト ボックスまたはコンボ ボックスの選択範囲が発生したの ID。  
  
 `iCurSel`  
 現在の選択範囲のインデックス。  
  
 `nCode`  
 コントロール通知のコードです。 このパラメーターは、次の値のいずれかが必要です。  
  
- **CD_LBSELCHANGE**指定`iCurSel`単一選択リスト ボックスで選択された項目。  
  
- **CD_LBSELSUB**ことを指定`iCurSel`複数選択のリスト ボックスで選択を解除します。  
  
- **CD_LBSELADD**ことを指定`iCurSel`複数選択のリスト ボックスで選択されています。  
  
- **CD_LBSELNOITEMS**複数選択のリスト ボックスで選択が存在しないことを指定します。  
  
### <a name="remarks"></a>コメント  
 リスト ボックスで選択範囲の変更のカスタム処理を指定するには、この関数をオーバーライドします。 この関数を使用するにはアクセス権を表示するなど、日の最終更新の各ファイルのユーザーを選択します。  
  
##  <a name="a-nameonshareviolationa--cfiledialogonshareviolation"></a><a name="onshareviolation"></a>CFileDialog::OnShareViolation  
 共有違反のカスタム処理を指定するには、この関数をオーバーライドします。  
  
```  
virtual UINT OnShareViolation(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszPathName`  
 共有違反が発生したファイルのパス。  
  
### <a name="return-value"></a>戻り値  
 次のいずれかの値です。  
  
- **OFN_SHAREFALLTHROUGH**  ダイアログ ボックスから、ファイル名が返されます。  
  
- **OFN_SHARENOWARN**これ以上の操作を実行する必要はありません。  
  
- **OFN_SHAREWARN**このエラーの標準的な警告メッセージが表示されます。  
  
### <a name="remarks"></a>コメント  
 通常、フレームワークが既定の共有違反のチェックを提供し、共有違反が発生した場合は、メッセージ ボックスを表示するために、この関数を使用する必要はありません。  
  
 共有違反チェックを無効にする場合は、ビットごとの OR 演算子を使用して、フラグを結合する**OFN_SHAREAWARE**と`m_ofn.Flags`です。  
  
##  <a name="a-nameontypechangea--cfiledialogontypechange"></a><a name="ontypechange"></a>CFileDialog::OnTypeChange  
 処理するには、この関数をオーバーライドして、 **WM_NOTIFYCDN_TYPECHANGE**メッセージです。  
  
```  
virtual void OnTypeChange();
```  
  
### <a name="remarks"></a>コメント  
 新しいファイルの種類の一覧から、開いているファイルの種類のまたは名前を付けて保存 ダイアログ ボックスを選択すると、通知メッセージが送信されます。  
  
 ダイアログ ボックスが OFN_EXPLORER スタイルで作成された場合にのみ、通知が送信されます。 通知の詳細については、次を参照してください。 [CDN_TYPECHANGE](http://msdn.microsoft.com/library/windows/desktop/ms646868)します。 OFN_EXPLORER スタイルの詳細については、次を参照してください。、 [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839)構造と[開くとダイアログ ボックスとして保存](http://msdn.microsoft.com/library/windows/desktop/ms646960)します。  
  
##  <a name="a-nameremovecontrolitema--cfiledialogremovecontrolitem"></a><a name="removecontrolitem"></a>CFileDialog::RemoveControlItem  
 コンテナー コントロール ダイアログ ボックスから項目を削除します。  
  
```  
HRESULT RemoveControlItem(
    DWORD dwIDCtl,  
    DWORD dwIDItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 項目を削除するコンテナー コントロールの ID。  
  
 `dwIDItem`  
 項目の ID です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetcheckbuttonstatea--cfiledialogsetcheckbuttonstate"></a><a name="setcheckbuttonstate"></a>CFileDialog::SetCheckButtonState  
 ダイアログ ボックスで、チェック ボタン (チェック ボックス) の現在の状態を設定します。  
  
```  
HRESULT SetCheckButtonState(
    DWORD dwIDCtl,  
    BOOL bChecked);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 チェック ボックスの ID です。  
  
 `bChecked`  
 チェック ボックスの状態。 `TRUE`checked; を示します`FALSE`オフにした場合を示します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetcontrolitemstatea--cfiledialogsetcontrolitemstate"></a><a name="setcontrolitemstate"></a>CFileDialog::SetControlItemState  
 ダイアログ ボックスであるコンテナー コントロールの項目の現在の状態を設定します。  
  
```  
HRESULT SetControlItemState(
    DWORD dwIDCtl,  
    DWORD dwIDItem,  
    CDCONTROLSTATEF dwState);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 コンテナー コントロールの ID。  
  
 `dwIDItem`  
 項目の ID です。  
  
 `dwState`  
 1 つまたは複数値 CDCONTROLSTATE 列挙体から、コントロールの新しい状態を示します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetcontrolitemtexta--cfiledialogsetcontrolitemtext"></a><a name="setcontrolitemtext"></a>CFileDialog::SetControlItemText  
 コントロールの項目のテキストを設定します。 たとえば、ラジオ ボタンまたはメニュー内の項目に付随するテキストです。  
  
```  
HRESULT SetControlItemText(
    DWORD dwIDCtl,  
    DWORD dwIDItem,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 コンテナー コントロールの ID。  
  
 `dwIDItem`  
 項目の ID です。  
  
 `strLabel`  
 項目のテキスト。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetcontrollabela--cfiledialogsetcontrollabel"></a><a name="setcontrollabel"></a>CFileDialog::SetControlLabel  
 ボタンのテキストまたはエディット ボックスのラベルなどのコントロールに関連付けられているテキストを設定します。  
  
```  
HRESULT SetControlLabel(
    DWORD dwIDCtl,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 コントロールの ID です。  
  
 `strLabel`  
 コントロールの名前。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetcontrolstatea--cfiledialogsetcontrolstate"></a><a name="setcontrolstate"></a>CFileDialog::SetControlState  
 現在の可視性を設定し、特定のコントロールの状態を有効にします。  
  
```  
HRESULT SetControlState(
    DWORD dwIDCtl,  
    CDCONTROLSTATEF dwState);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 コントロールの ID です。  
  
 `dwState`  
 1 つまたは複数の値 CDCONTROLSTATE 列挙体からコントロールの現在の状態を示します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetcontroltexta--cfiledialogsetcontroltext"></a><a name="setcontroltext"></a>CFileDialog::SetControlText  
 エクスプ ローラー スタイルで指定したコントロールのテキストを設定するには、このメソッドを呼び出す**開く**または**名前を付けて保存** ダイアログ ボックス。  
  
```  
void SetControlText(
    int nID,  
    LPCSTR lpsz);

 
void SetControlText(
    int nID,  
    const wchar_t *lpsz);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 テキストを設定する対象のコントロールの ID です。  
  
 [入力] `lpsz`  
 コントロールに対して設定するテキストを含む文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 この関数の両方のバージョンでは、Unicode を使用するアプリケーションに対して有効です。 ただし、LPCSTR 型のバージョンのみが正しく使用するアプリケーションの[!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)]です。  
  
 このメソッドを使用するには、OFN_EXPLORER スタイルでダイアログ ボックスを作成する必要があります。 それ以外の場合、関数は、アサーションは失敗します。  
  
##  <a name="a-namesetdefexta--cfiledialogsetdefext"></a><a name="setdefext"></a>CFileDialog::SetDefExt  
 エクスプ ローラー スタイルのオープンまたは名前を付けて保存コモン ダイアログ ボックスで既定のファイル名拡張子を設定するには、この関数を呼び出します。  
  
```  
void SetDefExt(LPCSTR lpsz);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpsz`  
 ダイアログ ボックスのオブジェクトを使用する既定の拡張子を含む文字列へのポインター。 この文字列は、ピリオド (.) を含めることはできません。  
  
### <a name="remarks"></a>コメント  
 ダイアログ ボックスが作成されている必要があります、 **OFN_EXPLORER**スタイル。 それ以外の場合、関数は、アサーションに失敗します。  
  
##  <a name="a-nameseteditboxtexta--cfiledialogseteditboxtext"></a><a name="seteditboxtext"></a>CFileDialog::SetEditBoxText  
 編集ボックス コントロールで現在のテキストを設定します。  
  
```  
HRESULT SetEditBoxText(
    DWORD dwIDCtl,  
    const CString& strText);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 編集ボックスの ID です。  
  
 `strText`  
 テキスト値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetpropertiesa--cfiledialogsetproperties"></a><a name="setproperties"></a>CFileDialog::SetProperties  
 保存される項目に対して使用される既定値を定義するプロパティ ストアを提供します。  
  
```  
BOOL SetProperties(LPCWSTR lpszPropList);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszPropList`  
 ";" で区切られた定義済みプロパティのリスト。 フラグの一覧は、次を参照してください。、`Flags`の[OPENFILENAME](http://msdn.microsoft.com/en-us/8cecfd45-f7c1-4f8d-81a0-4e7fecc3b104)します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetselectedcontrolitema--cfiledialogsetselectedcontrolitem"></a><a name="setselectedcontrolitem"></a>CFileDialog::SetSelectedControlItem  
 オプション ボタン グループ、またはダイアログ ボックスで、特定の項目の選択状態を設定します。  
  
```  
HRESULT SetSelectedControlItem(
    DWORD dwIDCtl,  
    DWORD dwIDItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 コンテナー コントロールの ID。  
  
 `dwIDItem`  
 ユーザーがコントロールで選択した項目の ID。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesettemplatea--cfiledialogsettemplate"></a><a name="settemplate"></a>CFileDialog::SetTemplate  
 ダイアログ ボックスのテンプレートの設定、 [CFileDialog](../../mfc/reference/cfiledialog-class.md)オブジェクトです。  
  
```  
void SetTemplate(
    UINT nWin3ID,  
    UINT nWin4ID);

 
void SetTemplate(
    LPCTSTR lpWin3ID,  
    LPCTSTR lpWin4ID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nWin3ID`  
 非エクスプ ローラーのテンプレート リソースの ID 番号を含む`CFileDialog`オブジェクトです。 このテンプレートは Windows NT 3.51 または OFN_EXPLORER スタイルが存在しない場合にのみ使用されます。  
  
 [入力] `nWin4ID`  
 エクスプ ローラーのテンプレート リソースの ID 番号を含む`CFileDialog`オブジェクトです。 このテンプレートはのみで使用される[!INCLUDE[WinNt4Family](../../mfc/reference/includes/winnt4family_md.md)]とそれ以降のバージョン、Windows 95 および以降のバージョンで OFN_EXPLORER スタイルが存在する場合、またはです。  
  
 [入力] `lpWin3ID`  
 非エクスプ ローラーのテンプレート リソースの名前を含む`CFileDialog`オブジェクトです。 このテンプレートは Windows NT 3.51 または OFN_EXPLORER スタイルが存在しない場合にのみ使用されます。  
  
 [入力] `lpWin4ID`  
 エクスプ ローラーのテンプレート リソースの名前を含む`CFileDialog`オブジェクトです。 このテンプレートはのみで使用される[!INCLUDE[WinNt4Family](../../mfc/reference/includes/winnt4family_md.md)]とそれ以降のバージョン、Windows 95 および以降のバージョンで OFN_EXPLORER スタイルが存在する場合、またはです。  
  
### <a name="remarks"></a>コメント  
 指定されたテンプレートの&1; つだけが使用されます。 システムでは、OFN_EXPLORER スタイルと、アプリケーションが実行されているオペレーティング システムの存在に基づいて、使用するテンプレートを決定します。 非 Explorer とエクスプ ローラー スタイルのテンプレートの両方を指定するは簡単にサポート Windows NT 3.51[!INCLUDE[WinNt4Family](../../mfc/reference/includes/winnt4family_md.md)]とのそれ以降のバージョンと Windows 95 およびそれ以降のバージョン。  
  
> [!NOTE]
> [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]ファイル ダイアログ ボックスのスタイルは、この関数をサポートしていません。 この関数を使用すると、[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]スタイル ファイル ダイアログ ボックスがスローされます[行わない](../../mfc/reference/cnotsupportedexception-class.md)します。 別の方法では、カスタマイズされたダイアログを使用します。 詳細については、カスタムの`CFileDialog`を参照してください[IFileDialogCustomize](http://msdn.microsoft.com/library/windows/desktop/bb775912)します。  
  
##  <a name="a-namestartvisualgroupa--cfiledialogstartvisualgroup"></a><a name="startvisualgroup"></a>CFileDialog::StartVisualGroup  
 ダイアログ ボックスでグループを宣言します。 以降、"add"メソッドを呼び出すは、それらの要素をこのグループに追加します。  
  
```  
HRESULT StartVisualGroup(
    DWORD dwIDCtl,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwIDCtl`  
 ビジュアルのグループの ID です。  
  
 `strLabel`  
 グループの名前。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameupdateofnfromshelldialoga--cfiledialogupdateofnfromshelldialog"></a><a name="updateofnfromshelldialog"></a>CFileDialog::UpdateOFNFromShellDialog  
 更新プログラム、`m_ofn`のデータ構造、 [CFileDialog](../../mfc/reference/cfiledialog-class.md)内部オブジェクトの現在の状態に基づいています。  
  
```  
void UpdateOFNFromShellDialog();
```  
  
### <a name="remarks"></a>コメント  
 前に Windows のバージョンで[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]、メンバー [OPENFILENAME](https://msdn.microsoft.com/library/ms911906.aspx)の状態と、このデータ構造を常に同期、`CFileDialog`です。 変更、 [m_ofn](#m_ofn)メンバー変数 ダイアログ ボックスの状態に直接影響します。 また、ダイアログの状態への変更はすぐに m_ofn メンバー変数を更新します。  
  
 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]、`m_ofn`データ構造が自動的に更新されません。 内のデータの精度を保証するために、`m_ofn`メンバー変数を呼び出す必要があります、`UpdateOFNFromShellDialog`データにアクセスする前に関数です。 Windows からこの関数が自動的に処理中に[IFileDialog::OnFileOK](http://msdn.microsoft.com/library/windows/desktop/bb775879)します。  
  
 使用する方法の詳細についての`CFileDialog`クラスの下にある[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]を参照してください[CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)します。  
  
### <a name="example"></a>例  
 この例では更新、`CFileDialog`表示する前にします。 更新する前に、`m_ofn`メンバー変数 ダイアログ ボックスの現在の状態を同期する必要があります。  
  
 [!code-cpp[NVC_MFC_CFileDialog&#1;](../../mfc/reference/codesnippet/cpp/cfiledialog-class_7.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CCommonDialog クラス](../../mfc/reference/ccommondialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)


