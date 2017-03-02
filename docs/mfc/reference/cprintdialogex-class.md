---
title: "メンバー クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPrintDialogEx
dev_langs:
- C++
helpviewer_keywords:
- Print Setup dialog box
- CPrintDialogEx class
- Print dialog box
ms.assetid: 1d506703-ee1c-44cc-b4ce-4e778fec26b8
caps.latest.revision: 22
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
ms.openlocfilehash: 8dc8f01eef42b54af18ed07520d547768c931748
ms.lasthandoff: 02/24/2017

---
# <a name="cprintdialogex-class"></a>メンバー クラス
Windows 2000 の [印刷] プロパティ シートに提供されるサービスをカプセル化します。  
  
## <a name="syntax"></a>構文  
  
```  
class CPrintDialogEx : public CCommonDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CPrintDialogEx::CPrintDialogEx](#cprintdialogex)|`CPrintDialogEx` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPrintDialogEx::CreatePrinterDC](#createprinterdc)|印刷 ダイアログ ボックスを表示することがなくプリンター デバイス コンテキストを作成します。|  
|[CPrintDialogEx::DoModal](#domodal)|ダイアログ ボックスを表示し、項目を選択することができます。|  
|[CPrintDialogEx::GetCopies](#getcopies)|要求されたコピーの数を取得します。|  
|[CPrintDialogEx::GetDefaults](#getdefaults)|ダイアログ ボックスを表示せずには、デバイスの既定値を取得します。|  
|[CPrintDialogEx::GetDeviceName](#getdevicename)|現在選択されているプリンター デバイスの名前を取得します。|  
|[CPrintDialogEx::GetDevMode](#getdevmode)|取得、`DEVMODE`構造体。|  
|[CPrintDialogEx::GetDriverName](#getdrivername)|プリンターのシステム定義のデバイス ドライバーの名前を取得します。|  
|[CPrintDialogEx::GetPortName](#getportname)|現在選択されているプリンター ポートの名前を取得します。|  
|[CPrintDialogEx::GetPrinterDC](#getprinterdc)|プリンター デバイス コンテキストを識別するハンドルを取得します。|  
|[CPrintDialogEx::PrintAll](#printall)|ドキュメントのすべてのページを印刷するかどうかを決定します。|  
|[CPrintDialogEx::PrintCollate](#printcollate)|コピーが要求された部単位で印刷するかどうかを決定します。|  
|[CPrintDialogEx::PrintCurrentPage](#printcurrentpage)|ドキュメントの現在のページを印刷するかどうかを決定します。|  
|[CPrintDialogEx::PrintRange](#printrange)|ページの指定した範囲のみを印刷するかどうかを決定します。|  
|[CPrintDialogEx::PrintSelection](#printselection)|現在選択されている項目だけを印刷するかどうかを決定します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPrintDialogEx::m_pdex](#m_pdex)|カスタマイズに使用する構造体、`CPrintDialogEx`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 アプリケーションの印刷プロセスの多くの側面を処理するため、フレームワークに依存することができます。 詳細については、印刷タスクを処理するために、フレームワークを使用して、記事を参照して[印刷](../../mfc/printing.md)します。  
  
 フレームワークの関与なし印刷処理を行うアプリケーションを実行する場合は、使用、`CPrintDialogEx`現状有姿"を指定すると、コンス トラクターを持つクラスまたはダイアログからのクラスを派生させることができます`CPrintDialogEx`と、ニーズに合わせてコンス トラクターを記述します。 いずれの場合、これらのダイアログ ボックスと同様に MFC の標準のダイアログ ボックス クラスから派生しているため`CCommonDialog`です。  
  
 使用する、`CPrintDialogEx`オブジェクトは、まずを使用してオブジェクトを作成、`CPrintDialogEx`コンス トラクターです。 ダイアログ ボックスを構築すると、設定または任意の値を変更、 [m_pdex](#m_pdex)  ダイアログ ボックスのコントロールの値を初期化するためにします。 `m_pdex`型の構造は、 [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844)します。 この構造体の詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] を参照してください。  
  
 ハンドルを指定しない場合`m_pdex`の**hDevMode**と**と**メンバー、Windows の関数を呼び出してください**GlobalFree**  ダイアログ ボックスを終了するときに、これらのハンドルのです。  
  
 ダイアログ ボックス コントロールを初期化した後、`DoModal`メンバー関数 ダイアログ ボックスが表示され、ユーザーが印刷オプションを選択できるようにします。 `DoModal`が返される、ユーザーが [ok]、適用、または [キャンセル] ボタンを選択するかどうかを判断できます。  
  
 ユーザーが [ok] を押した場合使用して`CPrintDialogEx`のユーザーが入力情報を取得するメンバー関数。  
  
 `CPrintDialogEx::GetDefaults`メンバー関数は、ダイアログ ボックスを表示することがなく、現在のプリンターの既定値を取得するために役立ちます。 このメソッドには、ユーザーの操作は不要です。  
  
 ウィンドウを使用できます**情報を得る**関数 ダイアログ ボックスの初期化中にエラーが発生したかどうかを確認し、エラーについて説明します。 この関数の詳細については、次を参照してください。、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 使用する方法について`CPrintDialogEx`を参照してください[コモン ダイアログ クラス](../../mfc/common-dialog-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `IObjectWithSite`  
  
 `IPrintDialogCallback`  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPrintDialogEx`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdlgs.h  
  
