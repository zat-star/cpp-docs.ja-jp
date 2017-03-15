---
title: "CPrintDialog クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPrintDialog
dev_langs:
- C++
helpviewer_keywords:
- Print Setup dialog box
- Print dialog box
- CPrintDialog class
ms.assetid: 5bdb2424-adf8-433d-a97c-df11a83bc4e4
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
ms.openlocfilehash: fe8b5a899169bf9dfd463278100384fde900a6a0
ms.lasthandoff: 02/24/2017

---
# <a name="cprintdialog-class"></a>CPrintDialog クラス
Windows のコモン ダイアログ ボックスである [印刷] ダイアログで提供されるサービスをカプセル化したものです。  
  
## <a name="syntax"></a>構文  
  
```  
class CPrintDialog : public CCommonDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CPrintDialog::CPrintDialog](#cprintdialog)|`CPrintDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPrintDialog::CreatePrinterDC](#createprinterdc)|印刷 ダイアログ ボックスを表示することがなくプリンター デバイス コンテキストを作成します。|  
|[CPrintDialog::DoModal](#domodal)|ダイアログ ボックスを表示および選択を行うことができます。|  
|[CPrintDialog::GetCopies](#getcopies)|要求されたコピーの数を取得します。|  
|[CPrintDialog::GetDefaults](#getdefaults)|ダイアログ ボックスを表示せずには、デバイスの既定値を取得します。|  
|[CPrintDialog::GetDeviceName](#getdevicename)|現在選択されているプリンター デバイスの名前を取得します。|  
|[CPrintDialog::GetDevMode](#getdevmode)|取得、`DEVMODE`構造体。|  
|[CPrintDialog::GetDriverName](#getdrivername)|現在選択されているプリンタ ドライバの名前を取得します。|  
|[CPrintDialog::GetFromPage](#getfrompage)|印刷範囲の開始ページを取得します。|  
|[CPrintDialog::GetPortName](#getportname)|現在選択されているプリンター ポートの名前を取得します。|  
|[CPrintDialog::GetPrinterDC](#getprinterdc)|プリンター デバイス コンテキストを識別するハンドルを取得します。|  
|[CPrintDialog::GetToPage](#gettopage)|印刷範囲の終了ページを取得します。|  
|[CPrintDialog::PrintAll](#printall)|ドキュメントのすべてのページを印刷するかどうかを決定します。|  
|[CPrintDialog::PrintCollate](#printcollate)|コピーが要求された部単位で印刷するかどうかを決定します。|  
|[CPrintDialog::PrintRange](#printrange)|ページの指定した範囲のみを印刷するかどうかを決定します。|  
|[CPrintDialog::PrintSelection](#printselection)|現在選択されている項目だけを印刷するかどうかを決定します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPrintDialog::m_pd](#m_pd)|カスタマイズに使用する構造体、`CPrintDialog`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 共通の印刷 ダイアログ ボックスでは、Windows の標準に準拠した方法で印刷および印刷の設定 ダイアログ ボックスを実装する簡単な方法を提供します。  
  
> [!NOTE]
>  `CPrintDialogEx`クラスは、Windows 2000 の印刷プロパティ シートに提供されるサービスをカプセル化します。 詳細については、次を参照してください。、[メンバー](../../mfc/reference/cprintdialogex-class.md)の概要です。  
  
 `CPrintDialog`機能をするのに代替[コモン](../../mfc/reference/cpagesetupdialog-class.md)、提供するために、コモン ダイアログ ボックスの両方の印刷設定、および ページ設定に設計されています。  
  
 アプリケーションの印刷プロセスの多くの側面を処理するため、フレームワークに依存することができます。 この場合は、フレームワークは、自動的に印刷用の Windows コモン ダイアログ ボックスを表示します。 アプリケーションの印刷のフレームワークのハンドルを持つは、独自の印刷 ダイアログ ボックスでは、共通の印刷 ダイアログ ボックスをオーバーライドすることもできます。 詳細については、印刷タスクを処理するために、フレームワークを使用して、記事を参照して[印刷](../../mfc/printing.md)します。  
  
 フレームワークの関与なし印刷処理を行うアプリケーションを実行する場合は、使用、`CPrintDialog`現状有姿"を指定すると、コンス トラクターを持つクラスまたはダイアログからのクラスを派生させることができます`CPrintDialog`と、ニーズに合わせてコンス トラクターを記述します。 いずれの場合、これらのダイアログ ボックスと同様に MFC の標準のダイアログ ボックス クラスから派生しているため`CCommonDialog`です。  
  
 使用する、`CPrintDialog`オブジェクトは、まずを使用してオブジェクトを作成、`CPrintDialog`コンス トラクターです。 ダイアログ ボックスを構築すると、設定または任意の値を変更、 [m_pd](#m_pd)  ダイアログ ボックスのコントロールの値を初期化するためにします。 `m_pd`型の構造は、 [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843)します。 この構造体の詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] を参照してください。  
  
 ハンドルを指定しない場合`m_pd`の**hDevMode**と**と**メンバー、Windows の関数を呼び出してください**GlobalFree**  ダイアログ ボックスを終了するときに、これらのハンドルのです。 によって提供されるフレームワークのプリンターの設定の実装を使用するときに`CWinApp::OnFilePrintSetup`、これらのハンドルを解放する必要はありません。 によって、ハンドルが保持されます`CWinApp`で解放されると`CWinApp`のデストラクターです。 使用する場合は、これらのハンドルを解放することがだけ`CPrintDialog`スタンドアロンです。  
  
 ダイアログ ボックス コントロールを初期化した後、`DoModal`メンバー関数 ダイアログ ボックスが表示され、ユーザーが印刷オプションを選択できるようにします。 `DoModal`ユーザーが [ok] を選択するかどうかを返します ( **IDOK**) またはキャンセル ( **IDCANCEL**) ボタンをクリックします。  
  
 場合`DoModal`返します**IDOK**のいずれかを使用する`CPrintDialog`のユーザーが入力情報を取得するメンバー関数。  
  
 `CPrintDialog::GetDefaults`メンバー関数は、ダイアログ ボックスを表示することがなく、現在のプリンターの既定値を取得するために役立ちます。 このメンバー関数には、ユーザーの操作は不要です。  
  
 ウィンドウを使用できます**情報を得る**関数 ダイアログ ボックスの初期化中にエラーが発生したかどうかを確認し、エラーについて説明します。 この関数の詳細については、次を参照してください。、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `CPrintDialog`COMMDLG に依存します。Windows 3.1 以降のバージョンに付属している DLL ファイルです。  
  
 ダイアログ ボックスをカスタマイズするには、派生クラスを`CPrintDialog`拡張されたコントロールからの通知メッセージを処理するメッセージ マップを追加、独自のダイアログ テンプレートを使用します。 基本クラス処理されないメッセージを渡す必要があります。 フック関数をカスタマイズする必要はありません。  
  
 ダイアログ ボックスは、印刷または印刷のセットアップするかどうかによって異なる方法で同じメッセージを処理するには、各ダイアログ ボックスにクラスを派生する必要があります。 また、Windows をオーバーライドする必要があります**移るため**関数で、印刷 ダイアログ ボックス内でプリンターの設定 を選択すると、新しいダイアログ ボックスの作成を処理します。  
  
 使用する方法について`CPrintDialog`を参照してください[コモン ダイアログ クラス](../../mfc/common-dialog-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPrintDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdlgs.h  
  
##  <a name="a-namecprintdialoga--cprintdialogcprintdialog"></a><a name="cprintdialog"></a>CPrintDialog::CPrintDialog  
 Windows の 印刷または印刷のセットアップのダイアログ オブジェクトを構築します。  
  
```  
CPrintDialog(
    BOOL bPrintSetupOnly,  
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS | PD_HIDEPRINTTOFILE | PD_NOSELECTION,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `bPrintSetupOnly`  
 標準の Windows の [印刷] ダイアログ ボックスまたは [印刷設定] ダイアログ ボックスが表示されるかどうかを指定します。 このパラメーターを設定**TRUE**を標準の Windows プリンターの設定 ダイアログ ボックスを表示します。 設定**FALSE**を Windows の [印刷] ダイアログ ボックスを表示します。 場合`bPrintSetupOnly`は**FALSE**印刷のセットアップ オプション ボタンは、印刷 ダイアログ ボックスに引き続き表示されます。  
  
 `dwFlags`  
 ビットごとの OR 演算子を使用して結合 ダイアログ ボックスの設定をカスタマイズに使用できる&1; つまたは複数のフラグです。 たとえば、 **PD_ALLPAGES**フラグは、ドキュメントのすべてのページに既定の印刷範囲を設定します。 参照してください、 [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]詳細については、これらのフラグ。  
  
 `pParentWnd`  
 ダイアログ ボックスの親ウィンドウまたはオーナー ウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、オブジェクトを構築するだけです。 使用して、 `DoModal`  ダイアログ ボックスを表示するメンバー関数。  
  
 持つコンス トラクターを呼び出すときに注意してください`bPrintSetupOnly`に設定**FALSE**、 **PD_RETURNDC**フラグが自動的に使用します。 呼び出した後`DoModal`、 `GetDefaults`、または`GetPrinterDC`、プリンターの DC が返されます`m_pd.hDC`します。 この DC はへの呼び出しによって解放する必要があります[とき](http://msdn.microsoft.com/library/windows/desktop/dd183533)の呼び出し元によって`CPrintDialog`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&174;](../../mfc/codesnippet/cpp/cprintdialog-class_1.cpp)]  
  
##  <a name="a-namecreateprinterdca--cprintdialogcreateprinterdc"></a><a name="createprinterdc"></a>CPrintDialog::CreatePrinterDC  
 プリンター デバイス コンテキスト (DC) を作成、 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)と[DEVNAMES](../../mfc/reference/devnames-structure.md)構造体。  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたプリンター デバイス コンテキストへのハンドルします。  
  
### <a name="remarks"></a>コメント  
 この DC は DC では、現在のプリンターと見なされ、以前取得したプリンター、ユーザーがドメイン コント ローラーを削除する必要があります。 この関数を呼び出すことができ、[印刷] ダイアログ ボックスを表示せず、結果として得られるのドメイン コント ローラーを使用します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&106;](../../mfc/codesnippet/cpp/cprintdialog-class_2.cpp)]  
  
##  <a name="a-namedomodala--cprintdialogdomodal"></a><a name="domodal"></a>CPrintDialog::DoModal  
 Windows の一般的な印刷ダイアログ ボックスを表示し、コピー、ページ範囲の数などのさまざまな印刷オプションを選択することができ、コピーを照合するかどうか。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 **IDOK**または**IDCANCEL**します。 場合**IDCANCEL**は、Windows を呼び出し、返される[情報を得る](http://msdn.microsoft.com/library/windows/desktop/ms646916)エラーが発生したかどうかを判断します。  
  
 **IDOK**と**IDCANCEL**をユーザーが [ok] または [キャンセル] ボタンを選択するかどうかを示す定数です。  
  
### <a name="remarks"></a>コメント  
 メンバーを設定して、さまざまな印刷ダイアログ オプションを初期化する場合、`m_pd`構造体を呼び出す前に、これを行う必要があります`DoModal`はダイアログ オブジェクトを構築します。  
  
 呼び出した後`DoModal`、他のメンバー ダイアログ ボックスに、設定や、ユーザーが入力した情報を取得する関数を呼び出すことができます。  
  
 持つコンス トラクターを呼び出すときに注意してください`bPrintSetupOnly`に設定**FALSE**、 **PD_RETURNDC**フラグが自動的に使用します。 呼び出した後`DoModal`、 `GetDefaults`、または`GetPrinterDC`、プリンターの DC が返されます`m_pd.hDC`します。 この DC はへの呼び出しによって解放する必要があります[とき](http://msdn.microsoft.com/library/windows/desktop/dd183533)の呼び出し元によって`CPrintDialog`します。  
  
### <a name="example"></a>例  
  例を参照してください[CPrintDialog::CreatePrinterDC](#createprinterdc)します。  
  
##  <a name="a-namegetcopiesa--cprintdialoggetcopies"></a><a name="getcopies"></a>CPrintDialog::GetCopies  
 要求されたコピーの数を取得します。  
  
```  
int GetCopies() const;  
```  
  
### <a name="return-value"></a>戻り値  
 要求されたコピーの数。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出した後`DoModal`コピー要求の数を取得します。  
  
### <a name="example"></a>例  
  例を参照してください[CPrintDialog::PrintCollate](#printcollate)します。  
  
##  <a name="a-namegetdefaultsa--cprintdialoggetdefaults"></a><a name="getdefaults"></a>CPrintDialog::GetDefaults  
 ダイアログ ボックスを表示せずには、既定のプリンター デバイスの既定値を取得します。  
  
```  
BOOL GetDefaults();
```  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 取得した値を配置している、`m_pd`構造体。  
  
 場合によっては、この関数に対する呼び出しは呼び出し、[コンス トラクター](#cprintdialog)の`CPrintDialog`と`bPrintSetupOnly`設定**FALSE**します。 ような場合、プリンターの DC と**と**と**hDevMode** (に&2; つのハンドルがある、`m_pd`データ メンバー) は自動的に割り当てられます。  
  
 場合のコンス トラクター`CPrintDialog`が呼び出された`bPrintSetupOnly`に設定**FALSE**、この関数はしか返されません**と**と**hDevMode** (内にある**m_pd.hDevNames**と**m_pd.hDevMode**)、呼び出し元にはプリンター DC で返すことも**m_pd.hDC**します。 DC のプリンターを削除し、Windows を呼び出す呼び出し元の機能により[GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579)関数が完了すると、ハンドルを`CPrintDialog`オブジェクトです。  
  
### <a name="example"></a>例  
 次のコード片は、通常使うプリンター デバイス コンテキストを取得し、インチあたりのドットでプリンターの解像度をユーザーに報告します。 (この属性はプリンターの機能の多くの場合と呼びます DPI。)  
  
 [!code-cpp[NVC_MFCDocView #&107;](../../mfc/codesnippet/cpp/cprintdialog-class_3.cpp)]  
  
##  <a name="a-namegetdevicenamea--cprintdialoggetdevicename"></a><a name="getdevicename"></a>CPrintDialog::GetDeviceName  
 現在選択されているプリンター デバイスの名前を取得します。  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在選択されているプリンターの名前。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出した後[DoModal](#domodal)または呼び出し後に、現在選択されているプリンタの名前を取得する[ため](#getdefaults)を既定のプリンターの現在のデバイスの既定値を取得します。 ポインターを使用して、`CString`によって返されるオブジェクト`GetDeviceName`の値として`lpszDeviceName`への呼び出しで[CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)します。  
  
### <a name="example"></a>例  
 次のコード片は、ユーザーの既定のプリンター名とプリンターを使用して、スプーラー名と共に、接続されているポートを示します。 コードは、メッセージ ボックスをオンを表示する場合があります"通常使うプリンターが HP LaserJet IIIP \\\server\share winspool。 を使用して"などです。  
  
 [!code-cpp[NVC_MFCDocView #&108;](../../mfc/codesnippet/cpp/cprintdialog-class_4.cpp)]  
  
##  <a name="a-namegetdevmodea--cprintdialoggetdevmode"></a><a name="getdevmode"></a>CPrintDialog::GetDevMode  
 取得、`DEVMODE`構造体。  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)データ構造は、デバイスの初期化とプリンター ドライバーの環境に関する情報が含まれています。 この構造体と Windows によって使用されるメモリのロックを解除する必要があります[GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595)で説明されている関数、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出した後[DoModal](#domodal)または[ため](#getdefaults)印刷デバイスに関する情報を取得します。  
  
### <a name="example"></a>例  
  例を参照してください[CPrintDialog::PrintCollate](#printcollate)します。  
  
##  <a name="a-namegetdrivernamea--cprintdialoggetdrivername"></a><a name="getdrivername"></a>CPrintDialog::GetDriverName  
 現在選択されているプリンタ ドライバの名前を取得します。  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`システム定義のドライバー名を指定します。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出した後[DoModal](#domodal)または[ため](#getdefaults)プリンターのシステム定義のデバイス ドライバーの名前を取得します。 ポインターを使用して、`CString`によって返されるオブジェクト`GetDriverName`の値として`lpszDriverName`への呼び出しで[CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)します。  
  
### <a name="example"></a>例  
  例を参照してください[CPrintDialog::GetDeviceName](#getdevicename)します。  
  
##  <a name="a-namegetfrompagea--cprintdialoggetfrompage"></a><a name="getfrompage"></a>CPrintDialog::GetFromPage  
 印刷範囲の開始ページを取得します。  
  
```  
int GetFromPage() const;  
```  
  
### <a name="return-value"></a>戻り値  
 印刷するページの範囲の開始のページ番号。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出した後`DoModal`を印刷するページの範囲の開始ページ番号を取得します。  
  
### <a name="example"></a>例  
  例を参照してください[CPrintDialog::m_pd](#m_pd)します。  
  
##  <a name="a-namegetportnamea--cprintdialoggetportname"></a><a name="getportname"></a>CPrintDialog::GetPortName  
 現在選択されているプリンター ポートの名前を取得します。  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在選択されているプリンター ポートの名前。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出した後[DoModal](#domodal)または[ため](#getdefaults)を現在選択されているプリンター ポートの名前を取得します。  
  
### <a name="example"></a>例  
  例を参照してください[CPrintDialog::GetDeviceName](#getdevicename)します。  
  
##  <a name="a-namegetprinterdca--cprintdialoggetprinterdc"></a><a name="getprinterdc"></a>CPrintDialog::GetPrinterDC  
 プリンター デバイス コンテキストを識別するハンドルを取得します。  
  
```  
HDC GetPrinterDC() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合のプリンター デバイス コンテキストを識別するハンドルそれ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 場合、`bPrintSetupOnly`のパラメーター、`CPrintDialog`コンス トラクターが**FALSE** (印刷 ダイアログ ボックスが表示されることを示す)、`GetPrinterDC`プリンター デバイス コンテキストへのハンドルを返します。 Windows を呼び出す必要があります[とき](http://msdn.microsoft.com/library/windows/desktop/dd183533)が済んだら、デバイス コンテキストを削除する関数を使用します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&109;](../../mfc/codesnippet/cpp/cprintdialog-class_5.cpp)]  
  
##  <a name="a-namegettopagea--cprintdialoggettopage"></a><a name="gettopage"></a>CPrintDialog::GetToPage  
 印刷範囲の終了ページを取得します。  
  
```  
int GetToPage() const;  
```  
  
### <a name="return-value"></a>戻り値  
 印刷するページの範囲の最後のページ番号。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出した後`DoModal`印刷するページの範囲の最後のページ番号を取得します。  
  
### <a name="example"></a>例  
  例を参照してください[CPrintDialog::m_pd](#m_pd)します。  
  
##  <a name="a-namempda--cprintdialogmpd"></a><a name="m_pd"></a>CPrintDialog::m_pd  
 メンバーはダイアログ オブジェクトの特性を格納する構造体。  
  
```  
PRINTDLG& m_pd;  
```  
  
### <a name="remarks"></a>コメント  
 構築した後、`CPrintDialog`オブジェクトを使用する`m_pd`を呼び出す前に、ダイアログ ボックスのさまざまな側面を設定する、 [DoModal](#domodal)メンバー関数。 詳細については、`m_pd`構造体は、「 [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 変更した場合、`m_pd`データ メンバーを直接、既定の動作をオーバーライドします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&111;](../../mfc/codesnippet/cpp/cprintdialog-class_6.cpp)]  
  
##  <a name="a-nameprintalla--cprintdialogprintall"></a><a name="printall"></a>CPrintDialog::PrintAll  
 ドキュメントのすべてのページを印刷するかどうかを決定します。  
  
```  
BOOL PrintAll() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ドキュメント内のすべてのページを印刷する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出した後`DoModal`をドキュメント内のすべてのページを印刷するかどうかを判断します。  
  
### <a name="example"></a>例  
  例を参照してください[CPrintDialog::m_pd](#m_pd)します。  
  
##  <a name="a-nameprintcollatea--cprintdialogprintcollate"></a><a name="printcollate"></a>CPrintDialog::PrintCollate  
 コピーが要求された部単位で印刷するかどうかを決定します。  
  
```  
BOOL PrintCollate() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスで、[部単位で印刷] チェック ボックスを選択する場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出した後`DoModal`プリンターがドキュメントの印刷したすべてのコピーを照合するかどうかを決定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&110;](../../mfc/codesnippet/cpp/cprintdialog-class_7.cpp)]  
  
##  <a name="a-nameprintrangea--cprintdialogprintrange"></a><a name="printrange"></a>CPrintDialog::PrintRange  
 ページの指定した範囲のみを印刷するかどうかを決定します。  
  
```  
BOOL PrintRange() const;  
```  
  
### <a name="return-value"></a>戻り値  
 だけを印刷するドキュメント内のページの範囲がある場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出した後`DoModal`をドキュメント内のページの範囲のみを印刷するかどうかを判断します。  
  
### <a name="example"></a>例  
  例を参照してください[CPrintDialog::m_pd](#m_pd)します。  
  
##  <a name="a-nameprintselectiona--cprintdialogprintselection"></a><a name="printselection"></a>CPrintDialog::PrintSelection  
 現在選択されている項目だけを印刷するかどうかを決定します。  
  
```  
BOOL PrintSelection() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択した項目を印刷するか専用の場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出した後`DoModal`を現在選択されている項目だけを印刷するかどうかを判断します。  
  
### <a name="example"></a>例  
  例を参照してください[CPrintDialog::m_pd](#m_pd)します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル DIBLOOK](../../visual-cpp-samples.md)   
 [CCommonDialog クラス](../../mfc/reference/ccommondialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CPrintInfo 構造体](../../mfc/reference/cprintinfo-structure.md)

