---
title: "CCmdTarget クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCmdTarget
dev_langs:
- C++
helpviewer_keywords:
- message maps, CCmdTarget base class
- command targets
- CCmdTarget class
- command routing, command targets
- targets, command
ms.assetid: 8883b132-2057-4ce0-a5f2-88979f8f2b13
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
ms.openlocfilehash: 0b5b7617f6b3d89e454e31c9f95b5d4455569114
ms.lasthandoff: 02/24/2017

---
# <a name="ccmdtarget-class"></a>CCmdTarget クラス
Microsoft Foundation Class ライブラリのメッセージ マップ アーキテクチャの基本クラス。  
  
## <a name="syntax"></a>構文  
  
```  
class CCmdTarget : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CCmdTarget::CCmdTarget](#ccmdtarget)|`CCmdTarget` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CCmdTarget::BeginWaitCursor](#beginwaitcursor)|砂時計カーソルを表示します。|  
|[CCmdTarget::DoOleVerb](#dooleverb)|実行する OLE 動詞によって指定されたアクションが発生します。|  
|[CCmdTarget::EnableAutomation](#enableautomation)|OLE オートメーションの使用、`CCmdTarget`オブジェクトです。|  
|[CCmdTarget::EnableConnections](#enableconnections)|接続ポイントよりもイベントの発生を使用できます。|  
|[CCmdTarget::EnableTypeLib](#enabletypelib)|オブジェクトのタイプ ライブラリを有効にします。|  
|[CCmdTarget::EndWaitCursor](#endwaitcursor)|以前のカーソルに戻ります。|  
|[CCmdTarget::EnumOleVerbs](#enumoleverbs)|オブジェクトの OLE 動詞を列挙します。|  
|[CCmdTarget::FromIDispatch](#fromidispatch)|ポインターを返す、`CCmdTarget`オブジェクトに関連付けられている、`IDispatch`ポインター。|  
|[CCmdTarget::GetDispatchIID](#getdispatchiid)|プライマリ ディスパッチ インターフェイス ID を取得します|  
|[CCmdTarget::GetIDispatch](#getidispatch)|ポインターを返す、`IDispatch`オブジェクトに関連付けられている、`CCmdTarget`オブジェクトです。|  
|[CCmdTarget::GetTypeInfoCount](#gettypeinfocount)|オブジェクトが提供する型情報インターフェイスの数を取得します。|  
|[CCmdTarget::GetTypeInfoOfGuid](#gettypeinfoofguid)|指定された GUID に対応する型の説明を取得します。|  
|[CCmdTarget::GetTypeLib](#gettypelib)|タイプ ライブラリへのポインターを取得します。|  
|[CCmdTarget::GetTypeLibCache](#gettypelibcache)|タイプ ライブラリのキャッシュを取得します。|  
|[CCmdTarget::IsInvokeAllowed](#isinvokeallowed)|オートメーション メソッドの呼び出しを有効にします。|  
|[CCmdTarget::IsResultExpected](#isresultexpected)|オートメーション関数の場合は&0; 以外を返します。 は、値を返す必要があります。|  
|[CCmdTarget::OnCmdMsg](#oncmdmsg)|ルーティングし、コマンドのメッセージをディスパッチします。|  
|[CCmdTarget::OnFinalRelease](#onfinalrelease)|OLE の最後の参照がリリース後にクリーンアップされます。|  
|[CCmdTarget::RestoreWaitCursor](#restorewaitcursor)|砂時計カーソルを復元します。|  
  
## <a name="remarks"></a>コメント  
 メッセージ マップは、それらを処理するためにメンバー関数にコマンドまたはメッセージをルーティングします。 (コマンドとは、アクセラレータ キー、コマンド ボタンまたはメニュー項目からのメッセージのことです)。  
  
 キー フレームワーク クラスから派生`CCmdTarget`含める[CView](../../mfc/reference/cview-class.md)、 [CWinApp](../../mfc/reference/cwinapp-class.md)、 [CDocument](../../mfc/reference/cdocument-class.md)、 [CWnd](../../mfc/reference/cwnd-class.md)、および[CFrameWnd](../../mfc/reference/cframewnd-class.md)します。 メッセージを処理する新しいクラスの場合は、次のいずれかからクラスを派生`CCmdTarget`-クラスを派生します。 クラスを派生させることはほとんどありませんは`CCmdTarget`直接します。  
  
 コマンド ターゲットの概要については、`OnCmdMsg`ルーティングを参照してください[コマンド ターゲット](../../mfc/command-targets.md)、[コマンド ルーティング](../../mfc/command-routing.md)、および[のメッセージの割り当て](../../mfc/mapping-messages.md)します。  
  
 `CCmdTarget`砂時計カーソルの表示を処理するメンバー関数が含まれます。 コマンドの実行にかなりの時間を要するが予想される場合は、砂時計カーソルを表示します。  
  
 ディスパッチ マップ、メッセージ マップに似た、OLE オートメーションを公開するため`IDispatch`機能します。 このインターフェイスを公開すると、その他のアプリケーション (Visual Basic の場合) などは、アプリケーションに呼び出すことができます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CCmdTarget`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="a-namebeginwaitcursora--ccmdtargetbeginwaitcursor"></a><a name="beginwaitcursor"></a>CCmdTarget::BeginWaitCursor  
 コマンドの実行にかなりの時間を要するが予想される場合は砂時計として表示するには、この関数を呼び出します。  
  
