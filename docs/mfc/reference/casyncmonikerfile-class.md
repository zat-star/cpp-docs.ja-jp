---
title: "CAsyncMonikerFile クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::Close
- AFXOLE/CAsyncMonikerFile::GetBinding
- AFXOLE/CAsyncMonikerFile::GetFormatEtc
- AFXOLE/CAsyncMonikerFile::Open
- AFXOLE/CAsyncMonikerFile::CreateBindStatusCallback
- AFXOLE/CAsyncMonikerFile::GetBindInfo
- AFXOLE/CAsyncMonikerFile::GetPriority
- AFXOLE/CAsyncMonikerFile::OnDataAvailable
- AFXOLE/CAsyncMonikerFile::OnLowResource
- AFXOLE/CAsyncMonikerFile::OnProgress
- AFXOLE/CAsyncMonikerFile::OnStartBinding
- AFXOLE/CAsyncMonikerFile::OnStopBinding
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], asynchronous
- OLE controls [C++], asynchronous
- monikers [C++], MFC
- asynchronous controls [C++]
- CAsyncMonikerFile class
- IMoniker interface, binding
ms.assetid: 17378b66-a49a-4b67-88e3-7756ad26a2fc
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
ms.openlocfilehash: eb8727e6fe884c98fe010beab072fb7268f2e2c4
ms.lasthandoff: 02/24/2017

