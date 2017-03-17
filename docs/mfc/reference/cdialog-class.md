---
title: "CDialog クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDialog
- AFXWIN/CDialog
- AFXWIN/CDialog::CDialog
- AFXWIN/CDialog::Create
- AFXWIN/CDialog::CreateIndirect
- AFXWIN/CDialog::DoModal
- AFXWIN/CDialog::EndDialog
- AFXWIN/CDialog::GetDefID
- AFXWIN/CDialog::GotoDlgCtrl
- AFXWIN/CDialog::InitModalIndirect
- AFXWIN/CDialog::MapDialogRect
- AFXWIN/CDialog::NextDlgCtrl
- AFXWIN/CDialog::OnInitDialog
- AFXWIN/CDialog::OnSetFont
- AFXWIN/CDialog::PrevDlgCtrl
- AFXWIN/CDialog::SetDefID
- AFXWIN/CDialog::SetHelpID
- AFXWIN/CDialog::OnCancel
- AFXWIN/CDialog::OnOK
dev_langs:
- C++
helpviewer_keywords:
- modal dialog boxes, creating
- MFC dialog boxes, base class
- modeless dialog boxes, creating
- modeless dialog boxes, displaying
- CDialog class
ms.assetid: ca64b77e-2cd2-47e3-8eff-c2645ad578f9
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
ms.openlocfilehash: 0944d815e8aca591f2a09c09af60fa591a9b1a6d
ms.lasthandoff: 02/24/2017

