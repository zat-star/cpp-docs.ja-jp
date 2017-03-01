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
- COleMessageFilter
dev_langs:
- C++
helpviewer_keywords:
- COleMessageFilter class
- OLE [C++], managing concurrency
- message filters [C++]
- OLE applications [C++], managing interactions
- OLE messages
- applications [OLE], managing interactions
- messages [C++], OLE
ms.assetid: b1fd1639-fac4-4fd0-bf17-15172deba13c
caps.latest.revision: 21
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
ms.openlocfilehash: d91ed300bb6cade5d804fe4a74dfe6cc2e4384fe
ms.lasthandoff: 02/24/2017

---
# <a name="colemessagefilter-class"></a>関数のクラス
OLE アプリケーション間の相互の要求を同時に管理します。  
  
## <a name="syntax"></a>構文  
  
```  
class COleMessageFilter : public CCmdTarget  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleMessageFilter::COleMessageFilter](#colemessagefilter)|`COleMessageFilter` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleMessageFilter::BeginBusyState](#beginbusystate)|アプリケーションをによって、ビジー状態にします。|  
|[COleMessageFilter::EnableBusyDialog](#enablebusydialog)|有効にし、呼び出し先のアプリケーションがビジー状態のときに表示されるダイアログ ボックスを無効にします。|  
|[COleMessageFilter::EnableNotRespondingDialog](#enablenotrespondingdialog)|有効にし、呼び出し先のアプリケーションが応答していないときに表示されるダイアログ ボックスを無効にします。|  
|[COleMessageFilter::EndBusyState](#endbusystate)|アプリケーションのビジー状態を終了します。|  
|[COleMessageFilter::OnMessagePending](#onmessagepending)|OLE 呼び出しが進行中は、メッセージを処理するためにフレームワークによって呼び出されます。|  
|[COleMessageFilter::Register](#register)|OLE システム Dll とメッセージ フィルターを登録します。|  
|[COleMessageFilter::Revoke](#revoke)|OLE システム Dll とメッセージ フィルターの登録を取り消します。|  
|[COleMessageFilter::SetBusyReply](#setbusyreply)|OLE の呼び出しに使用中のアプリケーションの応答を決定します。|  
|[COleMessageFilter::SetMessagePendingDelay](#setmessagependingdelay)|アプリケーションが OLE 呼び出しに対する応答を待つ時間を決定します。|  
|[COleMessageFilter::SetRetryReply](#setretryreply)|使用中のアプリケーションへの呼び出し元のアプリケーションの応答を決定します。|  
  
## <a name="remarks"></a>コメント  
 `COleMessageFilter`クラスはビジュアル編集サーバーとコンテナー アプリケーション、だけ OLE オートメーション アプリケーションで便利です。 呼び出されるサーバー アプリケーションでこのクラスは、他のコンテナー アプリケーションからの呼び出しか、取り消されたか、後で再試行できるように、アプリケーションを「ビジー」を使用できます。 このクラスは、呼び出し先のアプリケーションがビジー状態のときに、呼び出し元のアプリケーションで実行されるアクションを決定することもできます。  
  
 一般的な使用方法は、サーバー アプリケーションを呼び出して[BeginBusyState](#beginbusystate)と[EndBusyState](#endbusystate)した方が、ドキュメントまたはその他の OLE アクセス可能なオブジェクトを破棄するは危険です。 これらの呼び出しが行われた[CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle)ユーザー インターフェイスの更新中です。  
  
 既定では、`COleMessageFilter`アプリケーションが初期化されるときに、オブジェクトが割り当てられます。 取得できる[AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter)します。  
  
 これは高度なクラスです。頻度の低い、直接使用する必要があります。  
  
 詳細については、記事を参照してください。[サーバー: サーバーを実装する](../../mfc/servers-implementing-a-server.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleMessageFilter`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="a-namebeginbusystatea--colemessagefilterbeginbusystate"></a><a name="beginbusystate"></a>COleMessageFilter::BeginBusyState  
 この関数では、ビジー状態を開始します。  
  
```  
virtual void BeginBusyState();
```  
  