##  <a name="a-namecprintdialogexa--cprintdialogexcprintdialogex"></a><a name="cprintdialogex"></a>CPrintDialogEx::CPrintDialogEx  
 Windows 2000 の印刷プロパティ シートを作成します。  
  
```  
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwFlags`  
 ビットごとの OR 演算子を使用して結合 ダイアログ ボックスの設定をカスタマイズに使用できる&1; つまたは複数のフラグです。 たとえば、 **PD_ALLPAGES**フラグは、ドキュメントのすべてのページに既定の印刷範囲を設定します。 参照してください、 [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]詳細については、これらのフラグ。  
  
 `pParentWnd`  
 ダイアログ ボックスの親ウィンドウまたはオーナー ウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、オブジェクトを構築するだけです。 使用して、 `DoModal`  ダイアログ ボックスを表示するメンバー関数。  
  
##  <a name="a-namecreateprinterdca--cprintdialogexcreateprinterdc"></a><a name="createprinterdc"></a>CPrintDialogEx::CreatePrinterDC  
 プリンター デバイス コンテキスト (DC) を作成、 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)と[DEVNAMES](../../mfc/reference/devnames-structure.md)構造体。  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたプリンター デバイス コンテキストへのハンドルします。  
  
### <a name="remarks"></a>コメント  
 返された DC にも格納、 **hDC**のメンバー [m_pdex](#m_pdex)します。  
  
 この DC は DC では、現在のプリンターと見なされ、以前取得したプリンターの Dc を削除する必要があります。 この関数を呼び出すことができ、[印刷] ダイアログ ボックスを表示せず、結果として得られるのドメイン コント ローラーを使用します。  
  
##  <a name="a-namedomodala--cprintdialogexdomodal"></a><a name="domodal"></a>CPrintDialogEx::DoModal  
 Windows 2000 の [印刷] 一般的なプロパティ シートを表示し、コピー、ページ範囲の数などのさまざまな印刷オプションを選択できるようにするには、この関数を呼び出してコピーを照合するかどうかとします。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 INT_PTR では、値は実際には、HRESULT を返します。 戻り値を参照してください[PrintDlgEx](http://msdn.microsoft.com/library/windows/desktop/ms646942)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 メンバーを設定して、さまざまな印刷ダイアログ オプションを初期化する場合、`m_pdex`構造体を呼び出す前に、これを行う必要があります`DoModal`はダイアログ オブジェクトを構築します。  
  
 呼び出した後`DoModal`、他のメンバー ダイアログ ボックスに、設定や、ユーザーが入力した情報を取得する関数を呼び出すことができます。  
  
 場合、 **PD_RETURNDC**を呼び出すときにフラグを使用して`DoModal`、プリンターの DC が返されます、 **hDC**のメンバー [m_pdex](#m_pdex)します。 この DC はへの呼び出しによって解放する必要があります[とき](http://msdn.microsoft.com/library/windows/desktop/dd183533)の呼び出し元によって`CPrintDialogEx`します。  
  
##  <a name="a-namegetcopiesa--cprintdialogexgetcopies"></a><a name="getcopies"></a>CPrintDialogEx::GetCopies  
 この関数を呼び出した後`DoModal`コピー要求の数を取得します。  
  
```  
int GetCopies() const;  
```  
  
### <a name="return-value"></a>戻り値  
 要求されたコピーの数。  
  
##  <a name="a-namegetdefaultsa--cprintdialogexgetdefaults"></a><a name="getdefaults"></a>CPrintDialogEx::GetDefaults  
 ダイアログ ボックスを表示せず、既定のプリンターの既定のデバイスを取得するには、この関数を呼び出します。  
  
```  
BOOL GetDefaults();
```  
  
### <a name="return-value"></a>戻り値  
 **TRUE**成功した場合、それ以外の場合**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 プリンター デバイス コンテキスト (DC) を作成、 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)と[DEVNAMES](../../mfc/reference/devnames-structure.md)構造体。  
  
 `GetDefaults`[印刷] プロパティ シートは表示されません。 代わりに、設定、**と**と**hDevMode**のメンバー [m_pdex](#m_pdex)へのハンドルを[DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)と[DEVNAMES](../../mfc/reference/devnames-structure.md)がシステムの既定のプリンターに対して初期化構造体。 両方とも**と**と**hDevMode**は NULL を指定する必要がありますまたは`GetDefaults`は失敗します。  
  
 場合、 **PD_RETURNDC**フラグを設定すると、この関数はしか返されません**と**と**hDevMode** (内にある**m_pdex.hDevNames**と**m_pdex.hDevMode**)、呼び出し元にもプリンター DC でを返しますが、 **m_pdex.hDC**します。 DC のプリンターを削除し、Windows を呼び出す呼び出し元の機能により[GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579)関数が完了すると、ハンドルを`CPrintDialogEx`オブジェクトです。  
  
##  <a name="a-namegetdevicenamea--cprintdialogexgetdevicename"></a><a name="getdevicename"></a>CPrintDialogEx::GetDeviceName  
 この関数を呼び出した後[DoModal](#domodal)または呼び出し後に、現在選択されているプリンタの名前を取得する[ため](#getdefaults)を通常使うプリンターの名前を取得します。  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在選択されているプリンターの名前。  
  
### <a name="remarks"></a>コメント  
 ポインターを使用して、`CString`によって返されるオブジェクト`GetDeviceName`の値として`lpszDeviceName`への呼び出しで[CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)します。  
  
##  <a name="a-namegetdevmodea--cprintdialogexgetdevmode"></a><a name="getdevmode"></a>CPrintDialogEx::GetDevMode  
 この関数を呼び出した後[DoModal](#domodal)または[ため](#getdefaults)印刷デバイスに関する情報を取得します。  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)データ構造は、デバイスの初期化とプリンター ドライバーの環境に関する情報が含まれています。 この構造体と Windows によって使用されるメモリのロックを解除する必要があります[GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595)で説明されている関数、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetdrivernamea--cprintdialogexgetdrivername"></a><a name="getdrivername"></a>CPrintDialogEx::GetDriverName  
 この関数を呼び出した後[DoModal](#domodal)または[ため](#getdefaults)プリンターのシステム定義のデバイス ドライバーの名前を取得します。  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`システム定義のドライバー名を指定します。  
  
### <a name="remarks"></a>コメント  
 ポインターを使用して、`CString`によって返されるオブジェクト`GetDriverName`の値として`lpszDriverName`への呼び出しで[CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)します。  
  
##  <a name="a-namegetportnamea--cprintdialogexgetportname"></a><a name="getportname"></a>CPrintDialogEx::GetPortName  
 この関数を呼び出した後[DoModal](#domodal)または[ため](#getdefaults)を現在選択されているプリンター ポートの名前を取得します。  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在選択されているプリンター ポートの名前。  
  
##  <a name="a-namegetprinterdca--cprintdialogexgetprinterdc"></a><a name="getprinterdc"></a>CPrintDialogEx::GetPrinterDC  
 プリンター デバイス コンテキスト ハンドルを返します。  
  
```  
HDC GetPrinterDC() const;  
```  
  
### <a name="return-value"></a>戻り値  
 プリンター デバイス コンテキストへのハンドル。  
  
### <a name="remarks"></a>コメント  
 Windows を呼び出す必要があります[とき](http://msdn.microsoft.com/library/windows/desktop/dd183533)が済んだら、デバイス コンテキストを削除する関数を使用します。  
  
##  <a name="a-namempdexa--cprintdialogexmpdex"></a><a name="m_pdex"></a>CPrintDialogEx::m_pdex  
 ダイアログ オブジェクトの特性を格納するメンバーが PRINTDLGEX 構造体。  
  
```  
PRINTDLGEX m_pdex;  
```  
  
### <a name="remarks"></a>コメント  
 構築した後、`CPrintDialogEx`オブジェクトを使用する`m_pdex`を呼び出す前に、ダイアログ ボックスのさまざまな側面を設定する、 [DoModal](#domodal)メンバー関数。 詳細については、`m_pdex`構造体は、「 [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 変更した場合、`m_pdex`データ メンバーを直接、既定の動作をオーバーライドします。  
  
##  <a name="a-nameprintalla--cprintdialogexprintall"></a><a name="printall"></a>CPrintDialogEx::PrintAll  
 この関数を呼び出した後`DoModal`をドキュメント内のすべてのページを印刷するかどうかを判断します。  
  
```  
BOOL PrintAll() const;  
```  
  
### <a name="return-value"></a>戻り値  
 **TRUE** 、ドキュメント内のすべてのページの印刷、それ以外の場合**FALSE**します。  
  
##  <a name="a-nameprintcollatea--cprintdialogexprintcollate"></a><a name="printcollate"></a>CPrintDialogEx::PrintCollate  
 この関数を呼び出した後`DoModal`プリンターがドキュメントの印刷したすべてのコピーを照合するかどうかを決定します。  
  
```  
BOOL PrintCollate() const;  
```  
  
### <a name="return-value"></a>戻り値  
 **TRUE**ダイアログ ボックスで、[部単位で印刷] チェック ボックスを選択する場合は、それ以外の場合**FALSE**します。  
  
##  <a name="a-nameprintcurrentpagea--cprintdialogexprintcurrentpage"></a><a name="printcurrentpage"></a>CPrintDialogEx::PrintCurrentPage  
 この関数を呼び出した後`DoModal`を文書の現在のページを印刷するかどうかを判断します。  
  
```  
BOOL PrintCurrentPage() const;  
```  
  
### <a name="return-value"></a>戻り値  
 **TRUE**場合**現在のページを印刷**印刷ダイアログ ボックスで選択されているそれ以外の場合は、 **FALSE**します。  
  
##  <a name="a-nameprintrangea--cprintdialogexprintrange"></a><a name="printrange"></a>CPrintDialogEx::PrintRange  
 この関数を呼び出した後`DoModal`をドキュメント内のページの範囲のみを印刷するかどうかを判断します。  
  
```  
BOOL PrintRange() const;  
```  
  
### <a name="return-value"></a>戻り値  
 **TRUE**だけ印刷、それ以外のさまざまなドキュメントのページがある場合**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 指定したページ範囲を決定できる[m_pdex](#m_pdex) (を参照してください**nPageRanges**、 **nMaxPageRanges**、および**lpPageRanges**で、 [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844)構造体、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)])。  
  
##  <a name="a-nameprintselectiona--cprintdialogexprintselection"></a><a name="printselection"></a>CPrintDialogEx::PrintSelection  
 この関数を呼び出した後`DoModal`を現在選択されている項目だけを印刷するかどうかを判断します。  
  
```  
BOOL PrintSelection() const;  
```  
  
### <a name="return-value"></a>戻り値  
 **TRUE**だけ印刷、それ以外の選択した項目がある場合**FALSE**します。  
  
## <a name="see-also"></a>関連項目  
 [CCommonDialog クラス](../../mfc/reference/ccommondialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CPrintInfo 構造体](../../mfc/reference/cprintinfo-structure.md)