---
# <a name="cdialog-class"></a>CDialog クラス
画面上のダイアログ ボックスを表示するための基本クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CDialog : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[詳細](#cdialog)|`CDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDialog::Create](#create)|初期化、`CDialog`オブジェクトです。 モードレス ダイアログ ボックスを作成し、それをアタッチ、`CDialog`オブジェクトです。|  
|[CDialog::CreateIndirect](#createindirect)|(ないリソースに基づく) のメモリ内のダイアログ ボックスのテンプレートからモードレス ダイアログ ボックスを作成します。|  
|[CDialog::DoModal](#domodal)|モーダル ダイアログ ボックスの呼び出しを完了を返します。|  
|[CDialog::EndDialog](#enddialog)|モーダル ダイアログ ボックスを閉じます。|  
|[CDialog::GetDefID](#getdefid)|ダイアログ ボックスの既定のプッシュ ボタン コントロールの ID を取得します。|  
|[CDialog::GotoDlgCtrl](#gotodlgctrl)|ダイアログ ボックス内の指定 ダイアログ ボックス コントロールにフォーカスを移動します。|  
|[CDialog::InitModalIndirect](#initmodalindirect)|(ないリソースに基づく) のメモリ上のダイアログ ボックスのテンプレートからモーダル ダイアログ ボックスを作成します。 パラメーターを保存するまで関数`DoModal`が呼び出されます。|  
|[CDialog::MapDialogRect](#mapdialogrect)|四角形のダイアログ ボックスの単位を画面単位に変換します。|  
|[CDialog::NextDlgCtrl](#nextdlgctrl)|ダイアログ ボックスで、次のダイアログ ボックス コントロールにフォーカスを移動します。|  
|[CDialog::OnInitDialog](#oninitdialog)|オーバーライドすると、ダイアログ ボックスの初期化を強化します。|  
|[CDialog::OnSetFont](#onsetfont)|ダイアログ ボックス コントロールがテキストを描画するときを使用するフォントを指定するためにオーバーライドします。|  
|[CDialog::PrevDlgCtrl](#prevdlgctrl)|ダイアログ ボックスで、前のダイアログ ボックス コントロールにフォーカスを移動します。|  
|[CDialog::SetDefID](#setdefid)|指定したプッシュする ダイアログ ボックスの既定のプッシュ ボタン コントロールを変更します。|  
|[CDialog::SetHelpID](#sethelpid)|ダイアログ ボックスの状況依存のヘルプ ID を設定します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDialog::OnCancel](#oncancel)|[キャンセル] ボタンまたは ESC キーの動作を実行するためにオーバーライドします。 既定値は、ダイアログ ボックスを閉じ、 **DoModal**返します**IDCANCEL**します。|  
|[CDialog::OnOK](#onok)|モーダル ダイアログ ボックスで [ok] ボタンの操作を実行するためにオーバーライドします。 既定値は、ダイアログ ボックスを閉じ、`DoModal`返します**IDOK**します。|  
  
## <a name="remarks"></a>コメント  
 ダイアログ ボックスの&2; つの型である: モーダルとモードレスです。 アプリケーションを続行する前に、ユーザーが、モーダル ダイアログ ボックスを閉じる必要があります。 モードレス ダイアログ ボックスは、ダイアログ ボックスが表示され、キャンセルまたはダイアログ ボックスを削除せずに別のタスクに戻ることができます。  
  
 A`CDialog`オブジェクトは、ダイアログ テンプレートの組み合わせと`CDialog`-クラスを派生します。 ダイアログ テンプレートを作成し、リソースに保存するダイアログ エディターを使用してから派生したクラスを作成するクラスの追加ウィザードを使用して`CDialog`します。  
  
 その他のウィンドウのように、ダイアログ ボックスでは、Windows からメッセージを受信します。 ダイアログ ボックスでは、ユーザーがダイアログ ボックスと対話する方法では、ダイアログ ボックスのコントロールからの通知メッセージを処理、特に興味のあります。 [プロパティ] ウィンドウを使用すると、処理するメッセージは、適切なメッセージ マップ エントリとメッセージ ハンドラーのメンバー関数をクラスに追加するかを選択できます。 ハンドラーのメンバー関数でアプリケーションに固有のコードを記述する必要があるだけです。  
  
 場合は、常に記述できますとメンバー関数のメッセージ マップ エントリを手動で。  
  
 最も単純なダイアログ ボックス以外はすべて、ユーザーがダイアログ ボックスのコントロールに入力されたデータを格納する、またはユーザーのデータを表示するダイアログの派生クラスにメンバー変数を追加します。 メンバー変数を作成し、コントロールに関連付けるには、変数の追加ウィザードを使用できます。 同時には、変数の型と各変数の値の許容範囲を選択します。 コード ウィザードでは、派生ダイアログ クラスにメンバー変数を追加します。  
  
 メンバー変数と、ダイアログ ボックスのコントロール間のデータ交換を自動的に処理するには、データ マップが生成されます。 データ マップは、適切な値 ダイアログ ボックスでコントロールを初期化し、データを取得し、データを検証する関数を提供します。  
  
 モーダル ダイアログ ボックスを作成する派生ダイアログ クラスのコンス トラクターを使用して、スタック上のオブジェクトを構築し、し、呼び出す`DoModal`ダイアログ ウィンドウとそのコントロールを作成します。 モードレス ダイアログを作成する場合は、呼び出す**作成**ダイアログ クラスのコンス トラクターです。  
  
 使用して、メモリ内でテンプレートを作成することも、 [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394)データ構造」の説明に従って、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 構築した後、`CDialog`オブジェクトで呼び出す[CreateIndirect](#createindirect) 、モードレスを作成するダイアログ ボックスで、または呼び出し[持たない](#initmodalindirect)と[DoModal](#domodal)モーダル ダイアログ ボックスを作成します。  
  
 オーバーライドで、exchange と検証のデータ マップが書き込まれる`CWnd::DoDataExchange`新しいダイアログ クラスに追加されています。 参照してください、 [DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange)のメンバー関数内`CWnd`の詳細については、exchange と検証の機能です。  
  
 プログラマとフレームワークの呼び出しの両方`DoDataExchange`への呼び出しを通じて間接的に[:updatedata](../../mfc/reference/cwnd-class.md#updatedata)します。  
  
 Framework 呼び出し`UpdateData`ユーザーがモーダル ダイアログ ボックスを閉じる [ok] ボタンをクリックするとします。 (データは取得されません、[キャンセル] ボタンがクリックされた場合。)既定の実装[OnInitDialog](#oninitdialog)も呼び出して`UpdateData`コントロールの初期値を設定します。 通常、オーバーライドする`OnInitDialog`をさらにコントロールを初期化します。 `OnInitDialog`すべてのダイアログ コントロールを作成し、直前に、ダイアログ ボックスが表示されますが呼び出されます。  
  
 呼び出すことができます`CWnd::UpdateData`モーダルまたはモードレスのダイアログ ボックスの実行中にいつでもできます。  
  
 ダイアログ ボックスを手動で開発する場合、自分でダイアログ ボックスの派生クラスに必要なメンバー変数を追加して、設定またはこれらの値を取得するメンバー関数を追加します。  
  
 ユーザーが [ok] または [キャンセル] ボタンを押したときや、コードを呼び出したときに、モーダル ダイアログ ボックスが自動的に閉じます、`EndDialog`メンバー関数。  
  
 モードレス ダイアログ ボックスを実装するときに常にオーバーライド、`OnCancel`メンバー関数と呼び出し`DestroyWindow`から内部にします。 基本クラスを呼び出しません`CDialog::OnCancel`を呼び出すので、 `EndDialog`、ダイアログ ボックスを非表示にするは破棄されます。 またをオーバーライドする必要があります`PostNcDestroy`を削除するのにはモードレス ダイアログ ボックスの**この**モードレス ダイアログ ボックスに通常割り当てられているため、**新しい**します。 モーダル ダイアログ ボックスは、通常、フレーム上に構築され、必要はありません`PostNcDestroy`クリーンアップします。  
  
 `CDialog` の詳細については、次を参照してください。  
  
- [ダイアログ ボックス](../../mfc/dialog-boxes.md)  
  
-   サポート技術情報記事 Q262954: HOWTO: スクロール バーのサイズ ダイアログ ボックスの作成  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cdialog"></a>詳細  
 リソース ベースのモーダル ダイアログ ボックスを作成するには、どちらのパブリック コンス トラクターの形式を呼び出します。  
  
```  
explicit CDialog(
    LPCTSTR lpszTemplateName,  
    CWnd* pParentWnd = NULL);

 
explicit CDialog(
    UINT nIDTemplate,  
    CWnd* pParentWnd = NULL);  
  
CDialog();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszTemplateName`  
 ダイアログ テンプレート リソースの名前を指定する null で終わる文字列が含まれています。  
  
 `nIDTemplate`  
 ダイアログ テンプレート リソースの ID 番号が含まれています。  
  
 `pParentWnd`  
 親またはオーナー ウィンドウのオブジェクトを指します (型の[CWnd](../../mfc/reference/cwnd-class.md)) ダイアログ オブジェクトが属しています。 ある場合**NULL**、ダイアログ オブジェクトの親ウィンドウがアプリケーションのメイン ウィンドウに設定します。  
  
### <a name="remarks"></a>コメント  
 コンス トラクターの&1; つのフォームは、テンプレート名で、ダイアログ リソースへのアクセスを提供します。 その他のコンス トラクターへのアクセス提供テンプレートの ID 番号、通常、 **idd _**プレフィックス (IDD_DIALOG1 など)。  
  
 メモリ内のテンプレートからモーダル ダイアログ ボックスを構築するには、最初に、パラメーターなしで保護されているコンス トラクターを呼び出すし、呼び出す`InitModalIndirect`します。  
  
 上記のメソッドのいずれかで、モーダル ダイアログ ボックスを構築した後で呼び出す`DoModal`します。  
  
 モードレス ダイアログ ボックスを作成するには、保護対象のフォームを使用して、`CDialog`コンス トラクターです。 モードレス ダイアログ ボックスを実装する独自のダイアログ ボックス クラスを派生させる必要がありますので、コンス トラクターは保護されています。 モードレス ダイアログ ボックスの構築は、2 段階のプロセスです。 コンス トラクターの最初の呼び出し物書き、**作成**リソース ベースのダイアログ ボックスを作成するメンバー関数を呼び出したり`CreateIndirect`メモリ上のテンプレートから、ダイアログ ボックスを作成します。  
  
##  <a name="create"></a>CDialog::Create  
 呼び出す**作成**リソースからダイアログ ボックス テンプレートを使用して、モードレス ダイアログ ボックスを作成します。  
  
```  
virtual BOOL Create(
    LPCTSTR lpszTemplateName,  
    CWnd* pParentWnd = NULL);

 
virtual BOOL Create(
    UINT nIDTemplate,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszTemplateName`  
 ダイアログ テンプレート リソースの名前を指定する null で終わる文字列が含まれています。  
  
 `pParentWnd`  
 親ウィンドウのオブジェクトを指します (型の[CWnd](../../mfc/reference/cwnd-class.md)) ダイアログ オブジェクトが属しています。 ある場合**NULL**、ダイアログ オブジェクトの親ウィンドウがアプリケーションのメイン ウィンドウに設定します。  
  
 `nIDTemplate`  
 ダイアログ テンプレート リソースの ID 番号が含まれています。  
  
### <a name="return-value"></a>戻り値  
 どちらの形式 ダイアログ ボックスの作成と初期化が成功した場合は 0 以外を返しますそれ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出しを配置する**作成**コンス トラクターの呼び出し内部コンス トラクターには、呼び出されます。  
  
 2 つの形式、**作成**メンバー関数は、ダイアログ ボックスのテンプレート リソースにアクセスするため、テンプレート名またはテンプレート ID 番号 (IDD_DIALOG1 など) によって提供されます。  
  
 いずれの形式には、親ウィンドウ オブジェクトへのポインターを渡します。 場合`pParentWnd`は**NULL**、その親ウィンドウまたはオーナー ウィンドウにアプリケーションのメイン ウィンドウ設定で、ダイアログ ボックスが作成されます。  
  
 **作成** ダイアログ ボックスを作成した後すぐに、メンバー関数が返されます。  
  
 使用して、 **WS_VISIBLE**  ダイアログ ボックスのテンプレートのスタイルの場合は、親ウィンドウの作成時にダイアログ ボックスが表示されます。 それ以外の場合、呼び出す必要があります`ShowWindow`します。 さらにダイアログ ボックスのスタイルと、アプリケーションでは、「、 [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]と[ウィンドウ スタイル](../../mfc/reference/window-styles.md)で、 *『 MFC リファレンス*します。  
  
 使用して、`CWnd::DestroyWindow`によって作成されたダイアログ ボックスを破棄する関数、**作成**関数です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog #&62;](../../mfc/codesnippet/cpp/cdialog-class_1.cpp)]  
  
##  <a name="createindirect"></a>CDialog::CreateIndirect  
 メモリ内のダイアログ ボックスのテンプレートからモードレス ダイアログ ボックスを作成するには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL CreateIndirect(
    LPCDLGTEMPLATE lpDialogTemplate,  
    CWnd* pParentWnd = NULL,  
    void* lpDialogInit = NULL);

 
virtual BOOL CreateIndirect(
    HGLOBAL hDialogTemplate,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpDialogTemplate`  
 ダイアログ ボックスを作成するために使用する ダイアログ ボックス テンプレートが含まれるメモリへのポインター。 このテンプレートは、の形式で、 [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394)構造とコントロールについて、」の説明に従って、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `pParentWnd`  
 ダイアログ オブジェクトの親ウィンドウのオブジェクトを指す (型の[CWnd](../../mfc/reference/cwnd-class.md))。 ある場合**NULL**、ダイアログ オブジェクトの親ウィンドウがアプリケーションのメイン ウィンドウに設定します。  
  
 `lpDialogInit`  
 指す、 **DLGINIT**リソースです。  
  
 `hDialogTemplate`  
 ダイアログ ボックスのテンプレートを含むグローバル メモリへのハンドルが含まれています。 このテンプレートは、の形式で、 **DLGTEMPLATE**構造と、ダイアログ ボックスの各コントロールに対してデータ。  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスが作成され、正常に初期化される場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `CreateIndirect`  ダイアログ ボックスを作成した後すぐに、メンバー関数が返されます。  
  
 使用して、 **WS_VISIBLE**  ダイアログ ボックスのテンプレートのスタイルの場合は、親ウィンドウの作成時にダイアログ ボックスが表示されます。 それ以外の場合、呼び出す必要があります`ShowWindow`表示することです。 テンプレートの他のダイアログ ボックスのスタイルを指定する方法の詳細については、次を参照してください。、 [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 使用して、`CWnd::DestroyWindow`によって作成されたダイアログ ボックスを破棄する関数、`CreateIndirect`関数です。  
  
 ActiveX コントロールを含むダイアログ ボックスで提供される追加情報を必要とする**DLGINIT**リソースです。 詳細については、サポート技術情報記事 Q231591 を参照してください"HOWTO: ActiveX コントロールと MFC ダイアログを作成するダイアログ テンプレートを使用します。"。 サポート技術情報の記事は、MSDN ライブラリの Visual Studio のドキュメントで使用可能な[http://support.microsoft.com](http://support.microsoft.com/)します。  
  
##  <a name="domodal"></a>CDialog::DoModal  
 モーダル ダイアログ ボックスを起動し、[完了] ダイアログ ボックスの結果を返すには、このメンバー関数を呼び出します。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 `int`の値を指定する値、`nResult`に渡されたパラメーター、 [CDialog::EndDialog](#enddialog)メンバー関数は、ダイアログ ボックスを閉じるために使用します。 関数は、ダイアログ ボックスを作成できなかった場合、戻り値は –&1; または**IDABORT**その他のエラーが発生した場合に、出力ウィンドウはエラー情報が格納から[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、ダイアログ ボックスがアクティブなときに、ユーザーとすべての対話を処理します。 これは、こそが、ダイアログ ボックスをモーダルになります。つまり、ユーザーは、ダイアログ ボックスが閉じられるまで、他のウィンドウを操作できません。  
  
 ユーザーがクリックするとダイアログ ボックスで、[ok] または [キャンセル] メッセージ ハンドラーのメンバー関数などのプッシュ ボタンのいずれかのよう[OnOK](#onok)または[OnCancel](#oncancel)、ダイアログ ボックスを閉じますしようとすると呼びます。 既定値`OnOK`メンバー関数は検証 ダイアログ ボックスのデータおよび更新結果を使用 ダイアログ ボックスを閉じます**IDOK**、および既定の`OnCancel`メンバー関数は、ダイアログ ボックスを閉じます結果と共に**IDCANCEL**検証またはダイアログ ボックスのデータを更新せずします。 これらのメッセージ ハンドラー関数の動作を変更するのにはオーバーライドできます。  
  
> [!NOTE]
> `PreTranslateMessage`モーダル ダイアログ ボックスのメッセージの処理と呼ばれます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog #&63;](../../mfc/codesnippet/cpp/cdialog-class_2.cpp)]  
  
##  <a name="enddialog"></a>CDialog::EndDialog  
 モーダル ダイアログ ボックスを終了するには、このメンバー関数を呼び出します。  
  
```  
void EndDialog(int nResult);
```  
  
### <a name="parameters"></a>パラメーター  
 `nResult`  
 ダイアログ ボックスからの呼び出し元に返される値を含む`DoModal`します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数が返す`nResult`の戻り値として`DoModal`します。 使用する必要があります、`EndDialog`関数が、モーダル ダイアログ ボックスが作成されるたびに処理を完了します。  
  
 呼び出すことができます`EndDialog`であっても、いつでも[OnInitDialog](#oninitdialog)、前に、ダイアログ ボックスが表示される閉じる必要がある場合にまたは前に入力フォーカスを設定します。  
  
 `EndDialog`ダイアログ ボックスをすぐに閉じません。 代わりに、ダイアログ ボックスを現在のメッセージ ハンドラーによって返されるとすぐに終了するように指示するフラグを設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog #&64;](../../mfc/codesnippet/cpp/cdialog-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCControlLadenDialog #&65;](../../mfc/codesnippet/cpp/cdialog-class_4.cpp)]  
  
##  <a name="getdefid"></a>CDialog::GetDefID  
 呼び出す、 `GetDefID`  ダイアログ ボックスの既定のプッシュ ボタン コントロールの ID を取得します。  
  
```  
DWORD GetDefID() const;  
```  
  
### <a name="return-value"></a>戻り値  
 32 ビット値 ( `DWORD`)。 上位の単語に含まれる既定のプッシュ ボタンに ID 値がある場合は、 **DC_HASDEFID**下位ワードに ID 値が含まれています。 既定のプッシュ ボタンが ID 値を持たない場合、戻り値は 0 です。  
  
### <a name="remarks"></a>コメント  
 これは、通常、[ok] ボタンです。  
  
##  <a name="gotodlgctrl"></a>CDialog::GotoDlgCtrl  
 ダイアログ ボックスで指定したコントロールにフォーカスを移動します。  
  
```  
void GotoDlgCtrl(CWnd* pWndCtrl);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWndCtrl`  
 フォーカスを受け取るには、ウィンドウ (コントロール) を識別します。  
  
### <a name="remarks"></a>コメント  
 コントロールとして渡す (子ウィンドウ) にポインターを取得する`pWndCtrl`を呼び出す、`CWnd::GetDlgItem`へのポインターを返すメンバー関数、 [CWnd](../../mfc/reference/cwnd-class.md)オブジェクトです。  
  
### <a name="example"></a>例  
  例を参照してください[:getdlgitem](../../mfc/reference/cwnd-class.md#getdlgitem)します。  
  
##  <a name="initmodalindirect"></a>CDialog::InitModalIndirect  
 このメンバー関数を呼び出してメモリ上に作成 ダイアログ ボックス テンプレートを使用してモーダル ダイアログ オブジェクトを初期化します。  
  
```  
BOOL InitModalIndirect(
    LPCDLGTEMPLATE lpDialogTemplate,  
    CWnd* pParentWnd = NULL,  
    void* lpDialogInit = NULL);

 
    BOOL InitModalIndirect(
    HGLOBAL hDialogTemplate,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpDialogTemplate`  
 ダイアログ ボックスを作成するために使用する ダイアログ ボックス テンプレートが含まれるメモリへのポインター。 このテンプレートは、の形式で、 [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394)構造とコントロールについて、」の説明に従って、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `hDialogTemplate`  
 ダイアログ ボックスのテンプレートを含むグローバル メモリへのハンドルが含まれています。 このテンプレートは、の形式で、 **DLGTEMPLATE**構造と、ダイアログ ボックスの各コントロールに対してデータ。  
  
 `pParentWnd`  
 親またはオーナー ウィンドウのオブジェクトを指します (型の[CWnd](../../mfc/reference/cwnd-class.md)) ダイアログ オブジェクトが属しています。 ある場合**NULL**、ダイアログ オブジェクトの親ウィンドウがアプリケーションのメイン ウィンドウに設定します。  
  
 `lpDialogInit`  
 指す、 **DLGINIT**リソースです。  
  
### <a name="return-value"></a>戻り値  
 ダイアログ オブジェクトが作成され、正常に初期化される場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 まず、モーダル ダイアログ ボックスを直接作成するには、グローバル メモリ ブロックを割り当て、 ダイアログ ボックスのテンプレートを使用して入力します。 空を呼び出す`CDialog` ダイアログ ボックス オブジェクトを構築するコンス トラクターです。 次に、`InitModalIndirect`をメモリ内のダイアログ ボックスのテンプレートにハンドルを格納します。 Windows のダイアログ ボックスが作成され、表示されるときに、後で、 [DoModal](#domodal)メンバー関数が呼び出されます。  
  
 ActiveX コントロールを含むダイアログ ボックスで提供される追加情報を必要とする**DLGINIT**リソースです。 詳細については、サポート技術情報記事 Q231591 を参照してください"HOWTO: ActiveX コントロールと MFC ダイアログを作成するダイアログ テンプレートを使用します。"。 サポート技術情報の記事は、MSDN ライブラリの Visual Studio のドキュメントで使用可能な[http://support.microsoft.com](http://support.microsoft.com/)します。  
  
##  <a name="mapdialogrect"></a>CDialog::MapDialogRect  
 四角形のダイアログ ボックスの単位を画面単位に変換する呼び出しです。  
  
```  
void MapDialogRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または[CRect](../../atl-mfc-shared/reference/crect-class.md)  ダイアログ ボックスを含むオブジェクトを変換する座標します。  
  
### <a name="remarks"></a>コメント  
 ダイアログ単位は、平均的な幅とダイアログ ボックスのテキストに使用するフォントの文字の高さから派生した現在のダイアログ ボックス基本単位として。 水平方向の&1; つの単位 ダイアログ ボックスの基本幅の単位の&4; 分の&1;、垂直方向の&1; つの単位 ダイアログ ボックスの高さの基本単位の&8; 分の&1;。  
  
 **GetDialogBaseUnits** Windows 関数は、システム フォントのサイズ情報を返しますが、各ダイアログ ボックスに、別のフォントを指定するには、使用する場合、 **DS_SETFONT**リソース定義ファイル内のスタイル。 `MapDialogRect` Windows の機能は、このダイアログ ボックスの適切なフォントを使用します。  
  
 `MapDialogRect`メンバー関数は、ダイアログ ボックスの単位を置き換えます`lpRect`で画面の [作成] ダイアログ ボックスに、ボックス内のコントロールの位置四角形を使用できるようにする単位 (ピクセル単位)。  
  
##  <a name="nextdlgctrl"></a>CDialog::NextDlgCtrl  
 ダイアログ ボックスで次のコントロールにフォーカスを移動します。  
  
```  
void NextDlgCtrl() const;  
```  
  
### <a name="remarks"></a>コメント  
 ダイアログ ボックスの最後のコントロールにフォーカスがある場合は、最初のコントロールに移動します。  
  
##  <a name="oncancel"></a>CDialog::OnCancel  
 フレームワークが、ユーザーがクリックすると、このメソッドを呼び出します**キャンセル**か、モーダルまたはモードレスのダイアログ ボックスで、ESC キーを押します。  
  
```  
virtual void OnCancel();
```  
  
### <a name="remarks"></a>コメント  
 (古いデータの復元) などの操作を実行するには、このメソッドをオーバーライドして、ユーザーがクリックしてダイアログ ボックスを閉じたときに**キャンセル**か、ESC キーを押すことです。 既定値は、呼び出すことによって、モーダル ダイアログ ボックスを閉じます[EndDialog](#enddialog)とスケジュールの[DoModal](#domodal) IDCANCEL に戻ります。  
  
 実装する場合、**キャンセル**ボタン モードレス ダイアログ ボックスでは、オーバーライドする必要があります、`OnCancel`メソッドを呼び出します[DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow)中です。 呼び出すために基本クラスのメソッドを呼び出す必要はありません`EndDialog`、ダイアログ ボックスを非表示にを破棄することができます。  
  
> [!NOTE]
>  使用する場合は、このメソッドをオーバーライドすることはできません、 `CFileDialog` Windows XP でコンパイルされたプログラム内のオブジェクト。 詳細については`CFileDialog`を参照してください[CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog #&66;](../../mfc/codesnippet/cpp/cdialog-class_5.cpp)]  
  
##  <a name="oninitdialog"></a>CDialog::OnInitDialog  
 応答でこのメソッドは、`WM_INITDIALOG`メッセージです。  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーションがダイアログ ボックスで、コントロールのいずれかに入力フォーカスを設定したかどうかを指定します。 場合`OnInitDialog`戻り値は&0; 以外の値、Windows、入力フォーカスを設定は既定の場所 ダイアログ ボックスの最初のコントロールです。 アプリケーションは、明示的にフォーカスを設定した、入力コントロールのいずれかにダイアログ ボックスで場合にのみ、0 を返します。  
  
### <a name="remarks"></a>コメント  
 Windows の送信、`WM_INITDIALOG`中に、ダイアログ ボックスにメッセージ、[作成](#create)、 [CreateIndirect](#createindirect)、または[DoModal](#domodal)  ダイアログ ボックスが表示される直前に発生する呼び出しです。  
  
 ダイアログ ボックスが初期化されるときに特別な処理を実行する場合は、このメソッドをオーバーライドします。 オーバーライドされたバージョンの基本クラスを呼び出す最初`OnInitDialog`が、その戻り値を無視します。 通常戻ります`TRUE`オーバーライドされたメソッドからです。  
  
 Windows の呼び出し、 `OnInitDialog` Microsoft Foundation Class ライブラリのすべてのダイアログ ボックスに共通の標準的なグローバルのダイアログ ボックス プロシージャを使用することによって機能します。 メッセージ マップを使用して関数を呼び出しません、したがってする必要はありませんメッセージ マップ エントリこのメソッドにします。  
  
> [!NOTE]
>  使用する場合は、このメソッドをオーバーライドすることはできません、`CFileDialog`でコンパイルされたプログラムでオブジェクト[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]します。 変更の詳細については`CFileDialog`[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]を参照してください[CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog #&67;](../../mfc/codesnippet/cpp/cdialog-class_6.cpp)]  
  
##  <a name="onok"></a>CDialog::OnOK  
 ユーザーがクリックしたときに呼び出されます、 **OK** (ID が idok のボタン) ボタンをクリックします。  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>コメント  
 アクションを実行するには、このメソッドをオーバーライドするときに、 **ok**  ボタンがアクティブにします。 ダイアログ ボックスには、データの自動検証と交換が含まれている場合、このメソッドの既定の実装は ダイアログ ボックスのデータを検証し、アプリケーションの適切な変数を更新します。  
  
 実装する場合、 **OK**ボタン モードレス ダイアログ ボックスでは、オーバーライドする必要があります、`OnOK`メソッドを呼び出します[DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow)その内部です。 呼び出すので、基本クラスのメソッドを呼び出さないでください[EndDialog](#enddialog)と非表示に、ダイアログ ボックスは、破棄することができます。  
  
> [!NOTE]
>  使用する場合は、このメソッドをオーバーライドすることはできません、 `CFileDialog` Windows XP でコンパイルされたプログラム内のオブジェクト。 詳細については`CFileDialog`を参照してください[CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog #&68;](../../mfc/codesnippet/cpp/cdialog-class_7.cpp)]  
  
##  <a name="onsetfont"></a>CDialog::OnSetFont  
 テキストを描画するときに、ダイアログ ボックス コントロールを使用するフォントを指定します。  
  
```  
Virtual void OnSetFont(CFont* pFont);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pFont`  
 このダイアログ ボックスのすべてのコントロールの既定のフォントとして使用されるフォントへのポインターを指定します。  
  
### <a name="remarks"></a>コメント  
 ダイアログ ボックスに、すべてのコントロールの既定値として指定したフォントを使用します。  
  
 ダイアログ エディターは、ダイアログ ボックスのテンプレート リソースの一部として一般 ダイアログ ボックスのフォントを設定します。  
  
> [!NOTE]
>  使用する場合は、このメソッドをオーバーライドすることはできません、`CFileDialog`でコンパイルされたプログラムでオブジェクト[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]します。 変更の詳細については`CFileDialog`[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]を参照してください[CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)します。  
  
##  <a name="prevdlgctrl"></a>CDialog::PrevDlgCtrl  
 ダイアログ ボックスで前のコントロールにフォーカスを設定します。  
  
```  
void PrevDlgCtrl() const;  
```  
  
### <a name="remarks"></a>コメント  
 ダイアログ ボックスの最初のコントロールにフォーカスがある場合最後のコントロールに移動します。  
  
##  <a name="setdefid"></a>CDialog::SetDefID  
 ダイアログ ボックスの既定のプッシュ ボタン コントロールを変更します。  
  
```  
void SetDefID(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 既定値になるプッシュ ボタン コントロールの ID を指定します。  
  
##  <a name="sethelpid"></a>CDialog::SetHelpID  
 ダイアログ ボックスの状況依存のヘルプ ID を設定します。  
  
```  
void SetHelpID(UINT nIDR);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIDR*  
 状況依存のヘルプ ID を指定します  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル DLGCBR32](../../visual-cpp-samples.md)   
 [MFC サンプル DLGTEMPL](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)