### <a name="remarks"></a>コメント  
 組み合わせて動作[EndBusyState](#endbusystate)をアプリケーションのビジー状態を制御します。 関数[SetBusyReply](#setbusyreply)呼び出し元アプリケーションのビジー状態のときに、アプリケーションの応答を決定します。  
  
 `BeginBusyState`と`EndBusyState`呼び出しをインクリメントおよびデクリメント、それぞれ、アプリケーションがビジー状態かどうかを決定するカウンター。 たとえば、2 回の呼び出しに`BeginBusyState`とに&1; 回の呼び出し`EndBusyState`ビジー状態になります。 呼び出す必要があるビジー状態をキャンセルする`EndBusyState`同じ回数`BeginBusyState`が呼び出されています。  
  
 既定では、フレームワーク、状態にビジー状態で実行するアイドル状態の処理中に[CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle)します。 アプリケーションの処理中に**ON_COMMANDUPDATEUI**アイドル処理が完了したら、通知、着信呼び出しが、後で処理されます。  
  
##  <a name="a-namecolemessagefiltera--colemessagefiltercolemessagefilter"></a><a name="colemessagefilter"></a>COleMessageFilter::COleMessageFilter  
 
          `COleMessageFilter` オブジェクトを作成します。  
  
```  
COleMessageFilter();
```  
  
##  <a name="a-nameenablebusydialoga--colemessagefilterenablebusydialog"></a><a name="enablebusydialog"></a>COleMessageFilter::EnableBusyDialog  
 有効にし、保留中のメッセージの遅延時間の有効期限が切れたときに表示されるダイアログ ボックスが無効になります (を参照してください[ビジー](#setretryreply)) OLE 呼び出し中にします。  
  
```  
void EnableBusyDialog(BOOL bEnableBusy = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bEnableBusy*  
 「ビジー」ダイアログ ボックスが有効になっているかどうかを指定します。  
  
##  <a name="a-nameenablenotrespondingdialoga--colemessagefilterenablenotrespondingdialog"></a><a name="enablenotrespondingdialog"></a>COleMessageFilter::EnableNotRespondingDialog  
 有効にし、キーボードまたはマウス メッセージが保留中の場合に表示される「応答なし」のダイアログ ボックスを無効にする OLE 中の呼び出しと呼び出しがタイムアウトしました。  
  
```  
void EnableNotRespondingDialog(BOOL bEnableNotResponding = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bEnableNotResponding*  
 「応答なし」のダイアログ ボックスが有効になっているかどうかを指定します。  
  
##  <a name="a-nameendbusystatea--colemessagefilterendbusystate"></a><a name="endbusystate"></a>COleMessageFilter::EndBusyState  
 この関数では、ビジー状態を終了します。  
  
```  
virtual void EndBusyState();
```  
  
### <a name="remarks"></a>コメント  
 組み合わせて動作[BeginBusyState](#beginbusystate)をアプリケーションのビジー状態を制御します。 関数[SetBusyReply](#setbusyreply)呼び出し元アプリケーションのビジー状態のときに、アプリケーションの応答を決定します。  
  
 `BeginBusyState`と`EndBusyState`呼び出しをインクリメントおよびデクリメント、それぞれ、アプリケーションがビジー状態かどうかを決定するカウンター。 たとえば、2 回の呼び出しに`BeginBusyState`とに&1; 回の呼び出し`EndBusyState`ビジー状態になります。 呼び出す必要があるビジー状態をキャンセルする`EndBusyState`同じ回数`BeginBusyState`が呼び出されています。  
  
 既定では、フレームワーク、状態にビジー状態で実行するアイドル状態の処理中に[CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle)します。 アプリケーションの処理中に`ON_UPDATE_COMMAND_UI`アイドル処理が完了したら通知を受信した呼び出しが処理されます。  
  
##  <a name="a-nameonmessagependinga--colemessagefilteronmessagepending"></a><a name="onmessagepending"></a>COleMessageFilter::OnMessagePending  
 OLE 呼び出しが進行中は、メッセージを処理するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnMessagePending(const MSG* pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 `pMsg`  
 保留中のメッセージへのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常に完了した場合はゼロ以外、それ以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 呼び出し元のアプリケーションが呼び出しの完了を待機している場合、フレームワーク`OnMessagePending`保留中のメッセージへのポインター。 既定では、フレームワークのディスパッチ`WM_PAINT`メッセージ、長い時間がかかっている呼び出し中にウィンドウの更新を実行できるようにします。  
  
 呼び出してメッセージ フィルターを登録する必要があります[登録](#register)前に、アクティブになることができます。  
  
##  <a name="a-nameregistera--colemessagefilterregister"></a><a name="register"></a>COleMessageFilter::Register  
 OLE システム Dll とメッセージ フィルターを登録します。  
  
```  
BOOL Register();
```  
  
### <a name="return-value"></a>戻り値  
 正常に完了した場合はゼロ以外、それ以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 システム Dll に登録されていないメッセージ フィルターの効果はありません。 通常、アプリケーションの初期化コードは、アプリケーションのメッセージ フィルターを登録します。 呼び出しによってプログラムが終了する前に、アプリケーションで登録されている他のメッセージ フィルターを取り消す必要があります[取り消す](#revoke)します。  
  
 フレームワークの既定のメッセージ フィルターが自動的に初期化時に登録され、終了時に失効します。  
  
##  <a name="a-namerevokea--colemessagefilterrevoke"></a><a name="revoke"></a>COleMessageFilter::Revoke  
 呼び出しによって実行される前の登録を取り消します[登録](#register)します。  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>コメント  
 メッセージ フィルターは、プログラムが終了する前に取り消す必要があります。  
  
 作成され、フレームワークによって自動的に登録されている、既定のメッセージ フィルターも自動的に失効します。  
  
##  <a name="a-namesetbusyreplya--colemessagefiltersetbusyreply"></a><a name="setbusyreply"></a>COleMessageFilter::SetBusyReply  
 この関数は、アプリケーションの"ビジー状態の応答です。"を設定します。  
  
```  
void SetBusyReply(SERVERCALL nBusyReply);
```  
  
### <a name="parameters"></a>パラメーター  
 *nBusyReply*  
 値、 `SERVERCALL` COMPOBJ で定義されている列挙します。H. 次の値のいずれかを取ります。  
  
- **SERVERCALL_ISHANDLED**アプリケーションは呼び出しを受け付けることができますが、特定の呼び出しの処理に失敗する可能性があります。  
  
- **SERVERCALL_REJECTED**アプリケーションおそらくできなく、呼び出しを処理します。  
  
- **SERVERCALL_RETRYLATER**アプリケーションが一時的に、状態では、呼び出しを処理できません。  
  
### <a name="remarks"></a>コメント  
 [BeginBusyState](#beginbusystate)と[EndBusyState](#endbusystate)関数は、アプリケーションのビジー状態を制御します。  
  
 アプリケーションがなってへの呼び出しでビジー状態`BeginBusyState`の最後の設定によって決定される値と共に OLE システム Dll からの呼び出しに応答して`SetBusyReply`します。 呼び出し元のアプリケーションでは、このビジー状態の応答を使って実行するアクションを決定します。  
  
 ビジー状態の応答は、既定では、 **SERVERCALL_RETRYLATER**します。 この応答を受け取った呼び出し元のアプリケーションをできるだけ早く呼び出しを再試行します。  
  
##  <a name="a-namesetmessagependingdelaya--colemessagefiltersetmessagependingdelay"></a><a name="setmessagependingdelay"></a>COleMessageFilter::SetMessagePendingDelay  
 呼び出し元のアプリケーションがこれ以上の操作を実行する前に呼び出し先のアプリケーションから応答を待つ時間を決定します。  
  
```  
void SetMessagePendingDelay(DWORD nTimeout = 5000);
```  
  
### <a name="parameters"></a>パラメーター  
 `nTimeout`  
 保留中のメッセージの遅延時間のミリ秒数。  
  
### <a name="remarks"></a>コメント  
 この機能と連携して機能する[ビジー](#setretryreply)します。  
  
##  <a name="a-namesetretryreplya--colemessagefiltersetretryreply"></a><a name="setretryreply"></a>COleMessageFilter::SetRetryReply  
 呼び出し先のアプリケーションからがビジー状態の応答を受け取ると、呼び出し元アプリケーションの動作を決定します。  
  
```  
void SetRetryReply(DWORD nRetryReply = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nRetryReply`  
 再試行間隔をミリ秒単位の数です。  
  
### <a name="remarks"></a>コメント  
 呼び出し先のアプリケーションでは、ビジー状態であることによって、呼び出し元のアプリケーションを待ってから、サーバーがビジー状態、今すぐを再試行するかを指定した間隔の後に再試行が不要になったことがあります。 呼び出しをキャンセルすることもできます。  
  
 呼び出し元の応答は、関数によって制御されます`SetRetryReply`と[SetMessagePendingDelay](#setmessagependingdelay)します。 `SetRetryReply`呼び出し元のアプリケーションを特定の呼び出しの再試行の間待機する時間を決定します。 `SetMessagePendingDelay`さらにアクションを実行する前に、サーバーからの応答の呼び出し元のアプリケーション待機する時間を決定します。  
  
 通常、既定値は、許容されを変更する必要はありません。 フレームワークは、呼び出しを再試行すべて`nRetryReply`呼び出しがまたは保留中のメッセージの遅延時間が経過するまでのミリ秒です。 値 0 を`nRetryReply`を指定の呼び出しの取り消しを即時再試行、および 1 を指定します。  
  
 保留中のメッセージの遅延が切れたとき、OLE「ビジー状態です ダイアログ ボックス」(を参照してください[COleBusyDialog](../../mfc/reference/colebusydialog-class.md)) が表示されるので、ユーザーがキャンセルまたは呼び出しを再試行して選択します。 呼び出す[EnableBusyDialog](#enablebusydialog)を有効にする、またはこのダイアログ ボックスを無効にします。  
  
 キーボードまたはマウス メッセージが保留中の場合、呼び出しと呼び出しの中にタイムアウトしました (保留中のメッセージの遅延時間を超えると)、「応答なし」のダイアログ ボックスが表示されます。 呼び出す[EnableNotRespondingDialog](#enablenotrespondingdialog)を有効にする、またはこのダイアログ ボックスを無効にします。 通常この問題の状態は、何らかの問題が発生し、ユーザーを待たことを示します。  
  
 ダイアログ ボックスが無効にすると、現在「再試行」の応答は常に使用ビジー状態のアプリケーションへの呼び出し。  
  
## <a name="see-also"></a>関連項目  
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)