```  
void BeginWaitCursor();
```  
  
### <a name="remarks"></a>コメント  
 フレームワークがときなど、ビジー状態であるが、ユーザーを表示するには、この関数を呼び出す、 **CDocument**オブジェクトがファイルに保存したり読み込んだりできます。  
  
 アクション`BeginWaitCursor`常に反映されない&1; つのメッセージ ハンドラーの外部でその他のアクションとしてなど`OnSetCursor`カーソルに変更を処理する可能性があります。  
  
 呼び出す`EndWaitCursor`を以前のカーソルを復元します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&43;](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]  
  
##  <a name="a-nameccmdtargeta--ccmdtargetccmdtarget"></a><a name="ccmdtarget"></a>CCmdTarget::CCmdTarget  
 `CCmdTarget` オブジェクトを構築します。  
  
```  
CCmdTarget();
```  
  
##  <a name="a-namedooleverba--ccmdtargetdooleverb"></a><a name="dooleverb"></a>CCmdTarget::DoOleVerb  
 実行する OLE 動詞によって指定されたアクションが発生します。  
  
```  
BOOL DoOleVerb(
    LONG iVerb,  
    LPMSG lpMsg,  
    HWND hWndParent,  
    LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `iVerb`  
 動詞の数値識別子です。  
  
 `lpMsg`  
 ポインター、 [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958) (ダブルクリック) などの動詞を呼び出したイベントを記述する構造体。  
  
 `hWndParent`  
 オブジェクトを保持しているドキュメント ウィンドウのハンドル。  
  
 `lpRect`  
 ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)オブジェクトの定義 (ピクセル単位) の座標を持つ外接する四角形で*hwndParent*します。  
  
### <a name="return-value"></a>戻り値  
 TRUE の場合は成功しましたが、それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、の実装では基本的に[IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508)します。 実行可能なアクションによって列挙[CCmdTarget::EnumOleVerbs](#enumoleverbs)します。  
  
##  <a name="a-nameenableautomationa--ccmdtargetenableautomation"></a><a name="enableautomation"></a>CCmdTarget::EnableAutomation  
 オブジェクトの OLE オートメーションを有効にするには、この関数を呼び出します。  
  
```  
void EnableAutomation();
```  
  
### <a name="remarks"></a>コメント  
 この関数は、通常は、オブジェクトのコンス トラクターから呼び出され、クラスのディスパッチ マップが宣言されている場合にのみ呼び出す必要があります。 オートメーションの詳細については、記事を参照してください。[オートメーション クライアント](../../mfc/automation-clients.md)と[オートメーション サーバー](../../mfc/automation-servers.md)します。  
  
##  <a name="a-nameenableconnectionsa--ccmdtargetenableconnections"></a><a name="enableconnections"></a>CCmdTarget::EnableConnections  
 接続ポイントよりもイベントの発生を使用できます。  
  
```  
void EnableConnections();
```  
  
### <a name="remarks"></a>コメント  
 コネクション ポイントを有効にするには、派生クラスのコンス トラクターでこのメンバー関数を呼び出します。  
  
##  <a name="a-nameenabletypeliba--ccmdtargetenabletypelib"></a><a name="enabletypelib"></a>CCmdTarget::EnableTypeLib  
 オブジェクトのタイプ ライブラリを有効にします。  
  
```  
void EnableTypeLib();
```  
  
### <a name="remarks"></a>コメント  
 コンス トラクターでこのメンバー関数を呼び出して、`CCmdTarget`の型情報を提供する場合は、オブジェクトを派生します。 詳細については、サポート技術情報記事 Q185720 を参照してください"HOWTO: MFC オートメーション サーバーから型情報を入力します。"。 サポート技術情報の記事は、MSDN ライブラリの Visual Studio のドキュメントで使用可能な[http://support.microsoft.com](http://support.microsoft.com/)します。  
  
##  <a name="a-nameendwaitcursora--ccmdtargetendwaitcursor"></a><a name="endwaitcursor"></a>CCmdTarget::EndWaitCursor  
 呼び出した後に、この関数を呼び出して、`BeginWaitCursor`砂時計カーソルから以前のカーソルに戻すためのメンバー関数。  
  
```  
void EndWaitCursor();
```  
  
### <a name="remarks"></a>コメント  
 砂時計カーソルを呼び出した後、フレームワークもこのメンバー関数を呼び出します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&43;](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]  
  
##  <a name="a-nameenumoleverbsa--ccmdtargetenumoleverbs"></a><a name="enumoleverbs"></a>CCmdTarget::EnumOleVerbs  
 オブジェクトの OLE 動詞を列挙します。  
  
```  
BOOL EnumOleVerbs(LPENUMOLEVERB* ppenumOleVerb);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppenumOleVerb`  
 ポインターへのポインター、[返します](http://msdn.microsoft.com/library/windows/desktop/ms695084)インターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 オブジェクトは、少なくとも&1; つの OLE 動詞をサポートしている場合 (その場合\*`ppenumOleVerb`を指す、**返します**列挙子インターフェイス)、それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、の実装では基本的に[IOleObject::EnumVerbs](http://msdn.microsoft.com/library/windows/desktop/ms692781)します。  
  
##  <a name="a-namefromidispatcha--ccmdtargetfromidispatch"></a><a name="fromidispatch"></a>CCmdTarget::FromIDispatch  
 マップするには、この関数を呼び出して、`IDispatch`ポインター、オートメーション メンバー関数、クラスから受信した、`CCmdTarget`のインターフェイスを実装するオブジェクト、`IDispatch`オブジェクトです。  
  
```  
static CCmdTarget* PASCAL FromIDispatch(LPDISPATCH lpDispatch);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpDispatch`  
 `IDispatch` オブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CCmdTarget`オブジェクトに関連付けられている`lpDispatch`します。 この関数が返す**NULL**場合、`IDispatch`オブジェクトは、Microsoft Foundation Class としては認識されません`IDispatch`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 この関数の結果はメンバー関数への呼び出しの逆`GetIDispatch`します。  
  
