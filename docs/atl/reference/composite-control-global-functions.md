---
title: "複合コントロールのグローバル関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- composite controls, global functions
ms.assetid: 536884cd-e863-4c7a-ab0a-604dc60a0bbe
caps.latest.revision: 20
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: dd043335df32c04349403bbfe38e647f352826c4
ms.lasthandoff: 02/24/2017

---
# <a name="composite-control-global-functions"></a>複合コントロールのグローバル関数
これらの関数は、ダイアログ ボックスの作成、作成、ホスティング、および ActiveX コントロールのサポートを提供します。  
  
> [!IMPORTANT]
>  実行するアプリケーションでは、次の表に示されている関数を使用できません、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]です。  
  
|||  
|-|-|  
|[AtlAxDialogBox](#atlaxdialogbox)|ユーザーが用意するダイアログ テンプレートからモーダル ダイアログ ボックスを作成します。 表示されたダイアログ ボックスでは、ActiveX コントロールを含めることができます。|  
|[AtlAxCreateDialog](#atlaxcreatedialog)|ユーザーが用意するダイアログ テンプレートからモードレス ダイアログ ボックスを作成します。 表示されたダイアログ ボックスでは、ActiveX コントロールを含めることができます。|  
|[して](#atlaxcreatecontrol)|ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。|  
|[行うに](#atlaxcreatecontrolex)|ActiveX コントロールを作成、初期化し、指定されたウィンドウでホストおよびコントロールからインターフェイス ポインター (またはポインター) を取得します。|  
|[して](#atlaxcreatecontrollic)|ライセンスされた ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。|  
|[AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)|ライセンスされた ActiveX コントロールを作成、初期化し、指定されたウィンドウでホストおよびコントロールからインターフェイス ポインター (またはポインター) を取得します。|  
|[関連付け](#atlaxattachcontrol)|事前に作成されたコントロールを指定されたウィンドウにアタッチします。|  
|[AtlAxGetHost](#atlaxgethost)|(もしあれば) は、指定したウィンドウ、に対するコンテナーへのダイレクト インターフェイス ポインターを取得するために使用のハンドルを指定します。|  
|[AtlAxGetControl](#atlaxgetcontrol)|指定のウィンドウ (存在する場合)、内に含まれるコントロールへのダイレクト インターフェイス ポインターを取得するために使用のハンドルを指定します。|  
|[AtlSetChildSite](#atlsetchildsite)|初期化、 **IUnknown**子サイトのです。|  
|[な](#atlaxwininit)|AxWin オブジェクトのホスティング コードを初期化します。|  
|[AtlAxWinTerm](#atlaxwinterm)|AxWin オブジェクトのホスティング コードを非初期化します。|  
|[AtlGetObjectSourceInterface](#atlgetobjectsourceinterface)|オブジェクトの既定のソース インターフェイスに関する情報を返します。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlhost.h  

##  <a name="a-nameatlaxdialogboxa--atlaxdialogbox"></a><a name="atlaxdialogbox"></a>AtlAxDialogBox  
 ユーザーが用意するダイアログ テンプレートからモーダル ダイアログ ボックスを作成します。  
   
```
ATLAPI_(int) AtlAxDialogBox(
    HINSTANCE hInstance,
    LPCWSTR lpTemplateName,
    HWND hWndParent,
    DLGPROC lpDialogProc,
    LPARAM dwInitParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `hInstance`  
 [in]実行可能ファイルには、ダイアログ ボックスのテンプレートが含まれるモジュールのインスタンスを識別します。  
  
 `lpTemplateName`  
 [in]ダイアログ ボックスのテンプレートを識別します。 このパラメーターは、いずれかのダイアログ ボックスのテンプレートの名前を指定する null で終わる文字列へのポインターまたはダイアログ ボックスのテンプレートのリソース識別子を指定する整数値です。 パラメーターは、リソース識別子を指定する場合、ワードが高位を&0; にする必要があり、id がその下位ワードに格納する必要があります。 使用することができます、[されるときは](http://msdn.microsoft.com/library/windows/desktop/ms648029)マクロをこの値を作成します。  
  
 `hWndParent`  
 [in]ダイアログ ボックスを所有しているウィンドウを識別します。  
  
 `lpDialogProc`  
 [in]ダイアログ ボックス プロシージャへのポインター。 ダイアログ ボックス プロシージャの詳細については、次を参照してください。 [DialogProc](http://msdn.microsoft.com/library/windows/desktop/ms645469)します。  
  
 `dwInitParam`  
 [in]ダイアログ ボックスに渡す値を指定する、 **lParam**のパラメーター、 **WM_INITDIALOG**メッセージです。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
### <a name="remarks"></a>コメント  
 使用する**AtlAxDialogBox** 、ActiveX コントロールを含むダイアログ テンプレートに指定する有効な**CLSID**、 **APPID**または URL の文字列として、*テキスト*のフィールド、**コントロール**"AtlAxWin80 としてと共に、ダイアログ リソースのセクションで、*クラス名*同じセクションにあるフィールドです。 次にどのような有効な示します**コントロール**セクションのようになります。  
  
 `CONTROL    "{04FE35E9-ADBC-4f1d-83FE-8FA4D1F71C7F}", IDC_TEST,`  
  
 `"AtlAxWin80", WS_GROUP | WS_TABSTOP, 0, 0, 100, 100`  
  
 リソースのスクリプトの編集の詳細については、次を参照してください。[方法: テキスト形式でリソース スクリプト ファイルを開く](../../windows/how-to-open-a-resource-script-file-in-text-format.md)します。 コントロールのリソース定義ステートメントの詳細については、次を参照してください。[コントロールに共通のパラメーター](http://msdn.microsoft.com/library/windows/desktop/aa380902)  [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *: SDK ツール*します。  
  
 一般のダイアログ ボックスの詳細についてを参照してください[DialogBox](http://msdn.microsoft.com/library/windows/desktop/ms645452)と[CreateDialogParam](http://msdn.microsoft.com/library/windows/desktop/ms645445)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameatlaxcreatedialoga--atlaxcreatedialog"></a><a name="atlaxcreatedialog"></a>AtlAxCreateDialog  
 ユーザーが用意するダイアログ テンプレートからモードレス ダイアログ ボックスを作成します。  
  
```
ATLAPI_(HWND) AtlAxCreateDialog(
    HINSTANCE hInstance,
    LPCWSTR lpTemplateName,
    HWND hWndParent,
    DLGPROC lpDialogProc,
    LPARAM dwInitParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `hInstance`  
 [in]実行可能ファイルには、ダイアログ ボックスのテンプレートが含まれるモジュールのインスタンスを識別します。  
  
 `lpTemplateName`  
 [in]ダイアログ ボックスのテンプレートを識別します。 このパラメーターは、いずれかのダイアログ ボックスのテンプレートの名前を指定する null で終わる文字列へのポインターまたはダイアログ ボックスのテンプレートのリソース識別子を指定する整数値です。 パラメーターは、リソース識別子を指定する場合、ワードが高位を&0; にする必要があり、id がその下位ワードに格納する必要があります。 使用することができます、[されるときは](http://msdn.microsoft.com/library/windows/desktop/ms648029)マクロをこの値を作成します。  
  
 `hWndParent`  
 [in]ダイアログ ボックスを所有しているウィンドウを識別します。  
  
 `lpDialogProc`  
 [in]ダイアログ ボックス プロシージャへのポインター。 ダイアログ ボックス プロシージャの詳細については、次を参照してください。 [DialogProc](http://msdn.microsoft.com/library/windows/desktop/ms645469)します。  
  
 `dwInitParam`  
 [in]ダイアログ ボックスに渡す値を指定する、 **lParam**のパラメーター、 **WM_INITDIALOG**メッセージです。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
### <a name="remarks"></a>コメント  
 表示されたダイアログ ボックスでは、ActiveX コントロールを含めることができます。  
  
 参照してください[:createdialog](http://msdn.microsoft.com/library/windows/desktop/ms645434)と[CreateDialogParam](http://msdn.microsoft.com/library/windows/desktop/ms645445)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameatlaxcreatecontrola--atlaxcreatecontrol"></a><a name="atlaxcreatecontrol"></a>して  
 ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。  
  

```
ATLAPI AtlAxCreateControl(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 コントロールに渡される文字列へのポインター。 次の方法のいずれかでフォーマットされている必要があります。  
  
-   ProgID など"MSCAL します。Calendar.7"  
  
-   "{8E27C92B-1264-101C-8A2F-040224009C02}"などの CLSID  
  
-   URL"http://www.microsoft.com"など  
  
-   などのアクティブなドキュメントへの参照"file://\\\Documents\MyDoc.doc"  
  
-   などの HTML のフラグメント"MSHTML:\<HTML >\<本文 > これは、行のテキスト\</body >\</HTML >"  
  
    > [!NOTE]
    >  "MSHTML:"MSHTML ストリームとして指定できるように、HTML フラグメントを付ける必要があります。  
  
 `hWnd`  
 [in]コントロールのアタッチするウィンドウへのハンドルします。  
  
 `pStream`  
 [in]コントロールのプロパティを初期化するために使用されるストリームへのポインター。 できる**NULL**します。  
  
 `ppUnkContainer`  
 [out]受け取るポインターのアドレス、 **IUnknown**のコンテナーです。 できる**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
### <a name="remarks"></a>コメント  
 このグローバル関数が呼び出し元と同じ結果を使用する[行うに](#atlaxcreatecontrolex)( `lpszName` **、** `hWnd` **、** `pStream` **、NULL、NULL、NULL、NULL** );。  
  
 ライセンスされた ActiveX コントロールを作成するを参照してください。[して](#atlaxcreatecontrollic)します。  
  
##  <a name="a-nameatlaxcreatecontrolexa--atlaxcreatecontrolex"></a><a name="atlaxcreatecontrolex"></a>行うに  
 ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。 新しいコントロールのインターフェイス ポインターとイベント シンクも作成されます。  
  
```
ATLAPI AtlAxCreateControlEx(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    IUnknown** ppUnkControl,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 コントロールに渡される文字列へのポインター。 次の方法のいずれかでフォーマットされている必要があります。  
  
-   ProgID など"MSCAL します。Calendar.7"  
  
-   "{8E27C92B-1264-101C-8A2F-040224009C02}"などの CLSID  
  
-   URL"http://www.microsoft.com"など  
  
-   などのアクティブなドキュメントへの参照"file://\\\Documents\MyDoc.doc"  
  
-   などの HTML のフラグメント"MSHTML:\<HTML >\<本文 > これは、行のテキスト\</body >\</HTML >"  
  
    > [!NOTE]
    >  "MSHTML:"MSHTML ストリームとして指定できるように、HTML フラグメントを付ける必要があります。  
  
 `hWnd`  
 [in]コントロールのアタッチするウィンドウへのハンドルします。  
  
 `pStream`  
 [in]コントロールのプロパティを初期化するために使用されるストリームへのポインター。 できる**NULL**します。  
  
 `ppUnkContainer`  
 [out]受け取るポインターのアドレス、 **IUnknown**のコンテナーです。 できる**NULL**します。  
  
 `ppUnkControl`  
 [out]受け取るポインターのアドレス、 **IUnknown**に作成されたコントロールのです。 できる**NULL**します。  
  
 `iidSink`  
 格納されているオブジェクトのアウトゴーイング インターフェイスのインターフェイス id です。  
  
 *punkSink*  
 ポインター、 **IUnknown**で指定された接続ポイントに接続されているシンク オブジェクトのインターフェイス`iidSink`含まれるオブジェクトが含まれているオブジェクトが作成された後にします。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
### <a name="remarks"></a>コメント  
 `AtlAxCreateControlEx`ような[して](#atlaxcreatecontrol)が新しく作成されたコントロールへのインターフェイス ポインターを受け取るし、コントロールによって発生したイベントを受信するイベント シンクをセットアップすることもできます。  
  
 ライセンスされた ActiveX コントロールを作成するを参照してください。 [AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)します。  
  
##  <a name="a-nameatlaxcreatecontrollica--atlaxcreatecontrollic"></a><a name="atlaxcreatecontrollic"></a>して  
 ライセンスされた ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。  

```
ATLAPI AtlAxCreateControlLic(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    BSTR bstrLic = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 コントロールに渡される文字列へのポインター。 次の方法のいずれかでフォーマットされている必要があります。  
  
-   ProgID など"MSCAL します。Calendar.7"  
  
-   "{8E27C92B-1264-101C-8A2F-040224009C02}"などの CLSID  
  
-   URL"http://www.microsoft.com"など  
  
-   などのアクティブなドキュメントへの参照"file://\\\Documents\MyDoc.doc"  
  
-   などの HTML のフラグメント"MSHTML:\<HTML >\<本文 > これは、行のテキスト\</body >\</HTML >"  
  
    > [!NOTE]
    >  "MSHTML:"MSHTML ストリームとして指定できるように、HTML フラグメントを付ける必要があります。  
  
 `hWnd`  
 コントロールのアタッチするウィンドウへのハンドルします。  
  
 `pStream`  
 コントロールのプロパティを初期化するために使用されるストリームへのポインター。 できる**NULL**します。  
  
 `ppUnkContainer`  
 受け取るポインターのアドレス、 **IUnknown**のコンテナーです。 できる**NULL**します。  
  
 `bstrLic`  
 コントロールのライセンスを含む BSTR。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
### <a name="example"></a>例  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)を使用する方法のサンプルについては`AtlAxCreateControlLic`です。  
  
##  <a name="a-nameatlaxcreatecontrollicexa--atlaxcreatecontrollicex"></a><a name="atlaxcreatecontrollicex"></a>AtlAxCreateControlLicEx  
 ライセンスされた ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。 新しいコントロールのインターフェイス ポインターとイベント シンクも作成されます。  
  
```
ATLAPI AtlAxCreateControlLicEx(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    IUnknown** ppUnkControl,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLic = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 コントロールに渡される文字列へのポインター。 次の方法のいずれかでフォーマットされている必要があります。  
  
-   ProgID など"MSCAL します。Calendar.7"  
  
-   "{8E27C92B-1264-101C-8A2F-040224009C02}"などの CLSID  
  
-   URL"http://www.microsoft.com"など  
  
-   などのアクティブなドキュメントへの参照"file://\\\Documents\MyDoc.doc"  
  
-   などの HTML のフラグメント"MSHTML:\<HTML >\<本文 > これは、行のテキスト\</body >\</HTML >"  
  
    > [!NOTE]
    >  "MSHTML:"MSHTML ストリームとして指定できるように、HTML フラグメントを付ける必要があります。  
  
 `hWnd`  
 コントロールのアタッチするウィンドウへのハンドルします。  
  
 `pStream`  
 コントロールのプロパティを初期化するために使用されるストリームへのポインター。 できる**NULL**します。  
  
 `ppUnkContainer`  
 受け取るポインターのアドレス、 **IUnknown**のコンテナーです。 できる**NULL**します。  
  
 `ppUnkControl`  
 [out]受け取るポインターのアドレス、 **IUnknown**に作成されたコントロールのです。 できる**NULL**します。  
  
 `iidSink`  
 格納されているオブジェクトのアウトゴーイング インターフェイスのインターフェイス id です。  
  
 *punkSink*  
 ポインター、 **IUnknown**で指定された接続ポイントに接続されているシンク オブジェクトのインターフェイス`iidSink`含まれるオブジェクトが含まれているオブジェクトが作成された後にします。  
  
 `bstrLic`  
 コントロールのライセンスを含む BSTR。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
### <a name="remarks"></a>コメント  
 `AtlAxCreateControlLicEx`ような[して](#atlaxcreatecontrollic)が新しく作成されたコントロールへのインターフェイス ポインターを受け取るし、コントロールによって発生したイベントを受信するイベント シンクをセットアップすることもできます。  
  
### <a name="example"></a>例  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)を使用する方法のサンプルについては`AtlAxCreateControlLicEx`です。  
  
##  <a name="a-nameatlaxattachcontrola--atlaxattachcontrol"></a><a name="atlaxattachcontrol"></a>関連付け  
 事前に作成されたコントロールを指定されたウィンドウにアタッチします。  
  
```
ATLAPI AtlAxAttachControl(
    IUnknown* pControl,
    HWND hWnd,
    IUnknown** ppUnkContainer);
```  
  
### <a name="parameters"></a>パラメーター  
 `pControl`  
 [in]ポインター、 **IUnknown**コントロールのです。  
  
 `hWnd`  
 [in]コントロールをホストするウィンドウへのハンドルします。  
  
 `ppUnkContainer`  
 [out]ポインターへのポインター、 **IUnknown**のコンテナー オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
### <a name="remarks"></a>コメント  
 使用[行うに](#atlaxcreatecontrolex)と[して](#atlaxcreatecontrol)を同時に作成し、コントロールを追加します。  
  
> [!NOTE]
>  アタッチされるコントロール オブジェクトを呼び出す前に正しく初期化する必要があります`AtlAxAttachControl`します。  
  
##  <a name="a-nameatlaxgethosta--atlaxgethost"></a><a name="atlaxgethost"></a>AtlAxGetHost  
 ハンドルが与えられた指定のウィンドウに対するコンテナーへのダイレクト インターフェイス ポインターを取得します。  
  
```
ATLAPI AtlAxGetHost(HWND h, IUnknown** pp);
```  
  
### <a name="parameters"></a>パラメーター  
 `h`  
 [in]コントロールをホストしているウィンドウのハンドル。  
  
 `pp`  
 [out]**IUnknown**のコントロールのコンテナーです。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
##  <a name="a-nameatlaxgetcontrola--atlaxgetcontrol"></a><a name="atlaxgetcontrol"></a>AtlAxGetControl  
 ハンドルが与えられた指定のウィンドウ内に含まれるコントロールへのダイレクト インターフェイス ポインターを取得します。  
  
```
ATLAPI AtlAxGetControl(HWND h, IUnknown** pp);
```  
  
### <a name="parameters"></a>パラメーター  
 `h`  
 [in]コントロールをホストしているウィンドウのハンドル。  
  
 `pp`  
 [out]**IUnknown**ホストされるコントロールのです。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
##  <a name="a-nameatlsetchildsitea--atlsetchildsite"></a><a name="atlsetchildsite"></a>AtlSetChildSite  
 子オブジェクトのサイトを設定するには、この関数を呼び出す、 **IUnknown**の親オブジェクトです。  
  
```
HRESULT AtlSetChildSite(IUnknown* punkChild, IUnknown* punkParent);
```  
  
### <a name="parameters"></a>パラメーター  
 *punkChild*  
 [in]ポインター、 **IUnknown**子のインターフェイスです。  
  
 `punkParent`  
 [in]ポインター、 **IUnknown**親のインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準的な HRESULT 値。  
  
##  <a name="a-nameatlaxwininita--atlaxwininit"></a><a name="atlaxwininit"></a>な  
 この関数は、ホスティング コードを登録することにより、ATL のコントロールを初期化、 **"AtlAxWin80**と**"AtlAxWinLic80"**ウィンドウは、さらに、いくつかのカスタム ウィンドウ メッセージのクラスです。  
  
```
ATLAPI_(BOOL) AtlAxWinInit();
```  
  
### <a name="return-value"></a>戻り値  
 コードをホストしているコントロールの初期化が成功した場合は&0; 以外。それ以外の場合**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 ATL コントロール ホスト API を使用する前に、この関数を呼び出す必要があります。 この関数への呼び出しの後、 **"AtlAxWin"**への呼び出しでウィンドウ クラスを使用することができます[CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)または[CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  

##  <a name="a-nameatlaxwinterma--atlaxwinterm"></a><a name="atlaxwinterm"></a>AtlAxWinTerm  
 この関数には、ATL のコントロールの登録を解除してコードをホストが初期化されません、 **"AtlAxWin80**と**"AtlAxWinLic80"**ウィンドウ クラスです。  
  
```
inline BOOL AtlAxWinTerm();
```  
  
### <a name="return-value"></a>戻り値  
 常に返します**TRUE**します。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出すだけ[UnregisterClass](http://msdn.microsoft.com/library/windows/desktop/ms644899) 」の説明に従って、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 この関数を呼び出した場合に既存のすべてのホスト ウィンドウが破棄された後にクリーンアップ[な](#atlaxwininit)不要になったホスト ウィンドウを作成する必要があります。 この関数が呼び出されない場合、ウィンドウ クラスが登録解除する自動的にプロセスが終了したときにします。  
  
##  <a name="a-nameatlgetobjectsourceinterfacea--atlgetobjectsourceinterface"></a><a name="atlgetobjectsourceinterface"></a>AtlGetObjectSourceInterface  
 オブジェクトの既定のソース インターフェイスに関する情報を取得します。  
  
```
ATLAPI AtlGetObjectSourceInterface(
    IUnknown* punkObj,
    GUID* plibid,
    IID* piid,
    unsigned short* pdwMajor,
    unsigned short* pdwMinor);
```  
  
### <a name="parameters"></a>パラメーター  
 `punkObj`  
 [in]情報が返されるが対象のオブジェクトへのポインター。  
  
 `plibid`  
 [out]送信元インターフェイスの定義が含まれるタイプ ライブラリの LIBID へのポインター。  
  
 `piid`  
 [out]オブジェクトの既定のソース インターフェイスのインターフェイス ID へのポインター。  
  
 *pdwMajor*  
 [out]送信元インターフェイスの定義が含まれるタイプ ライブラリのメジャー バージョン番号へのポインター。  
  
 *pdwMinor*  
 [out]送信元インターフェイスの定義が含まれるタイプ ライブラリのマイナー バージョン番号へのポインター。  
  
### <a name="return-value"></a>戻り値  
 標準的な HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 `AtlGetObjectSourceInterface`そのインターフェイスを記述するタイプ ライブラリのマイナー バージョン番号と、既定のソース インターフェイス、LIBID と共にとメジャーのインターフェイス ID を提供できます。  
  
> [!NOTE]
>  正常に要求された情報を取得するには、この機能によって表されるオブジェクト`punkObj`を実装する必要があります`IDispatch`(によって型情報を返すと**が**) いずれかが実装する必要がありますも plus`IProvideClassInfo2`または`IPersist`です。 ソース インターフェイスの型情報の型情報と同じタイプ ライブラリにあります`IDispatch`します。  
  
### <a name="example"></a>例  
 次の例は、イベント シンク クラスを定義する方法を示しています。 `CEasySink`、に渡すことができるテンプレート引数の数を削減するため`IDispEventImpl`に、最低限必要です。 `EasyAdvise``EasyUnadvise`を使用して`AtlGetObjectSourceInterface`初期化するために、 [IDispEventImpl](../../atl/reference/idispeventimpl-class.md)メンバーを呼び出す前に[DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise)または[DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise)します。  
  
 [!code-cpp[NVC_ATL_Windowing #&93;](../../atl/codesnippet/cpp/composite-control-global-functions_1.h)]  
  
## <a name="see-also"></a>関連項目  
 [関数](../../atl/reference/atl-functions.md)   
 [複合コントロール マクロ](../../atl/reference/composite-control-macros.md)

