---
title: "CSocketFile クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSocketFile
dev_langs:
- C++
helpviewer_keywords:
- networks [C++], archive
- serialization [C++], network
- networks [C++], serializing to
- CSocketFile class
- archives [C++], network
- SOCKET handle
ms.assetid: 7924c098-5f72-40d6-989d-42800a47958f
caps.latest.revision: 24
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
ms.openlocfilehash: 6ca331c07e0a9fc48f152042fcccd5c38e743ccf
ms.lasthandoff: 02/24/2017

---
# <a name="csocketfile-class"></a>CSocketFile クラス
Windows ソケットを使ったネットワーク間でのデータの送受信に使われる `CFile` オブジェクトです。  
  
## <a name="syntax"></a>構文  
  
```  
class CSocketFile : public CFile  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSocketFile::CSocketFile](#csocketfile)|`CSocketFile` オブジェクトを構築します。|  
  
## <a name="remarks"></a>コメント  
 アタッチすることができます、`CSocketFile`オブジェクトを`CSocket`この目的のオブジェクト。 でき、接続には、通常、`CSocketFile`オブジェクトを`CArchive`MFC のシリアル化を使用してデータの送受信を簡略化するオブジェクト。  
  
 (送信) データをシリアル化するに挿入するを呼び出すと、アーカイブ`CSocketFile`メンバー関数は、データを書き込む、`CSocket`オブジェクトです。 逆シリアル化する (受信) アーカイブからのデータを抽出します。 これにより、アーカイブを呼び出す`CSocketFile`からデータを読み取るメンバー関数、`CSocket`オブジェクトです。  
  
> [!TIP]
>  使用するだけでなく`CSocketFile`」の説明に従って、として使用できますが、スタンドアロンのファイル オブジェクトの場合と同様`CFile`、その基本クラスです。 使用することも`CSocketFile`アーカイブ ベースの MFC シリアル化関数を使用します。 `CSocketFile`一部サポートされていません`CFile`の MFC はデフォルトで一部の機能をシリアル化関数は、互換性がない`CSocketFile`します。 これは特にの場合に、`CEditView`クラスです。 シリアル化しないでください`CEditView`を使用してデータを`CArchive`オブジェクトに関連付けられて、`CSocketFile`オブジェクトを使用して`CEditView::SerializeRaw`; を使用して**CEditView::Serialize**代わりにします。 `SerializeRaw`関数などを持っている関数、ファイル オブジェクトが必要ですが`Seek`、その`CSocketFile`はありません。  
  
 使用すると`CArchive`と`CSocketFile`と`CSocket`、状況が生じる場所**CSocket::Receive**ループに入る (によって**PumpMessages(FD_READ)**) 要求されたバイト数の待機しています。 これは、Windows ソケット FD_READ 通知ごとに&1; つだけ受信呼び出しを許可するため、`CSocketFile`と`CSocket`FD_READ ごとの複数の受信呼び出しを許可します。 読み取るデータがない場合に、FD_READ 表示された場合、アプリケーションがハングします。 別の FD_READ を取得しない場合、アプリケーションは、ソケット上での通信を停止します。  
  
 次のように、この問題を解決できます。 `OnReceive`メソッドを呼び出し、socket クラスの**CAsyncSocket::IOCtl (FIONREAD、...)**を呼び出す前に、`Serialize`ソケットから読み取る必要なデータが 1 つの TCP パケット (ネットワーク中、通常、少なくとも 1096 バイトの最大転送ユニット) のサイズを超えると、メッセージ クラスのメソッドです。 使用可能なデータのサイズが小さいと、必要以上の場合は、すべてのデータを受信して、読み取り操作を開始しています。  
  
 次の例で`m_dwExpected`は、ユーザーが受信されるバイトのおおよその数。 宣言している他の場所で、コード内と見なされます。  
  
 [!code-cpp[NVC_MFCSocketThread&4;](../../mfc/reference/codesnippet/cpp/csocketfile-class_1.cpp)]  
  
 詳細については、次を参照してください。 [MFC における Windows ソケット](../../mfc/windows-sockets-in-mfc.md)、 [Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)、だけでなく[Windows Sockets 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CSocketFile`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxsock.h  
  
##  <a name="a-namecsocketfilea--csocketfilecsocketfile"></a><a name="csocketfile"></a>CSocketFile::CSocketFile  
 `CSocketFile` オブジェクトを構築します。  
  
```  
explicit CSocketFile(
    CSocket* pSocket,  
    BOOL bArchiveCompatible = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSocket`  
 アタッチするソケット、`CSocketFile`オブジェクトです。  
  
 `bArchiveCompatible`  
 ファイル オブジェクトで使用するかどうかを指定する`CArchive`オブジェクトです。 渡す**FALSE**を使用する場合にのみ、`CSocketFile`スタンドアロンと同様に、単独でオブジェクト`CFile`オブジェクト、制限事項があります。 このフラグを変更する方法、`CArchive`オブジェクトに関連付けられて、`CSocketFile`オブジェクトは読み取り用のバッファーを管理します。  
  
### <a name="remarks"></a>コメント  
 オブジェクトのデストラクターの関連付けを解除自体のソケット オブジェクトからオブジェクトがスコープ外になるかが削除されるときです。  
  
> [!NOTE]
>  A`CSocketFile`なし (制限あり) ファイルとしても使用できる、`CArchive`オブジェクトです。 既定では、`CSocketFile`コンス トラクターの`bArchiveCompatible`パラメーターは**TRUE**します。 これは、アーカイブで使用するのファイル オブジェクトであることを指定します。 使用するには、アーカイブせずにファイル オブジェクトを渡す**FALSE**で、`bArchiveCompatible`パラメーター。  
  
 その「アーカイブ互換性あり」モードで、`CSocketFile`オブジェクトとパフォーマンスが向上「デッドロック」の危険性を軽減 デッドロックは、送信側と受信側の両方のソケットは、互いにまたは共通のリソースを待機している場合に発生します。 場合に、このような状況が発生する可能性があります、`CArchive`と協力して、オブジェクト、`CSocketFile`の場合と方法、`CFile`オブジェクトです。 `CFile`アーカイブが受信した場合、要求したバイト数、ファイルの末尾に達したことを想定することができます。  
  
 `CSocketFile`、ただし、データはメッセージ ベース; バッファーは、複数のメッセージを含めることができます、そのために要求されたバイト数よりも少ないの受信ファイルの終わりを意味しません。 アプリケーションでは、それほどで、ここではブロックしません`CFile`バッファーが空になるまで、バッファーからメッセージを読み取るを続けます。 [CArchive::IsBufferEmpty](../../mfc/reference/carchive-class.md#isbufferempty)関数は、このような場合のアーカイブのバッファーの状態を監視するために役立ちます。  
  
 使用の詳細については`CSocketFile`、記事を参照して[Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)と[Windows ソケット: 例のソケットを使用してアーカイブ](../../mfc/windows-sockets-example-of-sockets-using-archives.md)します。  
  
## <a name="see-also"></a>関連項目  
 [CFile クラス](../../mfc/reference/cfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket クラス](../../mfc/reference/casyncsocket-class.md)   
 [CSocket クラス](../../mfc/reference/csocket-class.md)