##  <a name="a-namegetdispatchiida--ccmdtargetgetdispatchiid"></a><a name="getdispatchiid"></a>CCmdTarget::GetDispatchIID  
 プライマリ ディスパッチ インターフェイス ID を取得します  
  
```  
virtual BOOL GetDispatchIID(IID* pIID);
```  
  
### <a name="parameters"></a>パラメーター  
 *pIID*  
 インターフェイス ID へのポインター (、 [GUID](http://msdn.microsoft.com/library/windows/desktop/aa373931))。  
  
### <a name="return-value"></a>戻り値  
 TRUE の場合は成功しましたが、それ以外の場合は FALSE。 成功した場合、 \* *pIID*プライマリ ディスパッチ インターフェイスの ID に設定されています。  
  
### <a name="remarks"></a>コメント  
 派生クラスは、このメンバー関数をオーバーライドする必要があります (オーバーライドされなかった場合、 `GetDispatchIID` FALSE を返します)。 参照してください[COleControl](../../mfc/reference/colecontrol-class.md)します。  
  
 詳細については、サポート技術情報記事 Q185720 を参照してください"HOWTO: MFC オートメーション サーバーから型情報を入力します。"。 サポート技術情報の記事は、MSDN ライブラリの Visual Studio のドキュメントで使用可能な[http://support.microsoft.com](http://support.microsoft.com/)します。  
  
##  <a name="a-namegetidispatcha--ccmdtargetgetidispatch"></a><a name="getidispatch"></a>CCmdTarget::GetIDispatch  
 取得するには、このメンバー関数を呼び出す、`IDispatch`ポインター オートメーション メソッドからはどちらかが返されます、`IDispatch`ポインターまたはでは、`IDispatch`ポインターの参照をします。  
  
```  
LPDISPATCH GetIDispatch(BOOL bAddRef);
```  
  
### <a name="parameters"></a>パラメーター  
 *bAddRef*  
 オブジェクトの参照カウントをインクリメントするかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 `IDispatch`オブジェクトに関連付けられたポインター。  
  
### <a name="remarks"></a>コメント  
 オブジェクトを呼び出す`EnableAutomation`この関数がの基礎クラスの実装にポインターを返すため、オートメーションを有効にすると、そのコンス トラクターで`IDispatch`経由で通信するクライアントで使用されている、`IDispatch`インターフェイスです。 呼び出しを作成する必要はありませんので、ポインターへの参照を追加する自動的にこの関数を呼び出す[:addref](http://msdn.microsoft.com/library/windows/desktop/ms691379)します。  
  
##  <a name="a-namegettypeinfocounta--ccmdtargetgettypeinfocount"></a><a name="gettypeinfocount"></a>CCmdTarget::GetTypeInfoCount  
 オブジェクトが提供する型情報インターフェイスの数を取得します。  
  
```  
virtual UINT GetTypeInfoCount();
```  
  
### <a name="return-value"></a>戻り値  
 型情報インターフェイスの数。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は基本的には、実装[IDispatch::GetTypeInfoCount](http://msdn.microsoft.com/en-us/da876d53-cb8a-465c-a43e-c0eb272e2a12)します。  
  
 派生クラスでは、(0 または 1) を提供する型情報インターフェイスの数を取得するには、この関数をオーバーライドする必要があります。 オーバーライドされなかった場合、**しなかった**0 を返します。 をオーバーライドするを使用して、 [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib)も実装されているマクロ`GetTypeLib`と`GetTypeLibCache`です。  
  
##  <a name="a-namegettypeinfoofguida--ccmdtargetgettypeinfoofguid"></a><a name="gettypeinfoofguid"></a>CCmdTarget::GetTypeInfoOfGuid  
 指定された GUID に対応する型の説明を取得します。  
  
```  
HRESULT GetTypeInfoOfGuid(
    LCID lcid,  
    const GUID& guid,  
    LPTYPEINFO* ppTypeInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `lcid`  
 ロケール識別子 ( `LCID`)。  
  
 `guid`  
 [GUID](http://msdn.microsoft.com/library/windows/desktop/aa373931)の種類の説明。  
  
 `ppTypeInfo`  
 ポインターへのポインター、`ITypeInfo`インターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合または呼び出しの失敗を示す HRESULT。 成功した場合、*`ppTypeInfo`型情報インターフェイスをポイントします。  
  
##  <a name="a-namegettypeliba--ccmdtargetgettypelib"></a><a name="gettypelib"></a>CCmdTarget::GetTypeLib  
 タイプ ライブラリへのポインターを取得します。  
  
```  
virtual HRESULT GetTypeLib(
    LCID lcid,  
    LPTYPELIB* ppTypeLib);
```  
  
### <a name="parameters"></a>パラメーター  
 `lcid`  
 ロケール識別子 ( `LCID`)。  
  
 `ppTypeLib`  
 ポインターへのポインター、`ITypeLib`インターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合または呼び出しの失敗を示す HRESULT。 成功した場合、*`ppTypeLib`タイプ ライブラリ インターフェイスをポイントします。  
  
### <a name="remarks"></a>コメント  
 派生クラスは、このメンバー関数をオーバーライドする必要があります (オーバーライドされなかった場合、 `GetTypeLib` TYPE_E_CANTLOADLIBRARY を返します)。 使用して、 [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib)も実装されているマクロ`GetTypeInfoCount`と`GetTypeLibCache`です。  
  
##  <a name="a-namegettypelibcachea--ccmdtargetgettypelibcache"></a><a name="gettypelibcache"></a>CCmdTarget::GetTypeLibCache  
 タイプ ライブラリのキャッシュを取得します。  
  
```  
virtual CTypeLibCache* GetTypeLibCache();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 **CTypeLibCache**オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 派生クラスは、このメンバー関数をオーバーライドする必要があります (オーバーライドされなかった場合、**によりオーバーライド**NULL が返されます)。 使用して、 [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib)も実装されているマクロ`GetTypeInfoCount`と`GetTypeLib`です。  
  
##  <a name="a-nameisinvokealloweda--ccmdtargetisinvokeallowed"></a><a name="isinvokeallowed"></a>CCmdTarget::IsInvokeAllowed  
 この関数は mfc の**idispatch::invoke**場合、指定されたオートメーション メソッド (で識別される`dispid`) 呼び出すことができます。  
  
```  
virtual BOOL IsInvokeAllowed(DISPID dispid);
```  
  
### <a name="parameters"></a>パラメーター  
 `dispid`  
 ディスパッチの id。  
  
### <a name="return-value"></a>戻り値  
 TRUE の場合、メソッドを起動できることができます。  
  
### <a name="remarks"></a>コメント  
 場合`IsInvokeAllowed`TRUE を返します。 **Invoke**メソッドを呼び出しますそれ以外の場合、`Invoke`は失敗すると、E_UNEXPECTED を返します。  
  
 派生クラスは、適切な値を返すには、この関数をオーバーライドして (オーバーライドされなかった場合、`IsInvokeAllowed`に TRUE を返します)。 具体的にを参照してください[COleControl::IsInvokeAllowed](../../mfc/reference/colecontrol-class.md#isinvokeallowed)します。  
  
##  <a name="a-nameisresultexpecteda--ccmdtargetisresultexpected"></a><a name="isresultexpected"></a>CCmdTarget::IsResultExpected  
 使用`IsResultExpected`をクライアントがオートメーション関数の呼び出しからの戻り値を求めているかどうかを確認します。  
  
```  
BOOL IsResultExpected();
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、オートメーション関数が値を返す必要があります。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 OLE インターフェイスは、MFC にクライアントを使用してまたは関数の呼び出しの結果を無視するかどうかについての情報を提供し、MFC 順番に使用してこの情報への呼び出しの結果を確認する`IsResultExpected`です。 戻り値の生産が時間、またはリソースを消費するの場合、戻り値を計算する前にこの関数を呼び出すことによって効率が向上します。  
  
 呼び出す場合に、オートメーション関数を他のオートメーション機能から有効な戻り値を取得ができるようにクライアントによって呼び出された後にのみ、この関数は 0 を返します。  
  
 `IsResultExpected`オートメーション関数呼び出しが実行されていないときに呼び出された場合は、0 以外の値を返します。  
  
##  <a name="a-nameoncmdmsga--ccmdtargetoncmdmsg"></a><a name="oncmdmsg"></a>CCmdTarget::OnCmdMsg  
 コマンド メッセージをディスパッチするため、コマンドのユーザー インターフェイス オブジェクトの更新を処理するために framework によって呼び出されます。  
  
```  
virtual BOOL OnCmdMsg(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 コマンド ID が含まれます  
  
 `nCode`  
 コマンド通知コードを識別します。 参照してください**解説**の値の詳細については詳細`nCode`します。  
  
 `pExtra`  
 値に従って使用`nCode`します。 参照してください**解説**の詳細については`pExtra`です。  
  
 `pHandlerInfo`  
 かどうか**NULL**、`OnCmdMsg`を入力、 **pTarget**と**pmf**のメンバー、`pHandlerInfo`ディスパッチ コマンドではなく構造体。 通常、このパラメーターに指定する必要があります**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 メッセージが処理された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 これは、フレームワーク コマンド アーキテクチャのメイン実装ルーチンです。  
  
 実行時に`OnCmdMsg`ルート クラスを呼び出すことによって、コマンド自体を取り扱う他のオブジェクトへのコマンドをディスパッチ`CCmdTarget::OnCmdMsg`、これは実際のメッセージ マップ検索します。 既定のコマンド ルーティングの詳細については、次を参照してください。[メッセージの処理とマップ」](../../mfc/message-handling-and-mapping.md)します。  
  
 ごくまれに、フレームワークを拡張するには、このメンバー関数を無効にすることがあります標準コマンド ルーティングします。 参照してください[テクニカル ノート 21](../../mfc/tn021-command-and-message-routing.md)コマンド ルーティングのアーキテクチャの詳細についてです。  
  
 オーバーライドする場合は`OnCmdMsg`、適切な値を指定する必要があります`nCode`、コマンドの通知コードと`pExtra`の値に依存する`nCode`です。 次の表に、対応する値を示します。  
  
|`nCode` の値|`pExtra` の値|  
|-------------------|--------------------|  
|CN_COMMAND|[CCmdUI](../../mfc/reference/ccmdui-class.md)*|  
|CN_EVENT|AFX_EVENT *|  
|CN_UPDATE_COMMAND_UI|CCmdUI *|  
|CN_OLECOMMAND|[COleCmdUI](../../mfc/reference/colecmdui-class.md)*|  
|CN_OLE_UNREGISTER|NULL|  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&44;](../../mfc/codesnippet/cpp/ccmdtarget-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #&45;](../../mfc/codesnippet/cpp/ccmdtarget-class_3.cpp)]  
  
##  <a name="a-nameonfinalreleasea--ccmdtargetonfinalrelease"></a><a name="onfinalrelease"></a>CCmdTarget::OnFinalRelease  
 OLE の最後の参照オブジェクト間のリリース時に、フレームワークによって呼び出されます。  
  
```  
virtual void OnFinalRelease();
```  
  
### <a name="remarks"></a>コメント  
 この状況に特別な処理を提供するには、この関数をオーバーライドします。 既定の実装では、オブジェクトを削除します。  
  
##  <a name="a-namerestorewaitcursora--ccmdtargetrestorewaitcursor"></a><a name="restorewaitcursor"></a>CCmdTarget::RestoreWaitCursor  
 (たとえば、終了後、メッセージ ボックスが開き、時間のかかる操作の途中で終了し、)、システムのカーソルが変更された後に、適切な砂時計カーソルを復元するには、この関数を呼び出します。  
  
```  
void RestoreWaitCursor();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&43;](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル ACDUAL](../../visual-cpp-samples.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CCmdUI クラス](../../mfc/reference/ccmdui-class.md)   
 [CDocument クラス](../../mfc/reference/cdocument-class.md)   
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)   
 [CWinApp クラス](../../mfc/reference/cwinapp-class.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [CView クラス](../../mfc/reference/cview-class.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)   
 [ディスパッチ クラス](../../mfc/reference/coledispatchdriver-class.md)