---
# <a name="casyncmonikerfile-class"></a>CAsyncMonikerFile クラス
ActiveX コントロール (以前の OLE コントロール) で非同期モニカーを使用するための機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CAsyncMonikerFile : public CMonikerFile  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAsyncMonikerFile::CAsyncMonikerFile](#casyncmonikerfile)|`CAsyncMonikerFile` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAsyncMonikerFile::Close](#close)|終了し、すべてのリソースを解放します。|  
|[CAsyncMonikerFile::GetBinding](#getbinding)|非同期転送バインドへのポインターを取得します。|  
|[CAsyncMonikerFile::GetFormatEtc](#getformatetc)|ストリーム内のデータの形式を取得します。|  
|[CAsyncMonikerFile::Open](#open)|非同期的にファイルを開きます。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAsyncMonikerFile::CreateBindStatusCallback](#createbindstatuscallback)|実装する COM オブジェクトを作成`IBindStatusCallback`します。|  
|[CAsyncMonikerFile::GetBindInfo](#getbindinfo)|OLE システム ライブラリを作成するバインドの種類に関する情報を要求によって呼び出されます。|  
|[CAsyncMonikerFile::GetPriority](#getpriority)|バインディングの優先順位を取得する OLE システム ライブラリによって呼び出されます。|  
|[CAsyncMonikerFile::OnDataAvailable](#ondataavailable)|非同期バインド操作中にクライアントに利用可能になったデータを提供するには、呼び出されます。|  
|[CAsyncMonikerFile::OnLowResource](#onlowresource)|リソースが少ないときに呼び出されます。|  
|[CAsyncMonikerFile::OnProgress](#onprogress)|データのダウンロード処理の進行状況を示すために呼び出されます。|  
|[CAsyncMonikerFile::OnStartBinding](#onstartbinding)|バインドが開始されたときに呼び出されます。|  
|[CAsyncMonikerFile::OnStopBinding](#onstopbinding)|非同期転送が停止したときに呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 派生した[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)からさらに派生した[関数](../../mfc/reference/colestreamfile-class.md)、`CAsyncMonikerFile`を使用して、 [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) URL から非同期的にファイルの読み込みを含む任意のデータ ストリームを非同期的にアクセスするインターフェイスです。 ファイルは、ActiveX コントロールのデータパス プロパティであることができます。  
  
 非同期モニカーは、ファイル転送中に、応答性の高いユーザー インターフェイスを提供するインターネット対応アプリケーションと ActiveX コントロールで、主に使用されます。 これの典型的な例は、使用する[関数](../../mfc/reference/cdatapathproperty-class.md)ActiveX コントロールの非同期プロパティを提供します。 `CDataPathProperty`オブジェクトは、時間のかかるプロパティ exchange 処理中に新しいデータの可用性を示すためにコールバックを取得して繰り返しです。  
  
 インターネット アプリケーションで非同期モニカーと ActiveX コントロールを使用する方法の詳細については、次の記事を参照してください。  
  
- [インターネット最初のステップ: 非同期モニカー](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
- [インターネット最初のステップ: ActiveX コントロール](../../mfc/activex-controls-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [関数](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 `CAsyncMonikerFile`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="casyncmonikerfile"></a>CAsyncMonikerFile::CAsyncMonikerFile  
 `CAsyncMonikerFile` オブジェクトを構築します。  
  
```  
CAsyncMonikerFile();
```  
  
### <a name="remarks"></a>コメント  
 作成することはできません、`IBindHost`インターフェイスです。 `IBindHost`指定した場合にのみ使用、**開く**メンバー関数。  
  
 詳細については、`IBindHost`インターフェイスを参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="close"></a>CAsyncMonikerFile::Close  
 この関数では、閉じ、すべてのリソースを解放します。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>コメント  
 開かれていないか既に閉じているかのファイルで呼び出すことができます。  
  
##  <a name="createbindstatuscallback"></a>CAsyncMonikerFile::CreateBindStatusCallback  
 実装する COM オブジェクトを作成`IBindStatusCallback`します。  
  
```  
virtual IUnknown* CreateBindStatusCallback(IUnknown* pUnkControlling);
```  
  
### <a name="parameters"></a>パラメーター  
 `pUnkControlling`  
 制御は、未知へのポインター (外側**IUnknown**) または**NULL**集計が使用されていない場合。  
  
### <a name="return-value"></a>戻り値  
 場合`pUnkControlling`は**NULL**、内部にポインターを返す**IUnknown** 、新しい COM オブジェクトをサポートする方法`IBindStatusCallback`します。 場合`pUnkControlling`は**NULL**へのポインターを返します、 **IUnknown**新しい COM オブジェクト サポート`IBindStatusCallback`します。  
  
### <a name="remarks"></a>コメント  
 `CAsyncMonikerFile`実装する COM オブジェクトが必要です`IBindStatusCallback`します。 MFC は、このようなオブジェクトを実装し、集約します。 オーバーライドできます`CreateBindStatusCallback`独自の COM オブジェクトを取得します。 COM オブジェクトは MFC 実装を呼び出すことによって集計できます`CreateBindStatusCallback`COM オブジェクトの制御"不明"とします。 使用して実装した COM オブジェクト、`CCmdTarget`制御不明なを使用して、COM サポートを取得できます**CCmdTarget::GetControllingUnknown**します。  
  
 呼び出して、COM オブジェクトを MFC 実装に委任できます代わりに、 **CreateBindStatusCallback (NULL)**します。  
  
 [CAsyncMonikerFile::Open](#open)呼び出し`CreateBindStatusCallback`します。  
  
 非同期モニカーおよび非同期のバインドの詳細については、次を参照してください。、[し](http://msdn.microsoft.com/library/ie/ms775060)インターフェイスと[非同期バインドする方法と記憶域作業](http://msdn.microsoft.com/library/windows/desktop/aa379152)します。 集計の詳細については、次を参照してください。[集計](http://msdn.microsoft.com/library/windows/desktop/ms686558)します。 次の&3; つすべてのトピックは、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getbindinfo"></a>CAsyncMonikerFile::GetBindInfo  
 非同期モニカーをバインドする方法を確認する非同期モニカーのクライアントから呼び出されます。  
  
```  
virtual DWORD GetBindInfo() const;  
```  
  
### <a name="return-value"></a>戻り値  
 設定を取得**し**します。 詳細については、`IBindStatusCallback`インターフェイスを参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、ストレージ メディア (ストリーム) を使用して、データ プッシュ モデルを使用して非同期へのバインドを設定します。 バインドの動作を変更する場合は、この関数をオーバーライドします。  
  
 これを行う理由の&1; つは、データ プッシュ モデルではなくデータ プル モデルを使用してバインドすることです。 データ プル モデルで、クライアントは、バインド操作をドライブし、モニカーは、読み取られるときにデータをクライアントのみ提供されます。 データ プッシュ モデルでは、モニカーは、バインドの非同期操作し、継続的に新しいデータがあるときにクライアントに通知します。  
  
##  <a name="getbinding"></a>CAsyncMonikerFile::GetBinding  
 非同期転送バインドへのポインターを取得するには、この関数を呼び出します。  
  
```  
IBinding* GetBinding() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`IBinding`非同期転送の開始時に提供されるインターフェイスです。 返します。 **NULL**何らかの理由で、転送を実行できない場合に非同期的にします。  
  
### <a name="remarks"></a>コメント  
 コントロールのデータ転送を使ってプロセスをこれにより、`IBinding`などと連動**IBinding::Abort**、 **IBinding::Pause**と**IBinding::Resume**します。  
  
 詳細については、`IBinding`インターフェイスを参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getformatetc"></a>CAsyncMonikerFile::GetFormatEtc  
 ストリーム内のデータの形式を取得するには、この関数を呼び出します。  
  
```  
FORMATETC* GetFormatEtc() const;  
```  
  
### <a name="return-value"></a>戻り値  
 Windows の構造体へのポインター [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)現在開いているストリーム。 返します。 **NULL**モニカーがバインドされていない場合、非同期ではない場合、または非同期操作が開始されていない場合。  
  
##  <a name="getpriority"></a>CAsyncMonikerFile::GetPriority  
 バインディング プロセスは、バインド操作のスレッドに与えられる優先度の受信が開始されると非同期モニカーのクライアントから呼び出されます。  
  
```  
virtual LONG GetPriority() const;  
```  
  
### <a name="return-value"></a>戻り値  
 非同期転送を行うを優先度です。 標準スレッドの優先順位フラグのいずれか: **THREAD_PRIORITY_ABOVE_NORMAL**、 **THREAD_PRIORITY_BELOW_NORMAL**、 **THREAD_PRIORITY_HIGHEST**、 **THREAD_PRIORITY_IDLE**、 **THREAD_PRIORITY_LOWEST**、 **THREAD_PRIORITY_NORMAL**、および**THREAD_PRIORITY_TIME_CRITICAL**します。 Windows の関数を参照してください[SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277)これらの値の詳細についてです。  
  
### <a name="remarks"></a>コメント  
 `GetPriority`呼び出さないで直接します。 **THREAD_PRIORITY_NORMAL**が既定の実装によって返されます。  
  
##  <a name="ondataavailable"></a>CAsyncMonikerFile::OnDataAvailable  
 非同期モニカーは、`OnDataAvailable`にデータをクライアントに提供して、使用可能になったら、非同期の中に、バインド操作します。  
  
```  
virtual void OnDataAvailable(DWORD dwSize, DWORD bscfFlag);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwSize`  
 バインドの開始時から使用可能なデータのバイト単位での累積時間。 データの量は、操作に関連していないまたは特定の量が利用できないことを示す、0 にすることができます。  
  
 *bscfFlag*  
 A **BSCF**列挙値。 次の値の&1; つ以上を指定できます。  
  
- **BSCF_FIRSTDATANOTIFICATION**最初の呼び出しを識別する`OnDataAvailable`操作が指定されたバインド。  
  
- **BSCF_INTERMEDIATEDATANOTIFICATION**に中間の呼び出しを識別する`OnDataAvailable`bind 操作をします。  
  
- **知らせる**最後の呼び出しを識別する`OnDataAvailable`bind 操作をします。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装は、何も行いません。 実装のサンプルについては、次の例を参照してください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWinInet&#5;](../../mfc/codesnippet/cpp/casyncmonikerfile-class_1.cpp)]  
  
##  <a name="onlowresource"></a>CAsyncMonikerFile::OnLowResource  
 リソースが少ないときに、モニカーによって呼び出されます。  
  
```  
virtual void OnLowResource();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装`GetBinding( )-> Abort( )`します。  
  
##  <a name="onprogress"></a>CAsyncMonikerFile::OnProgress  
 通常は、時間のかかる操作中に適切な間隔でこのバインド操作の現在の進行状況を表示するには、繰り返しモニカーによって呼び出されます。  
  
```  
virtual void OnProgress(
    ULONG ulProgress,  
    ULONG ulProgressMax,  
    ULONG ulStatusCode,  
    LPCTSTR szStatusText);
```  
  
### <a name="parameters"></a>パラメーター  
 `ulProgress`  
 示される予想される最大の基準としたバインド操作の現在の進行状況を示す`ulProgressMax`します。  
  
 `ulProgressMax`  
 予想最大値を示す`ulProgress`への呼び出しの間`OnProgress`この操作にします。  
  
 `ulStatusCode`  
 バインド操作の進行状況に関する追加情報を提供します。 有効な値から取得されます、`BINDSTATUS`列挙します。 指定できる値については、「解説」を参照してください。  
  
 `szStatusText`  
 値に応じて、現在の進行状況に関する情報`ulStatusCode`します。 指定できる値については、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 値の`ulStatusCode`(および`szStatusText`値ごとに) は。  
  
 **BINDSTATUS_FINDINGRESOURCE**  
 バインド操作では、オブジェクトにバインドされている記憶域を含むリソースを見つけることです。 `szStatusText`検索対象となるリソースの表示名を示します (たとえば、"www.microsoft.com") にします。  
  
 **BINDSTATUS_CONNECTING**  
 バインド操作にバインドされている記憶域、オブジェクトを保持するリソースに接続されています。 `szStatusText` (たとえば、IP アドレス) に接続されているリソースの表示名を提供します。  
  
 **BINDSTATUS_SENDINGREQUEST**  
 オブジェクトまたは記憶域にバインドされている、bind 操作が要求しています。 `szStatusText`オブジェクト (たとえば、ファイル名) の表示名を提供します。  
  
 **BINDSTATUS_REDIRECTING**  
 バインド操作は、データ ファイルの場所にリダイレクトされました。 `szStatusText`データの新しい場所の表示名を提供します。  
  
 **BINDSTATUS_USINGCACHEDCOPY**  
 バインド操作は、キャッシュされたコピーから、ストレージ、要求されたオブジェクトを取得しています。 The `szStatusText` is **NULL**.  
  
 **BINDSTATUS_BEGINDOWNLOADDATA**  
 バインド操作では、オブジェクトまたはにバインドされているストレージの受信を開始しました。 `szStatusText`データの場所の表示名を提供します。  
  
 **BINDSTATUS_DOWNLOADINGDATA**  
 バインド操作にバインドされている記憶域、オブジェクトを受信し続けます。 `szStatusText`データの場所の表示名を提供します。  
  
 **BINDSTATUS_ENDDOWNLOADDATA**  
 バインド操作は、オブジェクトにバインドされている記憶域を受信しました。 `szStatusText`データの場所の表示名を提供します。  
  
 **BINDSTATUS_CLASSIDAVAILABLE**  
 バインドされているオブジェクトのインスタンスが作成されるだけです。 `szStatusText`が必要な場合、クライアント、バインド操作をキャンセルする機会を許可する文字列の形式で新しいオブジェクトの CLSID を提供します。  
  
##  <a name="onstartbinding"></a>CAsyncMonikerFile::OnStartBinding  
 バインドが開始されるときにアクションを実行する派生クラスでオーバーライドします。  
  
```  
virtual void OnStartBinding();
```  
  
### <a name="remarks"></a>コメント  
 この関数は、モニカーによってコールバックされます。 既定の実装では、何も行われません。  
  
##  <a name="onstopbinding"></a>CAsyncMonikerFile::OnStopBinding  
 モニカー バインド操作の最後で呼び出されます。  
  
```  
virtual void OnStopBinding(HRESULT hresult, LPCTSTR szError);
```  
  
### <a name="parameters"></a>パラメーター  
 `hresult`  
 `HRESULT`つまりエラーまたは警告の値。  
  
 *szErrort*  
 エラーを説明する文字列。  
  
### <a name="remarks"></a>コメント  
 転送が停止したときにアクションを実行するには、この関数をオーバーライドします。 既定では、解放`IBinding`します。  
  
 詳細については、`IBinding`インターフェイスを参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="open"></a>CAsyncMonikerFile::Open  
 非同期的にファイルを開くには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL Open(
    LPCTSTR lpszURL,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    LPCTSTR lpszURL,
    IBindHost* pBindHost,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    IBindHost* pBindHost,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    LPCTSTR lpszURL,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    LPCTSTR lpszURL,
    IUnknown* pUnknown,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    IUnknown* pUnknown,
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszURL`  
 非同期的に開かれるファイルへのポインター。 有効な URL またはファイル名、ファイルができます。  
  
 `pError`  
 ファイルの例外へのポインター。 エラーが発生した場合、原因に設定されます。  
  
 `pMoniker`  
 非同期モニカー インターフェイスへのポインター`IMoniker`で取得できる、ドキュメントのモニカーの組み合わせである正確なモニカー **IOleClientSite::GetMoniker (** *OLEWHICHMK_CONTAINER* **)**、およびパス名から作成されたモニカーです。 コントロールは、このモニカーを使用して、バインドすることができますが、これは、コントロールを保存する必要がありますモニカーではありません。  
  
 *pBindHost*  
 ポインター、`IBindHost`可能性のある相対パス名からモニカーを作成するために使用するインターフェイスです。 バインド ホストが無効であるか、モニカーは行わない場合、呼び出し既定**オープン (** `lpszFileName` **、**`pError`**)**します。 詳細については、`IBindHost`インターフェイスを参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `pServiceProvider`  
 ポインター、`IServiceProvider`インターフェイスです。 サービス プロバイダーが正しくないか、またはサービスを提供する失敗したかどうかは`IBindHost`、呼び出しが既定で**オープン (** `lpszFileName` **、**`pError`**)**します。  
  
 *pUnknown*  
 ポインター、 **IUnknown**インターフェイスです。 場合`IServiceProvider`が見つかると、関数を検索するクエリ`IBindHost`します。 サービス プロバイダーが正しくないか、またはサービスを提供する失敗したかどうかは`IBindHost`、呼び出しが既定で**オープン (** `lpszFileName` **、**`pError`**)**します。  
  
### <a name="return-value"></a>戻り値  
 ファイルが正常に開かれている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この呼び出しは、バインディング プロセスを開始します。  
  
 URL またはファイルの名前を使用する、`lpszURL`パラメーター。 例:  
  
 [!code-cpp[NVC_MFCWinInet&6;](../../mfc/codesnippet/cpp/casyncmonikerfile-class_2.cpp)]  
  
 または  
  
 [!code-cpp[NVC_MFCWinInet&#7;](../../mfc/codesnippet/cpp/casyncmonikerfile-class_3.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CMonikerFile クラス](../../mfc/reference/cmonikerfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CMonikerFile クラス](../../mfc/reference/cmonikerfile-class.md)   
 [関数のクラス](../../mfc/reference/cdatapathproperty-class.md)

