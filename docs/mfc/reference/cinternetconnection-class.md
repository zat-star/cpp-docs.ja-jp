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
- CInternetConnection
dev_langs:
- C++
helpviewer_keywords:
- asynchronous connections
- CInternetConnection class
- Internet connections
ms.assetid: 62a5d1c3-8471-4e36-a064-48831829b2a7
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 7f99562e0c6103fc3f46a7fe28f9d2f2efff0a01
ms.lasthandoff: 02/24/2017

---
# <a name="cinternetconnection-class"></a>関数のクラス
インターネット サーバーへの接続を管理します。  
  
## <a name="syntax"></a>構文  
  
```  
class CInternetConnection : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CInternetConnection::CInternetConnection](#cinternetconnection)|`CInternetConnection` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CInternetConnection::GetContext](#getcontext)|この接続オブジェクトのコンテキスト ID を取得します。|  
|[CInternetConnection::GetServerName](#getservername)|接続に関連付けられているサーバーの名前を取得します。|  
|[CInternetConnection::GetSession](#getsession)|ポインターを取得、 [CInternetSession](../../mfc/reference/cinternetsession-class.md)接続に関連付けられているオブジェクト。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CInternetConnection::operator HINTERNET](#operator_hinternet)|インターネット セッションへのハンドル。|  
  
## <a name="remarks"></a>コメント  
 MFC クラスの基本クラスである[詳細](../../mfc/reference/cftpconnection-class.md)、[関数](../../mfc/reference/chttpconnection-class.md)、および[関数](../../mfc/reference/cgopherconnection-class.md)します。 これらの各クラスは、それぞれ、FTP、HTTP、または gopher サーバーと通信するため追加機能を提供します。  
  
 インターネット サーバーと直接通信するためにする必要があります、 [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトと`CInternetConnection`オブジェクトです。  
  
 WinInet クラスの動作に関する詳細については、記事を参照してください。 [WinInet を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CInternetConnection`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxinet.h  
  
##  <a name="a-namecinternetconnectiona--cinternetconnectioncinternetconnection"></a><a name="cinternetconnection"></a>CInternetConnection::CInternetConnection  
 このメンバー関数が呼び出されます、`CInternetConnection`オブジェクトを作成します。  
  
```  
CInternetConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSession`  
 ポインター、 [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトです。  
  
 `pstrServer`  
 サーバー名を含む文字列へのポインター。  
  
 `nPort`  
 この接続のインターネットのポートを識別する番号。  
  
 `dwContext`  
 コンテキスト識別子、`CInternetConnection`オブジェクトです。 参照してください**解説**の詳細については`dwContext`です。  
  
### <a name="remarks"></a>コメント  
 呼び出さないように`CInternetConnection`として考えてください。 代わりに、、 [CInternetSession](../../mfc/reference/cinternetsession-class.md)を確立する接続の種類のメンバー関数。  
  
- [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)  
  
- [代わりに](../../mfc/reference/cinternetsession-class.md#gethttpconnection)  
  
- [代わり](../../mfc/reference/cinternetsession-class.md#getgopherconnection)  
  
 既定値`dwContext`MFC から送信される、 `CInternetConnection`-派生オブジェクトから、 [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトの作成、**です**-派生オブジェクト。 既定値を 1 に設定します。、、特定のコンテキストでの識別子が明示的に指定することができます、 [CInternetSession](../../mfc/reference/cinternetsession-class.md#cinternetsession)接続のコンス トラクターです。 オブジェクトとその動作はそのコンテキスト ID に関連付けられる コンテキスト識別子が返される[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)特定ために使用するオブジェクトの状態をします。 記事を参照して[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)詳細については、コンテキスト識別子。  
  
##  <a name="a-namegetcontexta--cinternetconnectiongetcontext"></a><a name="getcontext"></a>CInternetConnection::GetContext  
 このセッションのコンテキスト ID を取得するには、このメンバー関数を呼び出します。  
  
```  
DWORD_PTR GetContext() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーション設定したコンテキスト id。  
  
### <a name="remarks"></a>コメント  
 コンテキスト ID が指定した[CInternetSession](../../mfc/reference/cinternetsession-class.md)に伝達および`CInternetConnection`- と[CInternetFile](../../mfc/reference/cinternetfile-class.md)-への接続を開き、関数の呼び出しで異なる方法で指定されていない場合、クラスを派生します。 コンテキスト ID が指定したオブジェクトのすべての操作に関連付けられているし、によって返される操作のステータス情報を識別する[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)します。  
  
 方法の詳細についての**GetContext**ユーザーのステータス情報を提供するためには、記事を参照して[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)詳細については、コンテキスト識別子。  
  
##  <a name="a-namegetservernamea--cinternetconnectiongetservername"></a><a name="getservername"></a>CInternetConnection::GetServerName  
 このインターネット接続に関連付けられているサーバーの名前を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetServerName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 この接続オブジェクトを使用するサーバーの名前。  
  
##  <a name="a-namegetsessiona--cinternetconnectiongetsession"></a><a name="getsession"></a>CInternetConnection::GetSession  
 ポインターを取得するには、このメンバー関数を呼び出す、`CInternetSession`この接続に関連付けられているオブジェクト。  
  
```  
CInternetSession* GetSession() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CInternetSession](../../mfc/reference/cinternetsession-class.md)インターネット接続オブジェクトに関連付けられているオブジェクト。  
  
##  <a name="a-nameoperatorhinterneta--cinternetconnectionoperator-hinternet"></a><a name="operator_hinternet"></a>CInternetConnection::operator HINTERNET  
 この演算子を使用して、現在のインターネット セッションの API レベルのハンドルを取得します。  
  
```  
operator HINTERNET() const;  
```  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)




