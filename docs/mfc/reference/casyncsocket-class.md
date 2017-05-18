---
title: "CAsyncSocket クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAsyncSocket
- AFXSOCK/CAsyncSocket
- AFXSOCK/CAsyncSocket::CAsyncSocket
- AFXSOCK/CAsyncSocket::Accept
- AFXSOCK/CAsyncSocket::AsyncSelect
- AFXSOCK/CAsyncSocket::Attach
- AFXSOCK/CAsyncSocket::Bind
- AFXSOCK/CAsyncSocket::Close
- AFXSOCK/CAsyncSocket::Connect
- AFXSOCK/CAsyncSocket::Create
- AFXSOCK/CAsyncSocket::Detach
- AFXSOCK/CAsyncSocket::FromHandle
- AFXSOCK/CAsyncSocket::GetLastError
- AFXSOCK/CAsyncSocket::GetPeerName
- AFXSOCK/CAsyncSocket::GetPeerNameEx
- AFXSOCK/CAsyncSocket::GetSockName
- AFXSOCK/CAsyncSocket::GetSockNameEx
- AFXSOCK/CAsyncSocket::GetSockOpt
- AFXSOCK/CAsyncSocket::IOCtl
- AFXSOCK/CAsyncSocket::Listen
- AFXSOCK/CAsyncSocket::Receive
- AFXSOCK/CAsyncSocket::ReceiveFrom
- AFXSOCK/CAsyncSocket::ReceiveFromEx
- AFXSOCK/CAsyncSocket::Send
- AFXSOCK/CAsyncSocket::SendTo
- AFXSOCK/CAsyncSocket::SendToEx
- AFXSOCK/CAsyncSocket::SetSockOpt
- AFXSOCK/CAsyncSocket::ShutDown
- AFXSOCK/CASyncSocket::Socket
- AFXSOCK/CAsyncSocket::OnAccept
- AFXSOCK/CAsyncSocket::OnClose
- AFXSOCK/CAsyncSocket::OnConnect
- AFXSOCK/CAsyncSocket::OnOutOfBandData
- AFXSOCK/CAsyncSocket::OnReceive
- AFXSOCK/CAsyncSocket::OnSend
- AFXSOCK/CAsyncSocket::m_hSocket
dev_langs:
- C++
helpviewer_keywords:
- network communications
- asynchronous Windows Sockets
- CAsyncSocket class
- Windows Sockets [C++], asynchronous
- communications [C++], network
- sockets [C++], Windows
ms.assetid: cca4d5a1-aa0f-48bd-843e-ef0e2d7fc00b
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c7a175fc12146d98becc5d06f80e975df5b5a008
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="casyncsocket-class"></a>CAsyncSocket クラス
Windows ソケットを表します。-ネットワーク通信のエンドポイント。  
  
## <a name="syntax"></a>構文  
  
```  
class CAsyncSocket : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAsyncSocket::CAsyncSocket](#casyncsocket)|`CAsyncSocket` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAsyncSocket::Accept](#accept)|ソケットで接続を受け入れます。|  
|[CAsyncSocket::AsyncSelect](#asyncselect)|ソケットのイベント通知を要求します。|  
|[CAsyncSocket::Attach](#attach)|ソケットのハンドルをアタッチ、`CAsyncSocket`オブジェクトです。|  
|[CAsyncSocket::Bind](#bind)|ソケットをローカル アドレスを関連付けます。|  
|[CAsyncSocket::Close](#close)|ソケットを閉じます。|  
|[不要なため](#connect)|ピア ソケットへの接続を確立します。|  
|[CAsyncSocket::Create](#create)|ソケットを作成します。|  
|[CAsyncSocket::Detach](#detach)|ソケットのハンドルからのデタッチ、`CAsyncSocket`オブジェクトです。|  
|[CAsyncSocket::FromHandle](#fromhandle)|ポインターを返す、`CAsyncSocket`オブジェクト、ソケットのハンドルを指定します。|  
|[CAsyncSocket::GetLastError](#getlasterror)|失敗した最後の操作のエラー状態を取得します。|  
|[で](#getpeername)|ソケットが接続されているピア ソケットのアドレスを取得します。|  
|[CAsyncSocket::GetPeerNameEx](#getpeernameex)|ソケットが接続されている (ハンドルの IPv6 アドレス) をピア ソケットのアドレスを取得します。|  
|[で](#getsockname)|ソケットのローカル名を取得します。|  
|[CAsyncSocket::GetSockNameEx](#getsocknameex)|ソケット (ハンドルの IPv6 アドレス) のローカル名を取得します。|  
|[CAsyncSocket::GetSockOpt](#getsockopt)|ソケット オプションを取得します。|  
|[CAsyncSocket::IOCtl](#ioctl)|ソケットのモードを制御します。|  
|[CAsyncSocket::Listen](#listen)|接続要求をリッスンするソケットを確立します。|  
|[CAsyncSocket::Receive](#receive)|ソケットからデータを受信します。|  
|[で](#receivefrom)|データグラムを受信し、送信元アドレスを格納します。|  
|[CAsyncSocket::ReceiveFromEx](#receivefromex)|データグラムを受信し、送信元アドレス (IPv6 アドレスのハンドル) を格納します。|  
|[CAsyncSocket::Send](#send)|接続されたソケットにデータを送信します。|  
|[で](#sendto)|データを特定の宛先に送信します。|  
|[CAsyncSocket::SendToEx](#sendtoex)|特定の宛先 (ハンドルの IPv6 アドレス) にデータを送信します。|  
|[CAsyncSocket::SetSockOpt](#setsockopt)|ソケット オプションを設定します。|  
|[CAsyncSocket::ShutDown](#shutdown)|無効に**送信**や**受信**ソケットでを呼び出します。|  
|[CASyncSocket::Socket](#socket)|ソケットのハンドルを割り当てます。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAsyncSocket::OnAccept](#onaccept)|呼び出すことによって保留中の接続要求を受け付けられる待機中のソケットに通知**Accept**します。|  
|[CAsyncSocket::OnClose](#onclose)|ソケットが接続されているソケットが閉じに通知します。|  
|[CAsyncSocket::OnConnect](#onconnect)|接続試行が完了した、かどうかが正常にまたはエラーが発生しているソケットに通知します。|  
|[CAsyncSocket::OnOutOfBandData](#onoutofbanddata)|帯域外の緊急のメッセージでは通常、ソケットで読み取るデータが受信側のソケットに通知します。|  
|[CAsyncSocket::OnReceive](#onreceive)|待機中のソケットを呼び出すことによって取得するデータがあることを通知**受信**します。|  
|[CAsyncSocket::OnSend](#onsend)|ソケットに呼び出すことによってデータを送信できることを通知**送信**します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAsyncSocket::operator =](#operator_eq)|新しい値を代入する`CAsyncSocket`オブジェクトです。|  
|[CAsyncSocket::operator ソケット](#operator_socket)|この演算子を使用して取得する、**ソケット**の処理、`CAsyncSocket`オブジェクトです。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAsyncSocket::m_hSocket](#m_hsocket)|示す、**ソケット**ハンドルは、これに接続されている`CAsyncSocket`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 クラス`CAsyncSocket`MFC と組み合わせて Windows ソケットを使用するプログラマのオブジェクト指向の抽象化を提供する、Windows ソケット関数 API をカプセル化します。  
  
 このクラスは、ネットワーク通信を理解していることを前提に基づいています。 ブロック、バイト順の相違点の処理を担当し、Unicode とマルチバイト文字の間の変換が文字列 (MBCS) 文字列を設定します。 これらの問題を管理する方が便利インターフェイスを実行する場合に、クラスを参照してください。 [CSocket](../../mfc/reference/csocket-class.md)します。  
  
 使用する、`CAsyncSocket`オブジェクト、そのコンス トラクターを呼び出す物書き、[作成](#create)を基になるソケット ハンドルを作成する関数 (型`SOCKET`)、ソケットが受け入れられている場合は除きます。 サーバー ソケットの呼び出しの[リッスン](#listen)メンバー関数、およびクライアント ソケットの呼び出しに対して、[接続](#connect)メンバー関数。 サーバー ソケットを呼び出す必要があります、 [Accept](#accept)接続要求を受け取った関数です。 残りの使用`CAsyncSocket`ソケットの間の通信を行う関数。 完了すると、破棄、`CAsyncSocket`オブジェクト ヒープで作成された場合は、デストラクターが自動的に呼び出します、[閉じる](#close)関数です。 `SOCKET`データ型は、記事で説明されて[Windows ソケット: バック グラウンド](../../mfc/windows-sockets-background.md)します。  
  
> [!NOTE]
>  静的にリンクされた MFC アプリケーションのセカンダリ スレッドで MFC ソケットを使用する場合を呼び出す必要があります`AfxSocketInit`ソケット ライブラリを初期化するソケットを使用する各スレッドにします。 既定では、`AfxSocketInit`はプライマリ スレッドでのみ呼び出されます。  
  
 詳細については、次を参照してください。 [Windows ソケット: を使用してクラス CAsyncSocket](../../mfc/windows-sockets-using-class-casyncsocket.md) 、関連する記事、だけでなく[Windows Sockets 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CAsyncSocket`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxsock.h  
  
##  <a name="accept"></a>CAsyncSocket::Accept  
 ソケットで接続を許可するには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL Accept(
    CAsyncSocket& rConnectedSocket,  
    SOCKADDR* lpSockAddr = NULL,  
    int* lpSockAddrLen = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `rConnectedSocket`  
 接続に使用される新しいソケットを識別する参照。  
  
 `lpSockAddr`  
 ポインター、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)接続のアドレスを受け取るソケット、ネットワーク上で認知されています。 正確な形式、`lpSockAddr`引数は、ソケットが作成されたときに確立されたアドレス ファミリによって決定されます。 場合`lpSockAddr`や`lpSockAddrLen`に等しい**NULL**、受け入れられたソケットのリモート アドレスに関する情報は返されません。  
  
 `lpSockAddrLen`  
 指定されたアドレスの長さへのポインター `lpSockAddr` (バイト単位)。 `lpSockAddrLen`値結果パラメーター: 指す領域の量を含める必要があります最初に`lpSockAddr`; 返された場合に返されるアドレスの実際の長さ (単位: バイト) が含まれます。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**正常な[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことを検出します。  
  
- **WSAEFAULT** 、`lpSockAddrLen`引数が小さすぎる (のサイズよりも小さいか、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)構造) です。  
  
- **WSAEINPROGRESS** Windows ソケットのブロッキング呼び出しが進行中です。  
  
- **WSAEINVAL** `Listen`が呼び出される前にそのまま使用します。  
  
- **WSAEMFILE**キューが受け入れるように入ったときに空で利用可能な記述子がないです。  
  
- `WSAENOBUFS`バッファー領域がありません。  
  
- **切り離します**記述子がソケットではありません。  
  
- **WSAEOPNOTSUPP**参照先のソケットが接続指向のサービスをサポートする型ではありません。  
  
- **とき**ソケットがマークされている非ブロッキング接続が許容されるために存在しません。  
  
