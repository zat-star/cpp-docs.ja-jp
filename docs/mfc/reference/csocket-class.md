---
title: "CSocket クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSocket
- AFXSOCK/CSocket
- AFXSOCK/CSocket::CSocket
- AFXSOCK/CSocket::Attach
- AFXSOCK/CSocket::CancelBlockingCall
- AFXSOCK/CSocket::Create
- AFXSOCK/CSocket::FromHandle
- AFXSOCK/CSocket::IsBlocking
- AFXSOCK/CSocket::OnMessagePending
dev_langs:
- C++
helpviewer_keywords:
- WinSock CSocket class
- CSocket class
- SOCKET handle
- sockets classes
ms.assetid: 7f23c081-d24d-42e3-b511-8053ca53d729
caps.latest.revision: 30
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 451ea100dbf02e365204fe4fdf1c380e855d8231
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="csocket-class"></a>CSocket クラス
派生した`CAsyncSocket`、Windows ソケット API のカプセル化を継承しより高い抽象化レベルを表す、`CAsyncSocket`オブジェクトです。  
  
## <a name="syntax"></a>構文  
  
```  
class CSocket : public CAsyncSocket  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSocket::CSocket](#csocket)|`CSocket` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Csocket::attach](#attach)|アタッチ、**ソケット**へのハンドル、`CSocket`オブジェクトです。|  
|[CSocket::CancelBlockingCall](#cancelblockingcall)|現在進行中のブロッキング呼び出しをキャンセルします。|  
|[CSocket::Create](#create)|ソケットを作成します。|  
|[CSocket::FromHandle](#fromhandle)|ポインターを返す、`CSocket`を指定したオブジェクト、**ソケット**を処理します。|  
|[CSocket::IsBlocking](#isblocking)|ブロッキング呼び出しが実行中かどうかを判断します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[種類](#onmessagepending)|ブロッキング呼び出しが完了するを待機中にメッセージを保留中の処理に呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 `CSocket`クラスと動作`CSocketFile`と`CArchive`データの送受信を管理します。  
  
 A`CSocket`オブジェクトも用意されてをブロックする同期操作に必要不可欠である`CArchive`です。 など、機能をブロック`Receive`、 `Send`、 `ReceiveFrom`、 `SendTo`、および`Accept`(から継承されたすべて`CAsyncSocket`)、戻ることはありません、`WSAEWOULDBLOCK`エラー`CSocket`します。 代わりに、これらの関数は、操作が完了するまで待機します。 元の呼び出しが中止され、エラー、さらに、`WSAEINTR`場合`CancelBlockingCall`がブロックしているこれらの関数のいずれかの中に呼び出されます。  
  
 使用する、`CSocket`オブジェクト、コンス トラクターを呼び出して物書き`Create`すると、基になる`SOCKET`処理 (型`SOCKET`)。 既定のパラメーターの`Create`ストリーム ソケットを作成、ソケットを使用していない場合は、`CArchive`オブジェクト、代わりに、データグラム ソケットを作成またはサーバー ソケットを作成する特定のポートにバインドするパラメーターを指定することができます。 使用してクライアント ソケット接続`Connect`クライアント側と`Accept`サーバー側でします。 作成し、`CSocketFile`オブジェクトし、それに関連付ける、`CSocket`内のオブジェクト、`CSocketFile`コンス トラクターです。 次に、作成、`CArchive`を送信するためのオブジェクトと (必要に応じて)、データを受信するための&1; つ関連付けるし、これらを`CSocketFile`内のオブジェクト、`CArchive`コンス トラクターです。 通信が完了すると、破棄、 `CArchive`、 `CSocketFile`、および`CSocket`オブジェクトです。 `SOCKET`データ型は、記事で説明されて[Windows ソケット: バック グラウンド](../../mfc/windows-sockets-background.md)します。  
  
 使用すると`CArchive`と`CSocketFile`と`CSocket`、状況が生じる場所`CSocket::Receive`ループに入る (によって`PumpMessages(FD_READ)`) 要求されたバイト数の待機しています。 これは、Windows ソケット FD_READ 通知ごとに&1; つだけ受信呼び出しを許可するため、`CSocketFile`と`CSocket`FD_READ ごとの複数の受信呼び出しを許可します。 読み取るデータがない場合に、FD_READ 表示された場合、アプリケーションがハングします。 別の FD_READ を取得しない場合、アプリケーションは、ソケット上での通信を停止します。  
  
 次のように、この問題を解決できます。 `OnReceive`メソッドを呼び出し、socket クラスの`CAsyncSocket::IOCtl(FIONREAD, ...)`を呼び出す前に、`Serialize`ソケットから読み取る必要なデータが 1 つの TCP パケット (ネットワーク中、通常、少なくとも 1096 バイトの最大転送ユニット) のサイズを超えると、メッセージ クラスのメソッドです。 使用可能なデータのサイズが小さいと、必要以上の場合は、すべてのデータを受信して、読み取り操作を開始しています。  
  
 次の例で`m_dwExpected`は、ユーザーが受信されるバイトのおおよその数。 宣言している他の場所で、コード内と見なされます。  
  
 [!code-cpp[NVC_MFCSocketThread&4;](../../mfc/reference/codesnippet/cpp/csocket-class_1.cpp)]  
  
> [!NOTE]
>  静的にリンクされた MFC アプリケーションのセカンダリ スレッドで MFC ソケットを使用する場合を呼び出す必要があります`AfxSocketInit`ソケット ライブラリを初期化するソケットを使用する各スレッドにします。 既定では、`AfxSocketInit`はプライマリ スレッドでのみ呼び出されます。  
  
 詳細については、次を参照してください。 [MFC における Windows ソケット](../../mfc/windows-sockets-in-mfc.md)、 [Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)、 [Windows ソケット: 作業のアーカイブ付きソケット](../../mfc/windows-sockets-how-sockets-with-archives-work.md)、 [Windows ソケット: 動作シーケンス](../../mfc/windows-sockets-sequence-of-operations.md)、 [Windows ソケット: 例のソケットを使用してアーカイブ](../../mfc/windows-sockets-example-of-sockets-using-archives.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAsyncSocket](../../mfc/reference/casyncsocket-class.md)  
  
 `CSocket`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxsock.h  
  
##  <a name="attach"></a>Csocket::attach  
 アタッチするには、このメンバー関数を呼び出す、`hSocket`へのハンドル、`CSocket`オブジェクトです。  
  
```  
BOOL Attach(SOCKET hSocket);
```  
  
### <a name="parameters"></a>パラメーター  
 `hSocket`  
 ソケットのハンドルが含まれています。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は&0; 以外を返します。  
  
### <a name="remarks"></a>コメント  
 **ソケット**ハンドルが、オブジェクトに格納されている[m_hSocket](../../mfc/reference/casyncsocket-class.md#m_hsocket)データ メンバーです。  
  
 詳細については、次を参照してください。 [Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSocketThread&#1;](../../mfc/reference/codesnippet/cpp/csocket-class_2.h)]  
  
 [!code-cpp[NVC_MFCSocketThread&#2;](../../mfc/reference/codesnippet/cpp/csocket-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCSocketThread&#3;](../../mfc/reference/codesnippet/cpp/csocket-class_4.cpp)]  
  
##  <a name="cancelblockingcall"></a>CSocket::CancelBlockingCall  
 現在実行中のブロッキング呼び出しをキャンセルするには、このメンバー関数を呼び出します。  
  
```  
void CancelBlockingCall();
```  
  
### <a name="remarks"></a>コメント  
 この関数は、このソケットに対する未処理のブロック操作をキャンセルします。 元のブロッキング呼び出しをエラーのため、できるだけ早く終了**WSAEINTR**します。  
  
 ブロッキング**接続**操作、Windows ソケットの実装が終了ブロッキング呼び出しが、できない場合がありますソケット リソースは、接続が完了しました (され、リセットされるまで) にリリースされるとすぐにまたはタイムアウトします。 これに、アプリケーションは、新しいソケット (使用可能なソケットがない場合) を開くか、同じピアに接続するためにすぐにしようとする場合にのみ起こります。  
  
 以外のすべての操作をキャンセル**Accept**不定状態で、ソケットのままにします。 アプリケーションが確実に実行できない依存することが唯一の操作への呼び出しは、アプリケーションでは、ソケットでのブロック操作をキャンセルした場合**閉じる**、いくつかの Windows Sockets 実装ではその他の操作が機能します。 アプリケーションの最大限の移植性が必要な場合は、実行する操作をキャンセルした後に依存しないように注意する必要があります。  
  
 詳細については、次を参照してください。 [Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)します。  
  
##  <a name="create"></a>CSocket::Create  
 呼び出す、**作成**メンバー関数の後に、Windows ソケットを作成し、接続のソケット オブジェクトを構築します。  
  
```  
BOOL Create(
    UINT nSocketPort = 0,  
    int nSocketType = SOCK_STREAM,  
    LPCTSTR lpszSocketAddress = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `nSocketPort`  
 Mfc でポートを選択する場合、ソケットまたは 0 で使用する特定のポートです。  
  
 `nSocketType`  
 **SOCK_STREAM**または**SOCK_DGRAM**します。  
  
 `lpszSocketAddress`  
 接続されたソケット、「128.56.22.8」などのピリオドで区切られた数のネットワーク アドレスを含む文字列へのポインター。 渡す、 **NULL**このパラメーターを文字列、 **CSocket**インスタンスがすべてのネットワーク インターフェイス上のクライアント アクティビティを待機する必要があります。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合`GetLastError`します。  
  
### <a name="remarks"></a>コメント  
 **作成**を呼び出して**バインド**指定のアドレスにソケットをバインドします。 次の種類のソケットがサポートされています。  
  
- **SOCK_STREAM**シーケンス処理、信頼性の高い、双方向、接続に基づくバイト ストリームを提供します。 インターネット アドレス ファミリ用には、伝送制御プロトコル (TCP) を使用します。  
  
- **SOCK_DGRAM**固定 (通常はわずか) の最大長のバッファーがコネクションレスで信頼性の低いは、データグラムをサポートしています。 インターネット アドレス ファミリ用には、ユーザー データグラム プロトコル (UDP) を使用します。 このオプションを使用する、ソケットを使用する必要がありますいない、`CArchive`オブジェクトです。  
  
    > [!NOTE]
    >  **Accept**メンバー関数は、新しい空への参照を受け取ります`CSocket`オブジェクトをパラメーターとして。 呼び出す前に、このオブジェクトを構築する必要があります**Accept**します。 注意このソケット オブジェクトがスコープ接続は閉じられますのなくなる場合。 呼び出す必要はありません**作成**この新しいソケット オブジェクトです。  
  
 ストリームとデータグラム ソケットの詳細については、記事を参照してください。 [Windows ソケット: バック グラウンド](../../mfc/windows-sockets-background.md)、 [Windows ソケット: ポートとソケット アドレス](../../mfc/windows-sockets-ports-and-socket-addresses.md)、および[Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)します。  
  
##  <a name="csocket"></a>CSocket::CSocket  
 `CSocket` オブジェクトを構築します。  
  
```  
CSocket();
```  
  
### <a name="remarks"></a>コメント  
 作成した後を呼び出す必要があります、**作成**メンバー関数。  
  
 詳細については、次を参照してください。 [Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)します。  
  
##  <a name="fromhandle"></a>CSocket::FromHandle  
 ポインターを返す、`CSocket`オブジェクトです。  
  
```  
static CSocket* PASCAL FromHandle(SOCKET hSocket);
```  
  
### <a name="parameters"></a>パラメーター  
 `hSocket`  
 ソケットのハンドルが含まれています。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CSocket`オブジェクト、または**NULL**がある場合ない`CSocket`オブジェクトにアタッチされて`hSocket`します。  
  
### <a name="remarks"></a>コメント  
 指定されている場合、**ソケット**を処理する場合、`CSocket`ハンドルには、オブジェクトはアタッチされていない、メンバー関数を返します**NULL**一時オブジェクトは作成されません。  
  
 詳細については、次を参照してください。 [Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)します。  
  
##  <a name="isblocking"></a>CSocket::IsBlocking  
 このメンバー関数を呼び出してブロッキング呼び出しが行われているかを決定します。  
  
```  
BOOL IsBlocking();
```  
  
### <a name="return-value"></a>戻り値  
 ソケットがブロッキングされている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)します。  
  
##  <a name="onmessagepending"></a>種類  
 Windows からの特定のメッセージを確認して、ソケットに対応するには、この関数をオーバーライドします。  
  
```  
virtual BOOL OnMessagePending();
```  
  
### <a name="return-value"></a>戻り値  
 メッセージが処理された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 これは、高度なオーバーライドします。  
  
 Framework 呼び出し`OnMessagePending`ソケットがアプリケーションに関心のあるメッセージを処理する機会を提供する Windows メッセージ ポンプを行って中です。 使用する方法の例については`OnMessagePending`、記事を参照して[Windows ソケット: ソケット クラスから派生する](../../mfc/windows-sockets-deriving-from-socket-classes.md)です。  
  
 詳細については、次を参照してください。 [Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)します。  
  
## <a name="see-also"></a>関連項目  
 [CAsyncSocket クラス](../../mfc/reference/casyncsocket-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket クラス](../../mfc/reference/casyncsocket-class.md)   
 [CSocketFile クラス](../../mfc/reference/csocketfile-class.md)