### <a name="remarks"></a>コメント  
 このルーチンは、接続待ちのキューの最初の接続を抽出し、このソケットと同じプロパティを持つ新しいソケットを作成し、それにアタッチ`rConnectedSocket`します。 キューに保留中の接続がない場合**Accept**は&0; を返しますと`GetLastError`エラーが返されます。 受け入れられたソケット ( *rConnectedSocket)*をより多くの接続を受け入れるように使用することはできません。 元のソケットでは、オープンで、リスナーは残ります。  
  
 引数`lpSockAddr`ソケット接続のアドレスを使用して読み込まれた結果のパラメーターは、通信レイヤーに認識されています。 **そのまま使用**など、接続ベースのソケットの種類と組み合わせて、 **SOCK_STREAM**します。  
  
##  <a name="asyncselect"></a>CAsyncSocket::AsyncSelect  
 このメンバー関数を呼び出して、ソケットのイベント通知を要求します。  
  
```  
BOOL AsyncSelect(long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `lEvent`  
 アプリケーションが関心があるネットワーク イベントの組み合わせを指定するビットマスクです。  
  
- **FD_READ**読み取り用の準備完了の通知を受信します。  
  
- **FD_WRITE**データが読み取り可能な場合に通知を受信します。  
  
- **FD_OOB**の帯域外のデータの追加の通知を受信します。  
  
- **FD_ACCEPT**着信接続の通知を受信します。  
  
- **FD_CONNECT**接続の結果の通知を受信します。  
  
- **FD_CLOSE**ピアでソケットが閉じられると、通知を受信します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**正常な[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことを検出します。  
  
- **WSAEINVAL**有効な指定されたパラメーターのいずれかがないことを示します。  
  
- **WSAEINPROGRESS** Windows ソケットのブロック操作が進行中です。  
  
### <a name="remarks"></a>コメント  
 この関数は、ソケットの MFC コールバック通知関数を呼び出すは指定するために使用されます。 `AsyncSelect`非ブロッキング モード ソケットが自動的に設定します。 詳細については、記事を参照してください。 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)します。  
  
##  <a name="attach"></a>CAsyncSocket::Attach  
 アタッチするには、このメンバー関数を呼び出す、`hSocket`へのハンドル、`CAsyncSocket`オブジェクトです。  
  
```  
BOOL Attach(
    SOCKET hSocket, long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `hSocket`  
 ソケットのハンドルが含まれています。  
  
 `lEvent`  
 アプリケーションが関心があるネットワーク イベントの組み合わせを指定するビットマスクです。  
  
- **FD_READ**読み取り用の準備完了の通知を受信します。  
  
- **FD_WRITE**データが読み取り可能な場合に通知を受信します。  
  
- **FD_OOB**の帯域外のデータの追加の通知を受信します。  
  
- **FD_ACCEPT**着信接続の通知を受信します。  
  
- **FD_CONNECT**接続の結果の通知を受信します。  
  
- **FD_CLOSE**ピアでソケットが閉じられると、通知を受信します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は&0; 以外を返します。  
  
### <a name="remarks"></a>コメント  
 **ソケット**ハンドルが、オブジェクトに格納されている[m_hSocket](#m_hsocket)データ メンバーです。  
  
##  <a name="bind"></a>CAsyncSocket::Bind  
 ソケットにローカル アドレスを関連付けるには、このメンバー関数を呼び出します。  
  
```  
BOOL Bind(
    UINT nSocketPort,  
    LPCTSTR lpszSocketAddress = NULL);

 
BOOL Bind (
    const SOCKADDR* lpSockAddr,  
    int nSockAddrLen);
```  
  
### <a name="parameters"></a>パラメーター  
 `nSocketPort`  
 ソケット アプリケーションを識別するポートです。  
  
 `lpszSocketAddress`  
 ネットワーク アドレスでは、「128.56.22.8」などのピリオドで区切られた数字。 渡す、 **NULL**このパラメーターを文字列、 **CAsyncSocket**インスタンスがすべてのネットワーク インターフェイス上のクライアント アクティビティを待機する必要があります。  
  
 `lpSockAddr`  
 ポインター、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)このソケットに割り当てられたアドレスを格納する構造体。  
  
 `nSockAddrLen`  
 指定されたアドレスの長さ`lpSockAddr`(バイト単位)。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**正常な[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことを検出します。  
  
- **WSAEADDRINUSE**指定したアドレスは既に使用されています。 (を参照してください、 **SO_REUSEADDR**ソケット オプションで[SetSockOpt](#setsockopt))。  
  
- **WSAEFAULT** 、`nSockAddrLen`引数が小さすぎる (のサイズよりも小さいか、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)構造) です。  
  
- **WSAEINPROGRESS** Windows ソケットのブロッキング呼び出しが進行中です。  
  
- **WSAEAFNOSUPPORT**このポートで指定したアドレス ファミリがサポートされていません。  
  
- **WSAEINVAL**ソケットは既に、アドレスにバインドします。  
  
- `WSAENOBUFS`十分なバッファーを使用可能、接続が多すぎます。  
  
- **切り離します**記述子がソケットではありません。  
  
### <a name="remarks"></a>コメント  
 このルーチンは前に接続されていないデータグラムまたはストリーム ソケットで使用後続**接続**または`Listen`呼び出しです。 接続要求を受け取る前にサーバー ソケットをリッスンしている必要がありますポート番号を選択となる Windows ソケットを呼び出すことによって**バインド**します。 **バインド**名前のないソケットにローカル名を割り当てることによって、ソケットのローカルの関連付け (ホスト アドレスとポート番号) を確立します。  
  
##  <a name="casyncsocket"></a>CAsyncSocket::CAsyncSocket  
 空のソケット オブジェクトを構築します。  
  
```  
CAsyncSocket();
```  
  
### <a name="remarks"></a>コメント  
 オブジェクトを構築後に呼び出す必要があります、**作成**を作成するメンバー関数、**ソケット**データ構造体し、そのアドレスをバインドします。 (待機中のソケットで使用するソケットを作成する場合は、Windows ソケット通信のサーバー側で、 **Accept**呼び出し、呼び出す必要はありません**作成**ソケットのです)。  
  
##  <a name="close"></a>CAsyncSocket::Close  
 ソケットを閉じます。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>コメント  
 この関数への参照がエラーで失敗するさらにするように、ソケット記述子を解放**切り離します**します。 これは、基になるソケットに対する最後の参照である場合、関連付けられている名前付け情報とキューに置かれたデータが破棄されます。 ソケット オブジェクトのデストラクターの呼び出し**閉じる**します。  
  
 `CAsyncSocket`のではなく`CSocket`、セマンティクスの**閉じる**ソケット オプションの影響を受ける**SO_LINGER**と**SO_DONTLINGER**します。 詳細については、メンバー関数を参照してください。`GetSockOpt`します。  
  
##  <a name="connect"></a>不要なため  
 接続されていないストリームまたはデータグラム ソケットへの接続を確立するためにこのメンバー関数を呼び出します。  
  
```  
BOOL Connect(
    LPCTSTR lpszHostAddress,  
    UINT nHostPort);

 
BOOL Connect(
    const SOCKADDR* lpSockAddr,  
    int nSockAddrLen);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszHostAddress`  
 このオブジェクトが接続されているソケットのネットワーク アドレス:「専用」や「128.56.22.8」などのピリオドで区切られた数字などのコンピューター名。  
  
 `nHostPort`  
 ソケット アプリケーションを識別するポートです。  
  
 `lpSockAddr`  
 ポインター、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)接続されたソケットのアドレスを格納する構造体。  
  
 `nSockAddrLen`  
 指定されたアドレスの長さ`lpSockAddr`(バイト単位)。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)します。 このエラー コードが示されている場合**とき**と、アプリケーションは、オーバーライド可能なコールバックを使用して、アプリケーションが表示されます、`OnConnect`接続操作の完了時にメッセージします。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**正常な[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことを検出します。  
  
- **WSAEADDRINUSE**指定したアドレスは既に使用されています。  
  
- **WSAEINPROGRESS** Windows ソケットのブロッキング呼び出しが進行中です。  
  
- **WSAEADDRNOTAVAIL**指定したアドレスは、ローカル コンピューターから使用できません。  
  
- **WSAEAFNOSUPPORT**このソケットで指定されているファミリ内のアドレスは使用できません。  
  
- **使います**接続の試行は拒否されました。  
  
- **WSAEDESTADDRREQ**送信先アドレスが必要です。  
  
- **WSAEFAULT** 、`nSockAddrLen`引数が正しくありません。  
  
- **WSAEINVAL**無効なホスト アドレス。  
  
- **WSAEISCONN**ソケットは既に接続されています。  
  
- **WSAEMFILE**ファイル記述子をこれ以上使用します。  
  
- **WSAENETUNREACH**ネットワークは、この時点でこのホストから到達できません。  
  
- `WSAENOBUFS`バッファー領域がありません。 ソケットを接続することはできません。  
  
- **切り離します**記述子がソケットではありません。  
  
- **WSAETIMEDOUT**がタイムアウトしました。 接続を確立せずに接続しようとしています。  
  
- **とき**ソケットがマークされている非ブロッキング接続は直ちに完了したことはできません。  
  
### <a name="remarks"></a>コメント  
 ソケットにバインドされていない場合は、一意の値が、システムでローカルの関連付けに割り当てられているソケットとしてマークされている次のようにバインドされます。 場合名前の構造体のアドレス フィールドがすべてゼロの場合は、**接続**は&0; を返します。 拡張エラー情報を取得する、`GetLastError`メンバー関数。  
  
 ストリーム ソケット (型**SOCK_STREAM**)、外部ホストへのアクティブな接続を開始します。 ソケットの呼び出しが正常に完了すると、ソケットはデータの送信/受信準備ができてです。  
  
 データグラム ソケットに関して (型**SOCK_DGRAM**)、既定の出力先を設定すると、以後のどちらを使用する**送信**と**受信**呼び出しです。  
  
##  <a name="create"></a>CAsyncSocket::Create  
 呼び出す、**作成**メンバー関数の後に、Windows ソケットを作成し、接続のソケット オブジェクトを構築します。  
  
```  
BOOL Create(
    UINT nSocketPort = 0,  
    int nSocketType = SOCK_STREAM,  
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,  
    LPCTSTR lpszSocketAddress = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `nSocketPort`  
 Windows ソケット ポートを選択する場合に、ソケットまたは 0 で使用される既知のポートです。  
  
 `nSocketType`  
 **SOCK_STREAM**または**SOCK_DGRAM**します。  
  
 `lEvent`  
 アプリケーションが関心があるネットワーク イベントの組み合わせを指定するビットマスクです。  
  
- **FD_READ**読み取り用の準備完了の通知を受信します。  
  
- **FD_WRITE**書き込みのための準備完了の通知を受信します。  
  
- **FD_OOB**の帯域外のデータの追加の通知を受信します。  
  
- **FD_ACCEPT**着信接続の通知を受信します。  
  
- **FD_CONNECT**完成した接続の通知を受信します。  
  
- **FD_CLOSE**ソケットの終了の通知を受信します。  
  
 *lpszSockAddress*  
 接続されたソケット、「128.56.22.8」などのピリオドで区切られた数のネットワーク アドレスを含む文字列へのポインター。渡す、 **NULL**このパラメーターを文字列、 **CAsyncSocket**インスタンスがすべてのネットワーク インターフェイス上のクライアント アクティビティを待機する必要があります。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**正常な[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことを検出します。  
  
- **WSAEAFNOSUPPORT**指定したアドレス ファミリがサポートされていません。  
  
- **WSAEINPROGRESS** Windows ソケットのブロック操作が進行中です。  
  
- **WSAEMFILE**ファイル記述子をこれ以上使用します。  
  
- `WSAENOBUFS`バッファー領域がありません。 ソケットを作成することはできません。  
  
- **WSAEPROTONOSUPPORT**指定したポートがサポートされていません。  
  
- **WSAEPROTOTYPE**指定されたポートは種類がソケットに対して正しくありません。  
  
- **WSAESOCKTNOSUPPORT**このアドレス ファミリでは、指定したソケットの種類はサポートされていません。  
  
### <a name="remarks"></a>コメント  
 **作成**呼び出し[ソケット](#socket)で成功した場合、それを呼び出します[バインド](#bind)指定のアドレスにソケットをバインドします。 次の種類のソケットがサポートされています。  
  
- **SOCK_STREAM**シーケンス処理、信頼性の高い、全二重モード、接続に基づくバイト ストリームを提供します。 インターネット アドレス ファミリ用には、伝送制御プロトコル (TCP) を使用します。  
  
- **SOCK_DGRAM**固定 (通常はわずか) の最大長のパケットのコネクションレスで信頼性の低いデータグラムをサポートしています。 インターネット アドレス ファミリ用には、ユーザー データグラム プロトコル (UDP) を使用します。  
  
    > [!NOTE]
    >  **Accept**メンバー関数は、新しい空への参照を受け取ります`CSocket`オブジェクトをパラメーターとして。 呼び出す前に、このオブジェクトを構築する必要があります**Accept**します。 注意このソケット オブジェクトがスコープ接続は閉じられますのなくなる場合。 呼び出す必要はありません**作成**この新しいソケット オブジェクトです。  
  
> [!IMPORTANT]
> **作成**は**いない**スレッド セーフであります。  呼び出す場合、マルチ スレッド環境でそのでしたとして起動される同時に別のスレッドで、各呼び出しでミュー テックスまたはその他の同期ロックを保護することを確認します。  
  
 ストリームとデータグラム ソケットの詳細については、記事を参照してください。 [Windows ソケット: バック グラウンド](../../mfc/windows-sockets-background.md)と[Windows ソケット: ポートとソケット アドレス](../../mfc/windows-sockets-ports-and-socket-addresses.md)と[Windows Sockets 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673)します。  
  
##  <a name="detach"></a>CAsyncSocket::Detach  
 デタッチするには、このメンバー関数を呼び出す、**ソケット**で処理、`m_hSocket`からそのデータ メンバー、`CAsyncSocket`オブジェクトし、設定`m_hSocket`に**NULL**します。  
  
```  
SOCKET Detach();
```  
  
##  <a name="fromhandle"></a>CAsyncSocket::FromHandle  
 ポインターを返す、`CAsyncSocket`オブジェクトです。  
  
```  
static CAsyncSocket* PASCAL FromHandle(SOCKET hSocket);
```  
  
### <a name="parameters"></a>パラメーター  
 `hSocket`  
 ソケットのハンドルが含まれています。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CAsyncSocket`オブジェクト、または**NULL**がある場合ない`CAsyncSocket`オブジェクトにアタッチされて`hSocket`します。  
  
### <a name="remarks"></a>コメント  
 指定されている場合、**ソケット**を処理する場合、`CAsyncSocket`ハンドルには、オブジェクトはアタッチされていない、メンバー関数を返します**NULL**します。  
  
##  <a name="getlasterror"></a>CAsyncSocket::GetLastError  
 このメンバー関数を呼び出して、最後の失敗した操作のエラー状態を取得します。  
  
```  
static int PASCAL GetLastError();
```  
  
### <a name="return-value"></a>戻り値  
 戻り値は、このスレッドによって実行される最後の Windows ソケット API ルーチンのエラー コードを示します。  
  
### <a name="remarks"></a>コメント  
 特定のメンバー関数は、エラーが発生したことを示す場合に`GetLastError`適切なエラー コードを取得する呼び出す必要があります。 該当するエラー コードの一覧については、個々 のメンバー関数の説明を参照してください。  
  
 エラー コードの詳細については、次を参照してください。 [Windows Sockets 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673)します。  
  
##  <a name="getpeername"></a>で  
 このソケットが接続されているピア ソケットのアドレスを取得するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetPeerName(
    CString& rPeerAddress,  
    UINT& rPeerPort);

 
BOOL GetPeerName(
    SOCKADDR* lpSockAddr,  
    int* lpSockAddrLen);
```  
  
### <a name="parameters"></a>パラメーター  
 `rPeerAddress`  
 参照、`CString`をピリオドで区切られた数値 IP アドレスを受け取るオブジェクト。  
  
 `rPeerPort`  
 参照、 **UINT**ポートを格納します。  
  
 `lpSockAddr`  
 ポインター、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)ピア ソケットの名を受け取る構造体。  
  
 `lpSockAddrLen`  
 指定されたアドレスの長さへのポインター `lpSockAddr` (バイト単位)。 戻り時に、`lpSockAddrLen`引数の実際のサイズに含まれる`lpSockAddr`(バイト単位) が返されます。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**正常な[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことを検出します。  
  
- **WSAEFAULT** 、`lpSockAddrLen`引数のサイズが不十分です。  
  
- **WSAEINPROGRESS** Windows ソケットのブロッキング呼び出しが進行中です。  
  
- **接続保持**ソケットが接続されていません。  
  
- **切り離します**記述子がソケットではありません。  
  
### <a name="remarks"></a>コメント  
 IPv6 アドレスを処理する[CAsyncSocket::GetPeerNameEx](#getpeernameex)します。  
  
##  <a name="getpeernameex"></a>CAsyncSocket::GetPeerNameEx  
 このソケットが接続されている (ハンドルの IPv6 アドレス) をピア ソケットのアドレスを取得するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetPeerNameEx(
    CString& rPeerAddress,  
    UINT& rPeerPort);
```  
  
### <a name="parameters"></a>パラメーター  
 `rPeerAddress`  
 参照、`CString`をピリオドで区切られた数値 IP アドレスを受け取るオブジェクト。  
  
 `rPeerPort`  
 参照、 **UINT**ポートを格納します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**正常な[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことを検出します。  
  
- **WSAEFAULT** 、`lpSockAddrLen`引数のサイズが不十分です。  
  
- **WSAEINPROGRESS** Windows ソケットのブロッキング呼び出しが進行中です。  
  
- **接続保持**ソケットが接続されていません。  
  
- **切り離します**記述子がソケットではありません。  
  
### <a name="remarks"></a>コメント  
 この関数は、同じ[で](#getpeername)IPv6 を処理する点を除いて、従来のプロトコルに対応します。  
  
##  <a name="getsockname"></a>で  
 このメンバー関数を呼び出して、ソケットのローカル名を取得します。  
  
```  
BOOL GetSockName(
    CString& rSocketAddress,  
    UINT& rSocketPort);

 
BOOL GetSockName(
    SOCKADDR* lpSockAddr,  
    int* lpSockAddrLen);
```  
  
### <a name="parameters"></a>パラメーター  
 `rSocketAddress`  
 参照、`CString`をピリオドで区切られた数値 IP アドレスを受け取るオブジェクト。  
  
 `rSocketPort`  
 参照、 **UINT**ポートを格納します。  
  
 `lpSockAddr`  
 ポインター、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)ソケットのアドレスを受け取る。  
  
 `lpSockAddrLen`  
 指定されたアドレスの長さへのポインター `lpSockAddr` (バイト単位)。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**正常な[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことを検出します。  
  
- **WSAEFAULT** 、`lpSockAddrLen`引数のサイズが不十分です。  
  
- **WSAEINPROGRESS** Windows ソケットのブロック操作が進行中です。  
  
- **切り離します**記述子がソケットではありません。  
  
- **WSAEINVAL**ソケットが使用するアドレスにバインドされていない**バインド**します。  
  
### <a name="remarks"></a>コメント  
 この呼び出しは特に便利な場合に、**接続**コマンドを実行せずに呼び出しが行われた、**バインド**先にこの呼び出しのシステムで設定されているローカルの関連付けを判断できますのみ手段を提供します。  
  
 IPv6 アドレスを処理する[CAsyncSocket::GetSockNameEx](#getsocknameex)  
  
##  <a name="getsocknameex"></a>CAsyncSocket::GetSockNameEx  
 ソケット (ハンドルの IPv6 アドレス) のローカル名を取得するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetSockNameEx(
    CString& rSocketAddress,  
    UINT& rSocketPort);
```  
  
### <a name="parameters"></a>パラメーター  
 `rSocketAddress`  
 参照、`CString`をピリオドで区切られた数値 IP アドレスを受け取るオブジェクト。  
  
 `rSocketPort`  
 参照、 **UINT**ポートを格納します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**正常な[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことを検出します。  
  
- **WSAEFAULT** 、`lpSockAddrLen`引数のサイズが不十分です。  
  
- **WSAEINPROGRESS** Windows ソケットのブロック操作が進行中です。  
  
- **切り離します**記述子がソケットではありません。  
  
- **WSAEINVAL**ソケットが使用するアドレスにバインドされていない**バインド**します。  
  
### <a name="remarks"></a>コメント  
 この呼び出しは同じ[で](#getsockname)IPv6 を処理する点を除いて、従来のプロトコルに対応します。  
  
 この呼び出しは特に便利な場合に、**接続**コマンドを実行せずに呼び出しが行われた、**バインド**先にこの呼び出しのシステムで設定されているローカルの関連付けを判断できますのみ手段を提供します。  
  
##  <a name="getsockopt"></a>CAsyncSocket::GetSockOpt  
 ソケット オプションを取得するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetSockOpt(
    int nOptionName,  
    void* lpOptionValue,  
    int* lpOptionLen,  
    int nLevel = SOL_SOCKET);
```  
  
### <a name="parameters"></a>パラメーター  
 `nOptionName`  
 値を取得するソケット オプション。  
  
 `lpOptionValue`  
 要求されたオプションの値が返されるバッファーへのポインター。 バッファーに、選択したオプションに関連付けられている値が返される`lpOptionValue`です。 整数を指す`lpOptionLen`必要があります (バイト単位) には、このバッファーのサイズが含まれていたとして、返された場合は、返される値のサイズに設定されます。 **SO_LINGER**のサイズになるこれ、`LINGER`構造体は他のすべてのオプションについてのサイズであることが、 **BOOL**または`int`オプションによって異なります。 オプションと、「解説」セクションでは、そのサイズ一覧を参照してください。  
  
 `lpOptionLen`  
 サイズへのポインター、`lpOptionValue`バッファーのバイト単位です。  
  
 `nLevel`  
 オプションを定義するレベルサポートされているレベルだけが**取得**と**取得できる**です。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)します。 オプションが設定されていない場合`SetSockOpt`、し`GetSockOpt`オプションの既定値を返します。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**正常な[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことを検出します。  
  
- **WSAEFAULT** 、`lpOptionLen`引数が無効です。  
  
- **WSAEINPROGRESS** Windows ソケットのブロック操作が進行中です。  
  
- **WSAENOPROTOOPT**オプションは、不明なまたはサポートされていません。 具体的には、 **:so_broadcast**型のソケットでサポートされていない**SOCK_STREAM**、中に**SO_ACCEPTCONN**、 **SO_DONTLINGER**、**接続**、 **SO_LINGER**、および**SO_OOBINLINE**型のソケットではサポートされません**SOCK_DGRAM**します。  
  
- **切り離します**記述子がソケットではありません。  
  
### <a name="remarks"></a>コメント  
 `GetSockOpt`任意の状態で、任意のソケットに関連付けられているソケット オプションの現在の値を取得し、その結果を`lpOptionValue`します。 オプションでは、パケットや帯域外のデータ転送のルーティングなどのソケット操作に影響します。  
  
 次のオプションはサポートされて`GetSockOpt`します。 型によってアドレス指定されたデータの種類を識別する`lpOptionValue`です。 **低下**オプションは、レベルを使用して**取得できる**; レベルを使用するその他のすべてのオプション**取得**します。  
  
|値|型|説明|  
|-----------|----------|-------------|  
|**SO_ACCEPTCONN**|**BOOL**|ソケットはリッスンしています。|  
|**:SO_BROADCAST**|**BOOL**|ソケットは、ブロードキャスト メッセージの送信で構成されています。|  
|**SO_DEBUG**|**BOOL**|デバッグが有効になっているとします。|  
|**SO_DONTLINGER**|**BOOL**|True の場合、 **SO_LINGER**オプションが無効になります。|  
|**SO_DONTROUTE**|**BOOL**|ルーティングが無効になります。|  
|**SO_ERROR**|`int`|エラー状態を取得し、クリアします。|  
|**接続**|**BOOL**|Keep alive が送信されます。|  
|**SO_LINGER**|**LINGER 構造体**|現在の待機オプションを返します。|  
|**SO_OOBINLINE**|**BOOL**|帯域外のデータは、通常のデータ ストリームの受信中です。|  
|**SO_RCVBUF**|`int`|バッファー サイズを受け取ります。|  
|**SO_REUSEADDR**|**BOOL**|ソケットは、既に使用されているアドレスにバインドすることができます。|  
|**SO_SNDBUF**|`int`|バッファー サイズを送信します。|  
|**SO_TYPE**|`int`|ソケットの種類 (たとえば、 **SOCK_STREAM**)。|  
|**低下**|**BOOL**|送信結合用の Nagle アルゴリズムを無効にします。|  
  
 Berkeley Software Distribution (BSD) オプションはサポートされていません`GetSockOpt`は。  
  
|値|型|説明|  
|-----------|----------|-------------|  
|**SO_RCVLOWAT**|`int`|低水位マークが表示されます。|  
|**SO_RCVTIMEO**|`int`|タイムアウトを受信します。|  
|**SO_SNDLOWAT**|`int`|下限値を送信します。|  
|**SO_SNDTIMEO**|`int`|タイムアウトを送信します。|  
|**なる**||IP ヘッダーにオプションを取得します。|  
|**TCP_MAXSEG**|`int`|TCP セグメントの最大サイズを取得します。|  
  
 呼び出す`GetSockOpt`サポートされていないオプションを使用してがのエラー コード**WSAENOPROTOOPT**から返される`GetLastError`です。  
  
##  <a name="ioctl"></a>CAsyncSocket::IOCtl  
 このメンバー関数を呼び出して、ソケットのモードを制御します。  
  
```  
BOOL IOCtl(
    long lCommand,  
    DWORD* lpArgument);
```  
  
### <a name="parameters"></a>パラメーター  
 `lCommand`  
 ソケットで実行するコマンドです。  
  
 `lpArgument`  
 パラメーターへのポインター`lCommand`します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**正常な[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことを検出します。  
  
- **WSAEINVAL** `lCommand`有効なコマンドではありませんまたは`lpArgument`用の許容可能なパラメーターではありません`lCommand`、または、コマンドは指定したソケットの種類には適用できません。  
  
- **WSAEINPROGRESS** Windows ソケットのブロック操作が進行中です。  
  
- **切り離します**記述子がソケットではありません。  
  
### <a name="remarks"></a>コメント  
 このルーチンは、いずれかの状態のすべてのソケットに使用できます。 取得またはプロトコルや通信サブシステムの独立した、ソケットに関連付けられている操作のパラメーターを取得するために使用します。 次のコマンドがサポートされています。  
  
- **FIONBIO**を有効にするまたは非ブロッキング モード ソケットを無効にします。 `lpArgument`パラメーターが指す、`DWORD`は非ブロッキング モードが有効にする場合、0 以外の値、および場合は&0; を無効にすることができます。 場合`AsyncSelect`使用しようとすると、ソケットで発行された**IOCtl** 、ソケットをブロッキング モードに設定するには失敗**WSAEINVAL**します。 ソケットをブロックしているモードに設定し、回避する、 **WSAEINVAL**エラー、アプリケーションまず無効にして`AsyncSelect`を呼び出して`AsyncSelect`で、`lEvent`し、パラメーターを 0 を呼び出す**IOCtl**します。  
  
- **FIONREAD**最大で&1; つの読み取り可能バイト数を決定**受信**このソケットからの呼び出しです。 `lpArgument`パラメーターが指す、`DWORD`を**IOCtl**結果を格納します。 このソケットが型の場合**SOCK_STREAM**、 **FIONREAD** 、1 つで読み取ることができるデータの総量を返す**受信**; これは、通常と同じソケットでのキューに置かれたデータの総量。 このソケットが型の場合**SOCK_DGRAM**、 **FIONREAD**ソケットでのキューに置かれた最初のデータグラムのサイズを返します。  
  
- **SIOCATMARK**すべての帯域外のデータが読み取られたかどうかを決定します。 これは、種類のソケットにのみ適用されます**SOCK_STREAM** 、帯域外のデータの行で受信用に構成する ( **SO_OOBINLINE**)。 読み取られる帯域外のデータが待機していない場合、操作は&0; 以外を返します。 それ以外の場合は 0 を返します、次回**受信**または`ReceiveFrom`上で実行「マーク」の前に、データの一部またはすべてのソケットが取得されます。 アプリケーションを使用する必要があります、 **SIOCATMARK**データが残っているかどうかを判断する操作。 (帯域外) の「緊急」のデータの前に通常のデータがある場合は、順序で受信されます。 (ことに注意してください、**受信**または`ReceiveFrom`帯域外の通常のデータを同じ呼び出しを混在させないでされます)。`lpArgument`パラメーターが指す、`DWORD`を**IOCtl**結果を格納します。  
  
 この関数のサブセットである**レジスタ**Berkeley ソケットで使用されるためです。 具体的には、コマンドと同じですがない**FIOASYNC**、中に**SIOCATMARK**はサポートされているソケット レベルだけコマンドです。  
  
##  <a name="listen"></a>CAsyncSocket::Listen  
 接続要求をリッスンするには、このメンバー関数を呼び出します。  
  
```  
BOOL Listen(int nConnectionBacklog = 5);
```  
  
### <a name="parameters"></a>パラメーター  
 *nConnectionBacklog*  
 接続待ちのキューが拡張可能最大長。 有効な範囲は 1 ~ 5 です。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**正常な[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことを検出します。  
  
- **WSAEADDRINUSE**アドレスは、使用中でリッスンが行われました。  
  
- **WSAEINPROGRESS** Windows ソケットのブロック操作が進行中です。  
  
- **WSAEINVAL**にソケットがバインドされていない**バインド**か、既に接続されています。  
  
- **WSAEISCONN**ソケットは既に接続されています。  
  
- **WSAEMFILE**ファイル記述子をこれ以上使用します。  
  
- `WSAENOBUFS`バッファー領域がありません。  
  
- **切り離します**記述子がソケットではありません。  
  
- **WSAEOPNOTSUPP**参照先のソケットをサポートする型のではありません、`Listen`操作します。  
  
### <a name="remarks"></a>コメント  
 接続を受け入れるように、ソケットを最初に作成**作成**、着信接続用のバックログがで指定された`Listen`とに、接続が受け入れられます**Accept**します。 `Listen`型は、接続をサポートするソケットにのみ適用されます**SOCK_STREAM**します。 このソケットは、「パッシブ」モードの受信接続が確認され、プロセスが承認待ちキューに置かれた場所に配置されます。  
  
 この関数は、通常のサーバー (または接続を許可する必要のある任意のアプリケーション) によって使用、一度に&1; つ以上の接続要求がある可能性があります。 クライアントは、エラーを示す値が、キューがいっぱいで、接続要求が到着すると、場合**使います**します。  
  
 `Listen`使用可能なポート (記述子) がない場合に、合理的に続行を試行します。 キューが空にするまでは接続を受け入れます。 ポートが利用可能になった場合に、後で呼び出さ`Listen`または**Accept**はキューを現在または最新の「バックログ」補充 (リフィル) 可能であれば、および着信接続のリッスンを再開します。  
  
##  <a name="m_hsocket"></a>CAsyncSocket::m_hSocket  
 含む、**ソケット**これによってカプセル化されたソケットのハンドル`CAsyncSocket`オブジェクトです。  
  
```  
SOCKET m_hSocket;  
```  
  
##  <a name="onaccept"></a>CAsyncSocket::OnAccept  
 呼び出すことによって保留中の接続要求を受け付けられる待機中のソケットに通知するフレームワークによって呼び出され、 [Accept](#accept)メンバー関数。  
  
```  
virtual void OnAccept(int nErrorCode);
```  
  
### <a name="parameters"></a>パラメーター  
 `nErrorCode`  
 ソケットで最新のエラーです。 次のエラー コードの対象、`OnAccept`メンバー関数。  
  
- **0**関数が正常に実行されました。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことを検出します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)します。  
  
##  <a name="onclose"></a>CAsyncSocket::OnClose  
 そのプロセスによって接続されたソケットが閉じているソケットに通知するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnClose(int nErrorCode);
```  
  
### <a name="parameters"></a>パラメーター  
 `nErrorCode`  
 ソケットで最新のエラーです。 次のエラー コードに適用、`OnClose`メンバー関数。  
  
- **0**関数が正常に実行されました。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことを検出します。  
  
- **WSAECONNRESET**リモート側によって接続がリセットされました。  
  
- **WSAECONNABORTED**タイムアウトまたはその他の障害によって接続が中止されました。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)します。  
  
##  <a name="onconnect"></a>CAsyncSocket::OnConnect  
 その接続の試行が完了したこと、正常にまたはエラーが発生するかどうかを接続しているソケットに通知するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnConnect(int nErrorCode);
```  
  
### <a name="parameters"></a>パラメーター  
 `nErrorCode`  
 ソケットで最新のエラーです。 次のエラー コードに適用、`OnConnect`メンバー関数。  
  
- **0**関数が正常に実行されました。  
  
- **WSAEADDRINUSE**指定したアドレスは既に使用されています。  
  
- **WSAEADDRNOTAVAIL**指定したアドレスは、ローカル コンピューターから使用できません。  
  
- **WSAEAFNOSUPPORT**このソケットで指定されているファミリ内のアドレスは使用できません。  
  
- **使います**接続の試行が強制的に拒否されます。  
  
- **WSAEDESTADDRREQ**送信先アドレスが必要です。  
  
- **WSAEFAULT** 、`lpSockAddrLen`引数が正しくありません。  
  
- **WSAEINVAL**ソケットは既に、アドレスにバインドします。  
  
- **WSAEISCONN**ソケットは既に接続されています。  
  
- **WSAEMFILE**ファイル記述子をこれ以上使用します。  
  
- **WSAENETUNREACH**ネットワークは、この時点でこのホストから到達できません。  
  
- `WSAENOBUFS`バッファー領域がありません。 ソケットを接続することはできません。  
  
- **接続保持**ソケットが接続されていません。  
  
- **切り離します**記述子がファイル、ソケットではありません。  
  
- **WSAETIMEDOUT**接続を確立することがなく、接続の試行がタイムアウトします。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  [CSocket](../../mfc/reference/csocket-class.md)、`OnConnect`通知関数を呼び出すことはありません。 接続は、単に呼び出す**接続**、(正常にまたはエラー)、接続が完了したときに返します。 MFC 実装の詳細は、接続の通知を処理する方法。  
  
 詳細については、次を参照してください。 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAsyncSocket&#1;](../../mfc/reference/codesnippet/cpp/casyncsocket-class_1.cpp)]  
  
##  <a name="onoutofbanddata"></a>CAsyncSocket::OnOutOfBandData  
 送信側のソケットが帯域外のデータを送信する受信側のソケットに通知するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnOutOfBandData(int nErrorCode);
```  
  
### <a name="parameters"></a>パラメーター  
 `nErrorCode`  
 ソケットで最新のエラーです。 次のエラー コードに適用、`OnOutOfBandData`メンバー関数。  
  
- **0**関数が正常に実行されました。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことを検出します。  
  
### <a name="remarks"></a>コメント  
 帯域外のデータが論理的に独立したチャネルの種類の接続されたソケットの各ペアに関連付けられている**SOCK_STREAM**します。 チャネルは通常、緊急データを送信する使用します。  
  
 MFC クラスのユーザーが、帯域外のデータをサポートしています`CAsyncSocket`を使用する推奨されていません。 簡単な方法では、このようなデータを渡すための&2; つ目のソケットを作成します。 帯域外のデータの詳細については、次を参照してください。 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)します。  
  
##  <a name="onreceive"></a>CAsyncSocket::OnReceive  
 ソケットに呼び出すことによって取得できる、バッファーにデータがあることを通知するためにフレームワークによって呼び出される、**受信**メンバー関数。  
  
```  
virtual void OnReceive(int nErrorCode);
```  
  
### <a name="parameters"></a>パラメーター  
 `nErrorCode`  
 ソケットで最新のエラーです。 次のエラー コードに適用、`OnReceive`メンバー関数。  
  
- **0**関数が正常に実行されました。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことを検出します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAsyncSocket&#2;](../../mfc/reference/codesnippet/cpp/casyncsocket-class_2.cpp)]  
  
##  <a name="onsend"></a>CAsyncSocket::OnSend  
 ソケットに呼び出すことによってデータを送信できるようになりましたことを通知するためにフレームワークによって呼び出される、**送信**メンバー関数。  
  
```  
virtual void OnSend(int nErrorCode);
```  
  
### <a name="parameters"></a>パラメーター  
 `nErrorCode`  
 ソケットで最新のエラーです。 次のエラー コードに適用、`OnSend`メンバー関数。  
  
- **0**関数が正常に実行されました。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことを検出します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAsyncSocket&#3;](../../mfc/reference/codesnippet/cpp/casyncsocket-class_3.cpp)]  
  
##  <a name="operator_eq"></a>CAsyncSocket::operator =  
 新しい値を代入する`CAsyncSocket`オブジェクトです。  
  
```  
void operator=(const CAsyncSocket& rSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 `rSrc`  
 既存への参照を`CAsyncSocket`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出して、既存のコピー`CAsyncSocket`オブジェクト間`CAsyncSocket`オブジェクトです。  
  
##  <a name="operator_socket"></a>CAsyncSocket::operator ソケット  
 この演算子を使用して取得する、**ソケット**の処理、`CAsyncSocket`オブジェクトです。  
  
```  
operator SOCKET() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合のハンドル、**ソケット**はそれ以外の場合、 **NULL**します。  
  
### <a name="remarks"></a>コメント  
 ハンドルを使用して、Windows Api を直接呼び出すことができます。  
  
##  <a name="receive"></a>CAsyncSocket::Receive  
 このメンバー関数を呼び出して、ソケットからデータを受信します。  
  
```  
virtual int Receive(
    void* lpBuf,  
    int nBufLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpBuf`  
 受信データのバッファー。  
  
 `nBufLen`  
 長さ`lpBuf`(バイト単位)。  
  
 `nFlags`  
 呼び出しが行われた場所の方法を指定します。 この関数のセマンティクスは、ソケット オプションによって決まりますと`nFlags`パラメーター。 後者は、次の値のいずれかの C++ と組み合わせることによって構築`OR`演算子。  
  
- **MSG_PEEK**受信データをピークします。 データは、バッファーにコピーされますが、入力キューからは削除されません。  
  
- **MSG_OOB**帯域外のデータを処理します。  
  
### <a name="return-value"></a>戻り値  
 エラーが発生しなかった場合**受信**受信したバイト数を返します。 接続が閉じられた場合は、0 を返します。 それ以外の場合、値の**あふれた**返されると特定のエラー コードを呼び出すことによって取得できる[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**正常な[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことを検出します。  
  
- **接続保持**ソケットが接続されていません。  
  
- **WSAEINPROGRESS** Windows ソケットのブロック操作が進行中です。  
  
- **切り離します**記述子がソケットではありません。  
  
- **WSAEOPNOTSUPP MSG_OOB**が指定されている、ソケットの種類ではありませんが、 **SOCK_STREAM**します。  
  
- **WSAESHUTDOWN**ソケットがシャット ダウンされたを呼び出すことはなく**受信**後ソケットで`ShutDown`で呼び出された`nHow`0 または 2 に設定します。  
  
- **とき**ソケットがマークされている非ブロッキングと**受信**操作はブロックされます。  
  
- **WSAEMSGSIZE**データグラムが、指定されたバッファーに収まるように大きすぎて、切り捨てられました。  
  
- **WSAEINVAL**にソケットがバインドされていない**バインド**します。  
  
- **WSAECONNABORTED**タイムアウトまたはその他の障害によって仮想回線が中止されました。  
  
- **WSAECONNRESET**リモート側によって仮想回線がリセットされました。  
  
### <a name="remarks"></a>コメント  
 この関数は、接続されているストリームまたはデータグラム ソケットの使用し、着信データを読み取るために使用します。  
  
 型のソケット**SOCK_STREAM**では、指定されたバッファーのサイズに達するまで、現在利用可能な限り多くの情報が返されます。 帯域外のデータの行で受信ソケットが構成されている場合 (ソケット オプション**SO_OOBINLINE**)、帯域外のデータが未読の帯域外ののみデータが返されます。 アプリケーションを使用できます、 **IOCtlSIOCATMARK**オプションまたは[OnOutOfBandData](#onoutofbanddata)をすべての帯域外の複数のデータが読み取られるままかどうかを判断します。  
  
 データグラム ソケットの場合は、指定されたバッファーのサイズに達するまで、最初のキューに登録されるデータグラムからデータを抽出します。 データグラムが、指定されたバッファーより大きい場合は、バッファーは、データグラムの最初の部分で塗りつぶさ、余分なデータが失われたと**受信**の値を返します**あふれた**に設定すると、エラー コード**WSAEMSGSIZE**します。 受信データがないかどうか、値は、ソケットに**あふれた**設定されたエラー コードと共に返される**とき**します。 [OnReceive](#onreceive)コールバック関数を使用してより多くのデータが到着したときを決定します。  
  
 型の場合は、ソケット**SOCK_STREAM**リモート側が、接続を正常にシャット ダウンし、**受信**は 0 バイトを受信して直ちに完了します。 接続がリセットされた場合、**受信**は失敗し、エラー **WSAECONNRESET**します。  
  
 **受信**時間ごとに&1; 回だけ呼び出す必要があります[CAsyncSocket::OnReceive](#onreceive)が呼び出されます。  
  
### <a name="example"></a>例  
  例を参照してください[CAsyncSocket::OnReceive](#onreceive)します。  
  
##  <a name="receivefrom"></a>で  
 データグラムを受信およびの送信元アドレスを格納するには、このメンバー関数を呼び出して、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)構造または`rSocketAddress`です。  
  
```  
int ReceiveFrom(
    void* lpBuf,  
    int nBufLen,  
    CString& rSocketAddress,  
    UINT& rSocketPort,  
    int nFlags = 0);

 
int ReceiveFrom(
    void* lpBuf,  
    int nBufLen,  
    SOCKADDR* lpSockAddr,  
    int* lpSockAddrLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpBuf`  
 受信データのバッファー。  
  
 `nBufLen`  
 長さ`lpBuf`(バイト単位)。  
  
 `rSocketAddress`  
 参照、`CString`をピリオドで区切られた数値 IP アドレスを受け取るオブジェクト。  
  
 `rSocketPort`  
 参照、 **UINT**ポートを格納します。  
  
 `lpSockAddr`  
 ポインター、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)関数が戻るとき、送信元アドレスを保持する構造体。  
  
 `lpSockAddrLen`  
 送信元アドレスの長さへのポインター `lpSockAddr` (バイト単位)。  
  
 `nFlags`  
 呼び出しが行われた場所の方法を指定します。 この関数のセマンティクスは、ソケット オプションによって決まりますと`nFlags`パラメーター。 後者は、次の値のいずれかの C++ と組み合わせることによって構築`OR`演算子。  
  
- **MSG_PEEK**受信データをピークします。 データは、バッファーにコピーされますが、入力キューからは削除されません。  
  
- **MSG_OOB**帯域外のデータを処理します。  
  
### <a name="return-value"></a>戻り値  
 エラーが発生しなかった場合`ReceiveFrom`受信したバイト数を返します。 接続が閉じられた場合は、0 を返します。 それ以外の場合、値の**あふれた**返されると特定のエラー コードを呼び出すことによって取得できる`GetLastError`です。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**正常な[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことを検出します。  
  
- **WSAEFAULT** 、`lpSockAddrLen`引数が無効:`lpSockAddr`バッファーが小さすぎるため、ピア アドレスに対応します。  
  
- **WSAEINPROGRESS** Windows ソケットのブロック操作が進行中です。  
  
- **WSAEINVAL**にソケットがバインドされていない**バインド**します。  
  
- **接続保持**、ソケットが接続されていません ( **SOCK_STREAM**のみ)。  
  
- **切り離します**記述子がソケットではありません。  
  
- **WSAEOPNOTSUPP MSG_OOB**が指定されている、ソケットの種類ではありませんが、 **SOCK_STREAM**します。  
  
- **WSAESHUTDOWN**ソケットがシャット ダウンされたを呼び出すことはなく`ReceiveFrom`後ソケットで`ShutDown`で呼び出された`nHow`0 または 2 に設定します。  
  
- **とき**ソケットがマークされている非ブロッキングと`ReceiveFrom`操作はブロックされます。  
  
- **WSAEMSGSIZE**データグラムが、指定されたバッファーに収まるように大きすぎて、切り捨てられました。  
  
- **WSAECONNABORTED**タイムアウトまたはその他の障害によって仮想回線が中止されました。  
  
- **WSAECONNRESET**リモート側によって仮想回線がリセットされました。  
  
### <a name="remarks"></a>コメント  
 この関数は、(場合によっては接続されている) ソケットの受信データの読み取りし、データの送信元アドレスのキャプチャに使用されます。  
  
 IPv6 アドレスを処理する[CAsyncSocket::ReceiveFromEx](#receivefromex)します。  
  
 型のソケット**SOCK_STREAM**では、指定されたバッファーのサイズに達するまで、現在利用可能な限り多くの情報が返されます。 帯域外のデータの行で受信ソケットが構成されている場合 (ソケット オプション**SO_OOBINLINE**)、帯域外のデータが未読の帯域外ののみデータが返されます。 アプリケーションを使用できます、 **IOCtlSIOCATMARK**オプションまたは`OnOutOfBandData`をすべての帯域外の複数のデータが読み取られるままかどうかを判断します。 `lpSockAddr`と`lpSockAddrLen`のパラメーターが無視される**SOCK_STREAM**ソケットです。  
  
 データグラム ソケットの場合は、指定されたバッファーのサイズに達するまで、最初のキューに登録されるデータグラムからデータを抽出します。 データグラムが、指定されたバッファーより大きい場合は、バッファーは、メッセージの最初の部分で塗りつぶさ、余分なデータが失われたと`ReceiveFrom`の値を返します**あふれた**に設定すると、エラー コード**WSAEMSGSIZE**します。  
  
 場合`lpSockAddr`0 以外の場合、種類がソケット**SOCK_DGRAM**、対応する、データを送信したソケットのネットワーク アドレスをコピー [SOCKADDR](../../mfc/reference/sockaddr-structure.md)構造体。 値が指す`lpSockAddrLen`はこの構造体のサイズに初期化され、格納されたアドレスの実際のサイズを示すために戻るときに変更します。 ソケットに利用可能な受信データがない場合、`ReceiveFrom`データの到着、ソケットでない限りを呼び出しが待機する非ブロッキングします。 この場合、値は**あふれた**設定されたエラー コードと共に返される**とき**します。 `OnReceive`コールバックより多くのデータが到着した場合を判断するために使用できます。  
  
 型の場合は、ソケット**SOCK_STREAM**リモート側が、接続を正常にシャット ダウンし、`ReceiveFrom`は 0 バイトを受信して直ちに完了します。  
  
##  <a name="receivefromex"></a>CAsyncSocket::ReceiveFromEx  
 データグラムを受信およびの送信元アドレスを格納するには、このメンバー関数を呼び出して、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)構造または`rSocketAddress`(IPv6 アドレスのハンドル)。  
  
```  
int ReceiveFromEx(
    void* lpBuf,  
    int nBufLen,  
    CString& rSocketAddress,  
    UINT& rSocketPort,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpBuf`  
 受信データのバッファー。  
  
 `nBufLen`  
 長さ`lpBuf`(バイト単位)。  
  
 `rSocketAddress`  
 参照、`CString`をピリオドで区切られた数値 IP アドレスを受け取るオブジェクト。  
  
 `rSocketPort`  
 参照、 **UINT**ポートを格納します。  
  
 `nFlags`  
 呼び出しが行われた場所の方法を指定します。 この関数のセマンティクスは、ソケット オプションによって決まりますと`nFlags`パラメーター。 後者は、次の値のいずれかの C++ と組み合わせることによって構築`OR`演算子。  
  
- **MSG_PEEK**受信データをピークします。 データは、バッファーにコピーされますが、入力キューからは削除されません。  
  
- **MSG_OOB**帯域外のデータを処理します。  
  
### <a name="return-value"></a>戻り値  
 エラーが発生しなかった場合`ReceiveFromEx`受信したバイト数を返します。 接続が閉じられた場合は、0 を返します。 それ以外の場合、値の**あふれた**返されると特定のエラー コードを呼び出すことによって取得できる`GetLastError`です。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**正常な[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことを検出します。  
  
- **WSAEFAULT** 、`lpSockAddrLen`引数が無効:`lpSockAddr`バッファーが小さすぎるため、ピア アドレスに対応します。  
  
- **WSAEINPROGRESS** Windows ソケットのブロック操作が進行中です。  
  
- **WSAEINVAL**にソケットがバインドされていない**バインド**します。  
  
- **接続保持**、ソケットが接続されていません ( **SOCK_STREAM**のみ)。  
  
- **切り離します**記述子がソケットではありません。  
  
- **WSAEOPNOTSUPP MSG_OOB**が指定されている、ソケットの種類ではありませんが、 **SOCK_STREAM**します。  
  
- **WSAESHUTDOWN**ソケットがシャット ダウンされたを呼び出すことはなく`ReceiveFromEx`後ソケットで`ShutDown`で呼び出された`nHow`0 または 2 に設定します。  
  
- **とき**ソケットがマークされている非ブロッキングと`ReceiveFromEx`操作はブロックされます。  
  
- **WSAEMSGSIZE**データグラムが、指定されたバッファーに収まるように大きすぎて、切り捨てられました。  
  
- **WSAECONNABORTED**タイムアウトまたはその他の障害によって仮想回線が中止されました。  
  
- **WSAECONNRESET**リモート側によって仮想回線がリセットされました。  
  
### <a name="remarks"></a>コメント  
 この関数は、(場合によっては接続されている) ソケットの受信データの読み取りし、データの送信元アドレスのキャプチャに使用されます。  
  
 この関数は、同じ[で](#receivefrom)IPv6 を処理する点を除いて、従来のプロトコルに対応します。  
  
 型のソケット**SOCK_STREAM**では、指定されたバッファーのサイズに達するまで、現在利用可能な限り多くの情報が返されます。 帯域外のデータの行で受信ソケットが構成されている場合 (ソケット オプション**SO_OOBINLINE**)、帯域外のデータが未読の帯域外ののみデータが返されます。 アプリケーションを使用できます、 **IOCtlSIOCATMARK**オプションまたは`OnOutOfBandData`をすべての帯域外の複数のデータが読み取られるままかどうかを判断します。 `lpSockAddr`と`lpSockAddrLen`のパラメーターが無視される**SOCK_STREAM**ソケットです。  
  
 データグラム ソケットの場合は、指定されたバッファーのサイズに達するまで、最初のキューに登録されるデータグラムからデータを抽出します。 データグラムが、指定されたバッファーより大きい場合は、バッファーは、メッセージの最初の部分で塗りつぶさ、余分なデータが失われたと`ReceiveFromEx`の値を返します**あふれた**に設定すると、エラー コード**WSAEMSGSIZE**します。  
  
 場合`lpSockAddr`0 以外の場合、種類がソケット**SOCK_DGRAM**、対応する、データを送信したソケットのネットワーク アドレスをコピー [SOCKADDR](../../mfc/reference/sockaddr-structure.md)構造体。 値が指す`lpSockAddrLen`はこの構造体のサイズに初期化され、格納されたアドレスの実際のサイズを示すために戻るときに変更します。 ソケットに利用可能な受信データがない場合、`ReceiveFromEx`データの到着、ソケットでない限りを呼び出しが待機する非ブロッキングします。 この場合、値は**あふれた**設定されたエラー コードと共に返される**とき**します。 `OnReceive`コールバックより多くのデータが到着した場合を判断するために使用できます。  
  
 型の場合は、ソケット**SOCK_STREAM**リモート側が、接続を正常にシャット ダウンし、`ReceiveFromEx`は 0 バイトを受信して直ちに完了します。  
  
##  <a name="send"></a>CAsyncSocket::Send  
 このメンバー関数を呼び出して、接続されたソケットにデータを送信します。  
  
```  
virtual int Send(
    const void* lpBuf,  
    int nBufLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpBuf`  
 転送するデータを保持するバッファー。  
  
 `nBufLen`  
 内のデータの長さ`lpBuf`(バイト単位)。  
  
 `nFlags`  
 呼び出しが行われた場所の方法を指定します。 この関数のセマンティクスは、ソケット オプションによって決まりますと`nFlags`パラメーター。 後者は、次の値のいずれかの C++ と組み合わせることによって構築`OR`演算子。  
  
- **MSG_DONTROUTE**データは、ルーティングされる可能性がありますすべきを指定します。 Windows ソケット サプライヤーは、このフラグを無視を選択できます。  
  
- **MSG_OOB**帯域外のデータを送信 ( **SOCK_STREAM**のみ)。  
  
### <a name="return-value"></a>戻り値  
 エラーが発生しなかった場合**送信**送信されたバイト数の合計を返します。 (これはいるによって示される数よりも少ない`nBufLen`)。それ以外の場合、値の**あふれた**返されると特定のエラー コードを呼び出すことによって取得できる[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**正常な[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことを検出します。  
  
- **WSAEACCES**要求されたアドレスは、ブロードキャスト アドレスですが、適切なフラグが設定されませんでした。  
  
- **WSAEINPROGRESS** Windows ソケットのブロック操作が進行中です。  
  
- **WSAEFAULT** 、`lpBuf`引数で、ユーザー アドレス空間の有効な部分ではありません。  
  
- **いるとき**Windows Sockets 実装が削除されたため、接続をリセットする必要があります。  
  
- `WSAENOBUFS`Windows ソケットの実装では、バッファーのデッドロックを報告します。  
  
- **接続保持**ソケットが接続されていません。  
  
- **切り離します**記述子がソケットではありません。  
  
- **WSAEOPNOTSUPP MSG_OOB**が指定されている、ソケットの種類ではありませんが、 **SOCK_STREAM**します。  
  
- **WSAESHUTDOWN**ソケットはシャット ダウンされました。 を呼び出すことはできません**送信**後ソケットで`ShutDown`で呼び出された`nHow`1 または 2 に設定します。  
  
- **とき**ソケットがマークされている非ブロッキングされ、要求された操作を停止します。  
  
- **WSAEMSGSIZE** 、ソケットの型が**SOCK_DGRAM**データグラムが Windows ソケットの実装でサポートされる最大値よりも大きいとします。  
  
- **WSAEINVAL**にソケットがバインドされていない**バインド**します。  
  
- **WSAECONNABORTED**タイムアウトまたはその他の障害によって仮想回線が中止されました。  
  
- **WSAECONNRESET**リモート側によって仮想回線がリセットされました。  
  
### <a name="remarks"></a>コメント  
 **送信**接続されているストリームまたはデータグラム ソケットで送信したデータを書き込むために使用します。 データグラム ソケットの場合は注意が必要で、指定した基になるサブネットの IP パケットの最大サイズを超えないように、**とき**内の要素、 [WSADATA](../../mfc/reference/wsadata-structure.md)によって返される構造体`AfxSocketInit`します。 データが長すぎて、基になるプロトコル エラー場合**WSAEMSGSIZE**経由で返されます`GetLastError`データは送信されません。  
  
 なお、データグラムのソケットを正常に完了、**送信**データが正常に送信されたことを示しません。  
  
 `CAsyncSocket`型のオブジェクト**SOCK_STREAM**、書き込まれたバイト数は 1 ~ ローカルおよび外部の両方のホスト上のバッファーの可用性に応じて、要求された長さで指定できます。  
  
### <a name="example"></a>例  
  例を参照してください[CAsyncSocket::OnSend](#onsend)します。  
  
##  <a name="sendto"></a>で  
 特定の宛先にデータを送信するには、このメンバー関数を呼び出します。  
  
```  
int SendTo(
    const void* lpBuf,  
    int nBufLen,  
    UINT nHostPort,  
    LPCTSTR lpszHostAddress = NULL,  
    int nFlags = 0);

 
int SendTo(
    const void* lpBuf,  
    int nBufLen,  
    const SOCKADDR* lpSockAddr,  
    int nSockAddrLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpBuf`  
 転送するデータを保持するバッファー。  
  
 `nBufLen`  
 内のデータの長さ`lpBuf`(バイト単位)。  
  
 `nHostPort`  
 ソケット アプリケーションを識別するポートです。  
  
 `lpszHostAddress`  
 このオブジェクトが接続されているソケットのネットワーク アドレス:「専用、」や「128.56.22.8」などのピリオドで区切られた数字などのコンピューター名。  
  
 `nFlags`  
 呼び出しが行われた場所の方法を指定します。 この関数のセマンティクスは、ソケット オプションによって決まりますと`nFlags`パラメーター。 後者は、次の値のいずれかの C++ と組み合わせることによって構築`OR`演算子。  
  
- **MSG_DONTROUTE**データは、ルーティングされる可能性がありますすべきを指定します。 Windows ソケット サプライヤーは、このフラグを無視を選択できます。  
  
- **MSG_OOB**帯域外のデータを送信 ( **SOCK_STREAM**のみ)。  
  
 `lpSockAddr`  
 ポインター、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)ターゲット ソケットのアドレスを格納する構造体。  
  
 `nSockAddrLen`  
 指定されたアドレスの長さ`lpSockAddr`(バイト単位)。  
  
### <a name="return-value"></a>戻り値  
 エラーが発生しなかった場合`SendTo`送信されたバイト数の合計を返します。 (これはいるによって示される数よりも少ない`nBufLen`)。それ以外の場合、値の**あふれた**返されると特定のエラー コードを呼び出すことによって取得できる[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**正常な[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことを検出します。  
  
- **WSAEACCES**要求されたアドレスは、ブロードキャスト アドレスですが、適切なフラグが設定されませんでした。  
  
- **WSAEINPROGRESS** Windows ソケットのブロック操作が進行中です。  
  
- **WSAEFAULT** 、`lpBuf`または`lpSockAddr`パラメーターは、ユーザー アドレス空間の一部ではない、または`lpSockAddr`引数が小さすぎる (のサイズよりも小さいか、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)構造) です。  
  
- **WSAEINVAL**ホスト名が無効です。  
  
- **いるとき**Windows Sockets 実装が削除されたため、接続をリセットする必要があります。  
  
- `WSAENOBUFS`Windows ソケットの実装では、バッファーのデッドロックを報告します。  
  
- **接続保持**、ソケットが接続されていません ( **SOCK_STREAM**のみ)。  
  
- **切り離します**記述子がソケットではありません。  
  
- **WSAEOPNOTSUPP MSG_OOB**が指定されている、ソケットの種類ではありませんが、 **SOCK_STREAM**します。  
  
- **WSAESHUTDOWN**ソケットがシャット ダウンされたを呼び出すことはなく`SendTo`後ソケットで`ShutDown`で呼び出された`nHow`1 または 2 に設定します。  
  
- **とき**ソケットがマークされている非ブロッキングされ、要求された操作を停止します。  
  
- **WSAEMSGSIZE** 、ソケットの型が**SOCK_DGRAM**データグラムが Windows ソケットの実装でサポートされる最大値よりも大きいとします。  
  
- **WSAECONNABORTED**タイムアウトまたはその他の障害によって仮想回線が中止されました。  
  
- **WSAECONNRESET**リモート側によって仮想回線がリセットされました。  
  
- **WSAEADDRNOTAVAIL**指定したアドレスは、ローカル コンピューターから使用できません。  
  
- **WSAEAFNOSUPPORT**このソケットで指定されているファミリ内のアドレスは使用できません。  
  
- **WSAEDESTADDRREQ**送信先アドレスが必要です。  
  
- **WSAENETUNREACH**ネットワークは、この時点でこのホストから到達できません。  
  
### <a name="remarks"></a>コメント  
 `SendTo`データグラム ソケットまたはストリーム ソケットで使用されており、ソケットで送信したデータを書き込むために使用します。 データグラム ソケットの場合は注意が必要で、指定した基になるサブネットの IP パケットの最大サイズを超えないように、**とき**内の要素、 [WSADATA](../../mfc/reference/wsadata-structure.md)構造体によって入力[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)します。 場合は、データが長すぎて、基になるプロトコル エラー **WSAEMSGSIZE**返されるデータは送信されません。  
  
 注意を正常に完了、`SendTo`データが正常に送信されたことを示しません。  
  
 `SendTo`のみ使用、 **SOCK_DGRAM**で識別される特定のソケットにデータグラムを送信するソケット、`lpSockAddr`パラメーター。  
  
 ブロードキャストを送信する (上、 **SOCK_DGRAM**のみ)、内のアドレス、`lpSockAddr`パラメーターは、特別な IP アドレスを使用して作成する必要があります**INADDR_BROADCAST** (WINSOCK Windows ソケットのヘッダー ファイルで定義されます。H) と共に目的のポート番号。 または、`lpszHostAddress`パラメーターは**NULL**ソケットがブロードキャスト用に構成します。 ブロードキャスト データグラムを断片化が発生することが、サイズを超えたことをお勧めはできません (ヘッダーを除く) のデータグラムのデータ部分が 512 バイトを超えていないことが含まれています。  
  
 IPv6 アドレスを処理する[CAsyncSocket::SendToEx](#sendtoex)します。  
  
##  <a name="sendtoex"></a>CAsyncSocket::SendToEx  
 特定の送信先 (ハンドルの IPv6 アドレス) にデータを送信するには、このメンバー関数を呼び出します。  
  
```  
int SendToEx(
    const void* lpBuf,  
    int nBufLen,  
    UINT nHostPort,  
    LPCTSTR lpszHostAddress = NULL,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpBuf`  
 転送するデータを保持するバッファー。  
  
 `nBufLen`  
 内のデータの長さ`lpBuf`(バイト単位)。  
  
 `nHostPort`  
 ソケット アプリケーションを識別するポートです。  
  
 `lpszHostAddress`  
 このオブジェクトが接続されているソケットのネットワーク アドレス:「専用、」や「128.56.22.8」などのピリオドで区切られた数字などのコンピューター名。  
  
 `nFlags`  
 呼び出しが行われた場所の方法を指定します。 この関数のセマンティクスは、ソケット オプションによって決まりますと`nFlags`パラメーター。 後者は、次の値のいずれかの C++ と組み合わせることによって構築`OR`演算子。  
  
- **MSG_DONTROUTE**データは、ルーティングされる可能性がありますすべきを指定します。 Windows ソケット サプライヤーは、このフラグを無視を選択できます。  
  
- **MSG_OOB**帯域外のデータを送信 ( **SOCK_STREAM**のみ)。  
  
### <a name="return-value"></a>戻り値  
 エラーが発生しなかった場合`SendToEx`送信されたバイト数の合計を返します。 (これはいるによって示される数よりも少ない`nBufLen`)。それ以外の場合、値の**あふれた**返されると特定のエラー コードを呼び出すことによって取得できる[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**正常な[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことを検出します。  
  
- **WSAEACCES**要求されたアドレスは、ブロードキャスト アドレスですが、適切なフラグが設定されませんでした。  
  
- **WSAEINPROGRESS** Windows ソケットのブロック操作が進行中です。  
  
- **WSAEFAULT** 、`lpBuf`または`lpSockAddr`パラメーターは、ユーザー アドレス空間の一部ではない、または`lpSockAddr`引数が小さすぎる (のサイズよりも小さいか、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)構造) です。  
  
- **WSAEINVAL**ホスト名が無効です。  
  
- **いるとき**Windows Sockets 実装が削除されたため、接続をリセットする必要があります。  
  
- `WSAENOBUFS`Windows ソケットの実装では、バッファーのデッドロックを報告します。  
  
- **接続保持**、ソケットが接続されていません ( **SOCK_STREAM**のみ)。  
  
- **切り離します**記述子がソケットではありません。  
  
- **WSAEOPNOTSUPP MSG_OOB**が指定されている、ソケットの種類ではありませんが、 **SOCK_STREAM**します。  
  
- **WSAESHUTDOWN**ソケットがシャット ダウンされたを呼び出すことはなく`SendToEx`後ソケットで`ShutDown`で呼び出された`nHow`1 または 2 に設定します。  
  
- **とき**ソケットがマークされている非ブロッキングされ、要求された操作を停止します。  
  
- **WSAEMSGSIZE** 、ソケットの型が**SOCK_DGRAM**データグラムが Windows ソケットの実装でサポートされる最大値よりも大きいとします。  
  
- **WSAECONNABORTED**タイムアウトまたはその他の障害によって仮想回線が中止されました。  
  
- **WSAECONNRESET**リモート側によって仮想回線がリセットされました。  
  
- **WSAEADDRNOTAVAIL**指定したアドレスは、ローカル コンピューターから使用できません。  
  
- **WSAEAFNOSUPPORT**このソケットで指定されているファミリ内のアドレスは使用できません。  
  
- **WSAEDESTADDRREQ**送信先アドレスが必要です。  
  
- **WSAENETUNREACH**ネットワークは、この時点でこのホストから到達できません。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、同じ[で](#sendto)IPv6 を処理する点を除いて、従来のプロトコルに対応します。  
  
 `SendToEx`データグラム ソケットまたはストリーム ソケットで使用されており、ソケットで送信したデータを書き込むために使用します。 データグラム ソケットの場合は注意が必要で、指定した基になるサブネットの IP パケットの最大サイズを超えないように、**とき**内の要素、 [WSADATA](../../mfc/reference/wsadata-structure.md)構造体によって入力[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)します。 場合は、データが長すぎて、基になるプロトコル エラー **WSAEMSGSIZE**返されるデータは送信されません。  
  
 注意を正常に完了、`SendToEx`データが正常に送信されたことを示しません。  
  
 `SendToEx`のみ使用、 **SOCK_DGRAM**で識別される特定のソケットにデータグラムを送信するソケット、`lpSockAddr`パラメーター。  
  
 ブロードキャストを送信する (上、 **SOCK_DGRAM**のみ)、内のアドレス、`lpSockAddr`パラメーターは、特別な IP アドレスを使用して作成する必要があります**INADDR_BROADCAST** (WINSOCK Windows ソケットのヘッダー ファイルで定義されます。H) と共に目的のポート番号。 または、`lpszHostAddress`パラメーターは**NULL**ソケットがブロードキャスト用に構成します。 ブロードキャスト データグラムを断片化が発生することが、サイズを超えたことをお勧めはできません (ヘッダーを除く) のデータグラムのデータ部分が 512 バイトを超えていないことが含まれています。  
  
##  <a name="setsockopt"></a>CAsyncSocket::SetSockOpt  
 ソケット オプションを設定するには、このメンバー関数を呼び出します。  
  
```  
BOOL SetSockOpt(
    int nOptionName,  
    const void* lpOptionValue,  
    int nOptionLen,  
    int nLevel = SOL_SOCKET);
```  
  
### <a name="parameters"></a>パラメーター  
 `nOptionName`  
 値を設定するソケット オプション。  
  
 `lpOptionValue`  
 要求されたオプションの値を指定するバッファーへのポインター。  
  
 `nOptionLen`  
 サイズ、`lpOptionValue`バッファーのバイト単位です。  
  
 `nLevel`  
 オプションを定義するレベルサポートされているレベルだけが**取得**と**取得できる**です。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**正常な[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことを検出します。  
  
- **WSAEFAULT** `lpOptionValue`プロセスのアドレス空間の有効な部分に含まれない。  
  
- **WSAEINPROGRESS** Windows ソケットのブロック操作が進行中です。  
  
- **WSAEINVAL** `nLevel`が有効でないかの情報は、`lpOptionValue`が無効です。  
  
- **いるとき**接続がタイムアウト場合**接続**が設定されます。  
  
- **WSAENOPROTOOPT**オプションは、不明なまたはサポートされていません。 具体的には、 **:so_broadcast**の種類のソケットでサポートされていない**SOCK_STREAM**、中に**SO_DONTLINGER**、**接続**、 **SO_LINGER**、および**SO_OOBINLINE**型のソケットではサポートされません**SOCK_DGRAM**します。  
  
- **接続保持**接続されたときにリセット**接続**設定されています。  
  
- **切り離します**記述子がソケットではありません。  
  
### <a name="remarks"></a>コメント  
 `SetSockOpt`いずれかの状態の任意の型のソケットに関連付けられているソケット オプションの現在の値を設定します。 オプションは、複数のプロトコル レベルで存在しますが、この仕様には最上位の「ソケット」レベルに存在するためのオプションのみを定義します。 オプションでは、ブロードキャスト メッセージ、ソケットで送信できるしたりかどうかに通常のデータ ストリーム内で優先データが受信したかどうかなどのソケット操作に影響します。  
  
 ソケット オプションの&2; 種類があります: ブール型のオプションを有効にするか、機能や動作を無効にして、整数値または構造体を必要とするオプションです。 ブール値のオプションを有効にする`lpOptionValue`ゼロ以外の整数をポイントします。 オプションを無効に`lpOptionValue`0 に等しい整数を指します。 `nOptionLen`同じになります**sizeof(BOOL)**ブール型のオプションにします。 他のオプションについて`lpOptionValue`整数またはオプションとして、目的の値を含む構造体を指すと`nOptionLen`整数または構造体の長さです。  
  
 **SO_LINGER**ときに実行されるアクション未送信のデータがキューに置かれたソケット上のコントロールと**閉じる**関数が呼び出され、ソケットを閉じる。  
  
 既定では、ソケットをバインドすることはできません (を参照してください[バインド](#bind)) が既に使用しているローカル アドレスにします。 場合によっては、ただし、ある可能性があります"を「再利用この方法でアドレスすること望ましいです。 すべての接続は、ローカルおよびリモート アドレスの組み合わせによって一意に識別、ので、2 つのソケットがリモートのアドレスが異なる限り、同じローカル アドレスにバインドされていることに問題はありません。  
  
 Windows Sockets 実装を通知するためにいる、**バインド**、必要なアドレスが既に別のソケットが使用されているため、ソケットに対しては禁止されませんが、アプリケーションを設定する必要があります、 **SO_REUSEADDR**ソケットを発行する前に、ソケットのオプション、**バインド**を呼び出します。 時刻にのみ、オプションが解釈されることに注意してください、**バインド**呼び出し:、したがって必要はありません (ただし、影響を与えません) には、既存のアドレスにバインドするソケット オプションを設定して設定または後にオプションをリセットして、**バインド**このソケットがいずれかの呼び出しではありません。  
  
 アプリケーションが要求する Windows Sockets 実装が有効にして"keep alive"パケットで伝送制御プロトコル (TCP) 接続の使用を有効にする、**接続**ソケット オプション。 Windows Sockets 実装は、keep alive の使用をサポートしない必要があります場合は、正確なセマンティクスでは実装によって異なりますが、RFC 1122 のセクション 4.2.3.6 に従う必要があります:"Requirements for Internet Hosts-通信レイヤーです。"。 接続がエラー コード"keep alive"の結果として削除された場合**いるとき**、ソケットに対する進行中のすべての呼び出しに返されますが、後続の呼び出しは失敗し、**接続保持**します。  
  
 **低下**オプションは、Nagle アルゴリズムを無効になります。 Nagle アルゴリズムはフルサイズのパケットを送信するまでの非承認送信データのバッファリングによって、ホストによって送信される小規模のパケットの数を減らすために使用します。 ただし、一部のアプリケーションのこのアルゴリズム、パフォーマンスが低下、および**低下**を無効にするために使用できます。 アプリケーションの作成者は設定しないでください**低下**でない限り、その影響よく理解されていると、必要な設定から**低下**ネットワーク パフォーマンスに重大な悪影響を及ぼすことができます。 **低下**のみがサポートされているレベルを使用するソケット オプション**取得できる**; レベルを使用するその他のすべてのオプション**取得**します。  
  
 Windows ソケット装置の実装によっては、場合にデバッグ情報を出力、 **SO_DEBUG**オプションは、アプリケーションで設定します。  
  
 次のオプションはサポートされて`SetSockOpt`します。 型によってアドレス指定されたデータの種類を識別する`lpOptionValue`です。  
  
|値|型|説明|  
|-----------|----------|-------------|  
|**:SO_BROADCAST**|**BOOL**|ソケットのブロードキャスト メッセージの転送を許可します。|  
|**SO_DEBUG**|**BOOL**|デバッグ情報を記録します。|  
|**SO_DONTLINGER**|**BOOL**|ブロックしない**閉じる**未送信のデータを送信するを待機しています。 同じことには、このオプションを設定**SO_LINGER**と**こと**を&0; に設定します。|  
|**SO_DONTROUTE**|**BOOL**|ルーティングしません。 インターフェイスに直接送信します。|  
|**接続**|**BOOL**|Keep alive を送信します。|  
|**SO_LINGER**|**LINGER 構造体**|待機**閉じる**場合は未送信のデータが存在します。|  
|**SO_OOBINLINE**|**BOOL**|通常のデータ ストリームでは、帯域外のデータを受信します。|  
|**SO_RCVBUF**|`int`|受信用のバッファー サイズを指定します。|  
|**SO_REUSEADDR**|**BOOL**|既に使用されているアドレスにバインドするソケットを使用できます。 (See [Bind](#bind).)|  
|**SO_SNDBUF**|`int`|送信用のバッファー サイズを指定します。|  
|**低下**|**BOOL**|送信結合用の Nagle アルゴリズムを無効にします。|  
  
 Berkeley Software Distribution (BSD) オプションはサポートされていません`SetSockOpt`は。  
  
|値|型|説明|  
|-----------|----------|-------------|  
|**SO_ACCEPTCONN**|**BOOL**|ソケットはリッスンしてください。|  
|**SO_ERROR**|`int`|エラー状態を取得し、クリアします。|  
|**SO_RCVLOWAT**|`int`|低水位マークが表示されます。|  
|**SO_RCVTIMEO**|`int`|受信タイムアウト|  
|**SO_SNDLOWAT**|`int`|下限値を送信します。|  
|**SO_SNDTIMEO**|`int`|タイムアウトを送信します。|  
|**SO_TYPE**|`int`|ソケットの種類です。|  
|**なる**||IP ヘッダーには、オプションのフィールドを設定します。|  
  
##  <a name="shutdown"></a>CAsyncSocket::ShutDown  
 呼び出しを無効にするには、このメンバー関数は、次の送信、受信すると、ソケットにまたはその両方です。  
  
```  
BOOL ShutDown(int nHow = sends);
```  
  
### <a name="parameters"></a>パラメーター  
 `nHow`  
 操作の種類を示すフラグが不要になったできる、次の列挙値を使用します。  
  
- **受信 = 0**  
  
- **送信 = 1**  
  
- **両方 = 2**  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**正常な[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことを検出します。  
  
- **WSAEINVAL** `nHow`が無効です。  
  
- **WSAEINPROGRESS** Windows ソケットのブロック操作が進行中です。  
  
- **接続保持**、ソケットが接続されていません ( **SOCK_STREAM**のみ)。  
  
- **切り離します**記述子がソケットではありません。  
  
### <a name="remarks"></a>コメント  
 `ShutDown`受信と送信、またはその両方を無効にするすべての種類のソケットで使用されます。 場合`nHow`が 0 の場合での受信は、ソケットは使用できません。 下位のプロトコル層への影響はありません。  
  
 伝送制御プロトコル (TCP) では、TCP ウィンドウが変更されていないと、受信データになります (ただし、応答ではありません) ウィンドウがなくなるまでに受け入れられます。 ユーザー データグラム プロトコル (UDP) では、受信したデータグラムが受け入れられるキューとします。 いかなる場合で、ICMP エラー パケットが生成されます。 場合`nHow`1 では、その後送信は許可されません。 TCP ソケット FIN が送信されます。 設定`nHow`2 に、両方の送信を無効にし、上記で説明したときに受信します。  
  
 注意`ShutDown`はない閉じるソケット、およびソケットに接続されているリソースは解放されませんまで**閉じる**と呼びます。 アプリケーションは、シャット ダウン後に、ソケットを再利用することに依存する必要があります。 具体的には、Windows Sockets 実装は、の使用をサポートする必要はありません**接続**このようなソケットにします。  
  
### <a name="example"></a>例  
  例を参照してください[CAsyncSocket::OnReceive](#onreceive)します。  
  
##  <a name="socket"></a>CASyncSocket::Socket  
 ソケットのハンドルを割り当てます。  
  
```  
BOOL Socket(
    int nSocketType = SOCK_STREAM,  
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,  
    int nProtocolType = 0,  
    int nAddressFormat = PF_INET);
```  
  
### <a name="parameters"></a>パラメーター  
 `nSocketType`  
 指定`SOCK_STREAM`または`SOCK_DGRAM`です。  
  
 `lEvent`  
 アプリケーションが関心があるネットワーク イベントの組み合わせを指定するビットマスク。  
  
- `FD_READ`: 読み取り用の準備完了の通知を受信するとしてください。  
  
- `FD_WRITE`: 書き込みのための準備完了の通知を受信するとしてください。  
  
- `FD_OOB`: の帯域外のデータの追加の通知を受信するとしてください。  
  
- `FD_ACCEPT`: 通知の受信接続を受信するとしてください。  
  
- `FD_CONNECT`: 完成した接続の通知を受信するとしてください。  
  
- `FD_CLOSE`: ソケットの終了の通知を受信するとしてください。  
  
 `nProtocolType`  
 指定されたアドレス ファミリに固有のソケットで使用するプロトコルです。  
  
 `nAddressFormat`  
 ファミリの仕様に対応します。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は、`TRUE` を返します。それ以外の場合は、`FALSE` を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ソケットのハンドルを割り当てます。 呼び出しません[CAsyncSocket::Bind](#bind)に呼び出す必要があるために、指定したアドレスにソケットをバインドする`Bind`以降を指定したアドレスにソケットをバインドします。 使用する[CAsyncSocket::SetSockOpt](#setsockopt)バインドされている前に、ソケット オプションを設定します。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CSocket クラス](../../mfc/reference/csocket-class.md)   
 [CSocketFile クラス](../../mfc/reference/csocketfile-class.md)

