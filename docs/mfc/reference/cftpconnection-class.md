---
title: "クラスの詳細 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFtpConnection
dev_langs:
- C++
helpviewer_keywords:
- CFtpConnection class
- FTP (File Transfer Protocol), establishing connections
- Internet connections, FTP
- Internet services, FTP
ms.assetid: 5e3a0501-8893-49cf-a3d5-0628d8d6b936
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
ms.openlocfilehash: ebfe4078bf70d0afc2d36a222b61c11dbaf7c64d
ms.lasthandoff: 02/24/2017

---
# <a name="cftpconnection-class"></a>クラスの詳細
インターネット サーバーへの FTP 接続を管理でき、そのサーバー上のディレクトリおよびファイルを直接操作できます。  
  
## <a name="syntax"></a>構文  
  
```  
class CFtpConnection : public CInternetConnection  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CFtpConnection::CFtpConnection](#cftpconnection)|`CFtpConnection` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFtpConnection::Command](#command)|FTP サーバーに直接コマンドを送信します。|  
|[CFtpConnection::CreateDirectory](#createdirectory)|サーバー上のディレクトリを作成します。|  
|[CFtpConnection::GetCurrentDirectory](#getcurrentdirectory)|この接続の現在のディレクトリを取得します。|  
|[CFtpConnection::GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl)|この接続を URL としての現在のディレクトリを取得します。|  
|[CFtpConnection::GetFile](#getfile)|接続先のサーバーからファイルを取得します。|  
|[CFtpConnection::OpenFile](#openfile)|接続されているサーバー上のファイルを開きます。|  
|[CFtpConnection::PutFile](#putfile)|サーバー上のファイルを配置します。|  
|[CFtpConnection::Remove](#remove)|サーバーからファイルを削除します。|  
|[CFtpConnection::RemoveDirectory](#removedirectory)|サーバーから、指定したディレクトリを削除します。|  
|[CFtpConnection::Rename](#rename)|サーバー上のファイルの名前を変更します。|  
|[CFtpConnection::SetCurrentDirectory](#setcurrentdirectory)|現在の FTP ディレクトリを設定します。|  
  
## <a name="remarks"></a>コメント  
 FTP では、MFC WinInet クラスによって認識される&3; つのインターネット サービスの&1; つです。  
  
 Ftp サーバーと通信するためのインスタンスを最初に作成する必要があります[CInternetSession](../../mfc/reference/cinternetsession-class.md)、し、作成、`CFtpConnection`オブジェクトです。 作成しないで、`CFtpConnection`オブジェクトに直接を呼び出す[CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)、作成、`CFtpConnection`オブジェクトし、ポインターを返します。  
  
 方法について説明する`CFtpConnection`他のインターネットの MFC クラスと動作は、記事を参照して[WinInet を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)します。 サービス、HTTP および gopher は、クラスを参照してください。 サポートされている他の&2; つとの通信の詳細については[関数](../../mfc/reference/chttpconnection-class.md)と[関数](../../mfc/reference/cgopherconnection-class.md)します。  
  
## <a name="example"></a>例  
  例を参照して、[関数](../../mfc/reference/cftpfilefind-class.md)クラスの概要です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [関数](../../mfc/reference/cinternetconnection-class.md)  
  
 `CFtpConnection`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxinet.h  
  
##  <a name="a-namecftpconnectiona--cftpconnectioncftpconnection"></a><a name="cftpconnection"></a>CFtpConnection::CFtpConnection  
 このメンバー関数が作成すると呼ばれる、`CFtpConnection`オブジェクトです。  
  
```  
CFtpConnection(
    CInternetSession* pSession,  
    HINTERNET hConnected,  
    LPCTSTR pstrServer,  
    DWORD_PTR dwContext);

 
CFtpConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    DWORD_PTR dwContext = 0,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    BOOL bPassive = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSession`  
 関連するへのポインター [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトです。  
  
 `hConnected`  
 現在のインターネット セッションの Windows ハンドル。  
  
 `pstrServer`  
 FTP サーバーの名前を含む文字列へのポインター。  
  
 `dwContext`  
 操作のコンテキストの識別子です。 `dwContext`によって返される操作のステータス情報を識別する[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)します。 既定値を 1 に設定します。ただし、操作の特定のコンテキスト ID を明示的に割り当てることができます。 オブジェクトとその動作はそのコンテキスト ID に関連付けられる  
  
 `pstrUserName`  
 ログインするユーザーの名前を指定する null で終わる文字列へのポインター。 場合**NULL**、既定値は匿名です。  
  
 `pstrPassword`  
 ログインに使用するパスワードを指定する null で終わる文字列へのポインター。 両方`pstrPassword`と`pstrUserName`は**NULL**、匿名の既定のパスワードは、ユーザーの電子メール名。 場合`pstrPassword`は**NULL** (または空の文字列) が、`pstrUserName`は**NULL**、空白のパスワードを使用します。 次の表の&4; 種類の設定では、動作`pstrUserName`と`pstrPassword`:  
  
|`pstrUserName`|`pstrPassword`|FTP サーバーに送信されるユーザー名|FTP サーバーに送信されるパスワード|  
|--------------------|--------------------|---------------------------------|---------------------------------|  
|**NULL**または""|**NULL**または""|「匿名」|ユーザーの電子メール名|  
|非- **NULL**文字列|**NULL**または""|`pstrUserName`|" "|  
|**NULL**以外**NULL**文字列|**エラー**|**エラー**||  
|非- **NULL**文字列|非- **NULL**文字列|`pstrUserName`|`pstrPassword`|  
  
 `nPort`  
 サーバーで使用する TCP/IP ポートを識別する番号。  
  
 `bPassive`  
 この FTP セッションのパッシブまたはアクティブ モードを指定します。 場合に設定**TRUE**、Win32 API を設定して`dwFlag`に**INTERNET_FLAG_PASSIVE**します。  
  
### <a name="remarks"></a>コメント  
 作成しないで、`CFtpConnection`オブジェクトに直接します。 代わりに、 [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)、作成、 **CFptConnection**オブジェクトです。  
  
##  <a name="a-namecommanda--cftpconnectioncommand"></a><a name="command"></a>CFtpConnection::Command  
 FTP サーバーに直接コマンドを送信します。  
  
```  
CInternetFile* Command(
    LPCTSTR pszCommand,  
    CmdResponseType eResponse = CmdRespNone,  
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszCommand`  
 送信されるコマンドが含まれている文字列へのポインター。  
  
 *eResponse*  
 FTP サーバーからの応答が予期されているかどうかを判断します。 次のいずれかの値になります。  
  
- **CmdRespNone**応答は発生しません。  
  
- **CmdRespRead**応答が必要です。  
  
 `dwFlags`  
 この関数を制御するフラグが含まれている値。 完全な一覧については、次を参照してください。 [FTPCommand](http://msdn.microsoft.com/library/windows/desktop/aa384133)します。  
  
 `dwContext`  
 コールバックでアプリケーションのコンテキストを識別するために使用されるアプリケーション定義の値が含まれている値へのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [FTPCommand](http://msdn.microsoft.com/library/windows/desktop/aa384133)関数」の説明に従って、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 エラーが発生する場合、MFC は型の例外をスロー[表す](../../mfc/reference/cinternetexception-class.md)します。  
  
##  <a name="a-namecreatedirectorya--cftpconnectioncreatedirectory"></a><a name="createdirectory"></a>CFtpConnection::CreateDirectory  
 接続されたサーバーのディレクトリを作成するには、このメンバー関数を呼び出します。  
  
```  
BOOL CreateDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrDirName`  
 作成するディレクトリの名前を含む文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Windows の関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのには呼び出すことができます。  
  
### <a name="remarks"></a>コメント  
 使用`GetCurrentDirectory`をこのサーバーへの接続の現在の作業ディレクトリを判断します。 リモート システムが接続されていることをルート ディレクトリとは限りません。  
  
 `pstrDirName`パラメーターには、いずれかを指定できます、部分的にまたは現在のディレクトリに対して相対的な完全修飾ファイル名。 円記号 (\\) またはいずれかの名前のディレクトリ区切り記号としてスラッシュ (/) を使用できます。 `CreateDirectory`使用されるように、適切な文字にディレクトリ名の区切り記号を変換します。  
  
##  <a name="a-namegetcurrentdirectorya--cftpconnectiongetcurrentdirectory"></a><a name="getcurrentdirectory"></a>CFtpConnection::GetCurrentDirectory  
 このメンバー関数を呼び出して、現在のディレクトリの名前を取得します。  
  
```  
BOOL GetCurrentDirectory(CString& strDirName) const;  
  
BOOL GetCurrentDirectory(
    LPTSTR pstrDirName,  
    LPDWORD lpdwLen) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `strDirName`  
 ディレクトリの名前を受け取る文字列への参照。  
  
 `pstrDirName`  
 ディレクトリの名前を受け取る文字列へのポインター。  
  
 `lpdwLen`  
 次の情報を含む DWORD へのポインター。  
  
|||  
|-|-|  
|エントリ|によって参照されるバッファーのサイズ`pstrDirName`します。|  
|返された場合|格納されている文字数`pstrDirName`します。 メンバー関数が失敗したかどうか、および、ERROR_INSUFFICIENT_BUFFER が返されます`lpdwLen`文字列を取得するためにアプリケーションを割り当てる必要がありますバイト数が含まれています。|  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのには呼び出すことができます。  
  
### <a name="remarks"></a>コメント  
 URL として代わりに、ディレクトリ名を取得する[GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl)します。  
  
 パラメーター`pstrDirName`または`strDirName`または完全な現在のディレクトリに対して相対的いずれかの部分修飾ファイル名であることができます。 円記号 (\\) またはいずれかの名前のディレクトリ区切り記号としてスラッシュ (/) を使用できます。 `GetCurrentDirectory`使用されるように、適切な文字にディレクトリ名の区切り記号を変換します。  
  
##  <a name="a-namegetcurrentdirectoryasurla--cftpconnectiongetcurrentdirectoryasurl"></a><a name="getcurrentdirectoryasurl"></a>CFtpConnection::GetCurrentDirectoryAsURL  
 現在のディレクトリの名前を URL としてを取得するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetCurrentDirectoryAsURL(CString& strDirName) const;  
  
BOOL GetCurrentDirectoryAsURL(
    LPTSTR pstrName,  
    LPDWORD lpdwLen) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `strDirName`  
 ディレクトリの名前を受け取る文字列への参照。  
  
 `pstrDirName`  
 ディレクトリの名前を受け取る文字列へのポインター。  
  
 `lpdwLen`  
 次の情報を含む DWORD へのポインター。  
  
|||  
|-|-|  
|エントリ|によって参照されるバッファーのサイズ`pstrDirName`します。|  
|返された場合|格納されている文字数`pstrDirName`します。 メンバー関数が失敗したかどうか、および、ERROR_INSUFFICIENT_BUFFER が返されます`lpdwLen`文字列を取得するためにアプリケーションを割り当てる必要がありますバイト数が含まれています。|  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのには呼び出すことができます。  
  
### <a name="remarks"></a>コメント  
 `GetCurrentDirectoryAsURL`同じように動作[GetCurrentDirectory](#getcurrentdirectory)  
  
 パラメーター`strDirName`または完全な現在のディレクトリに対して相対的いずれかの部分修飾ファイル名であることができます。 円記号 (\\) またはいずれかの名前のディレクトリ区切り記号としてスラッシュ (/) を使用できます。 `GetCurrentDirectoryAsURL`使用されるように、適切な文字にディレクトリ名の区切り記号を変換します。  
  
##  <a name="a-namegetfilea--cftpconnectiongetfile"></a><a name="getfile"></a>CFtpConnection::GetFile  
 このメンバー関数を呼び出して、FTP サーバーからファイルを取得して、ローカル コンピューターに保存しています。  
  
```  
BOOL GetFile(
    LPCTSTR pstrRemoteFile,  
    LPCTSTR pstrLocalFile,  
    BOOL bFailIfExists = TRUE,  
    DWORD dwAttributes = FILE_ATTRIBUTE_NORMAL,  
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrRemoteFile`  
 FTP サーバーから取得するファイルの名前を表す null で終わる文字列へのポインター。  
  
 `pstrLocalFile`  
 ローカル システムで作成するファイルの名前を表す null で終わる文字列へのポインター。  
  
 *bFailIfExists*  
 ファイル名が既存のファイルで使用できます既にかどうかを示します。 ローカル ファイルの名前が既に存在するかどうかは、このパラメーターが**TRUE**、`GetFile`は失敗します。 それ以外の場合、`GetFile`ファイルの既存のコピーが消去されます。  
  
 `dwAttributes`  
 ファイルの属性を示します。 次の FILE_ATTRIBUTE_ * フラグの任意の組み合わせを入力できます。  
  
-   FILE_ATTRIBUTE_ARCHIVE ファイルは、アーカイブ ファイルです。 アプリケーションでは、この属性を使用して、ファイルをバックアップまたは削除をマークします。  
  
-   FILE_ATTRIBUTE_COMPRESSED ファイルまたはディレクトリが圧縮されます。 ファイルの場合は、圧縮は、すべてのファイルにデータが圧縮されているを意味します。 ディレクトリの場合は、圧縮は、新しく作成されたファイルとサブディレクトリの既定値です。  
  
-   FILE_ATTRIBUTE_DIRECTORY ファイルは、ディレクトリです。  
  
-   FILE_ATTRIBUTE_NORMAL ファイルには、他の属性セットがありません。 この属性は、単独で使用される場合にのみ有効です。 その他のすべてのファイル属性は、FILE_ATTRIBUTE_NORMAL をオーバーライドします。  
  
-   FILE_ATTRIBUTE_HIDDEN ファイルは表示されません。 通常のディレクトリ一覧に含めるには  
  
-   FILE_ATTRIBUTE_READONLY ファイルは読み取り専用です。 アプリケーションは、ファイルの読み取りことはできませんからの書き込みしたり削除できます。  
  
-   FILE_ATTRIBUTE_SYSTEM ファイルの一部であるか、オペレーティング システムによって排他的に使用されます。  
  
-   一時的な記憶域 FILE_ATTRIBUTE_TEMPORARY ファイルを使用しています。 アプリケーションは、絶対に必要な場合にのみ、ファイルに書き込む必要があります。 ファイルのデータの大部分は、ファイルがすぐに削除されるため、メディアに書き込まれずに、メモリに残ります。  
  
 `dwFlags`  
 転送が発生する条件を指定します。 このパラメーターには、いずれかを指定できます、`dwFlags`値」に記載[FtpGetFile](http://msdn.microsoft.com/library/windows/desktop/aa384157)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `dwContext`  
 ファイルを取得するためのコンテキストの識別子です。 参照してください**解説**の詳細については`dwContext`です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのには呼び出すことができます。  
  
### <a name="remarks"></a>コメント  
 `GetFile`FTP サーバーからファイルの読み取りをローカルに格納することに関連するオーバーヘッドのすべてを処理する高レベルのルーチンです。 ファイル データを取得するのみまたはファイル転送を閉じる制御を必要とするアプリケーションを使用する必要があります`OpenFile`と[細かい](../../mfc/reference/cinternetfile-class.md#read)代わりにします。  
  
 場合`dwFlags`FILE_TRANSFER_TYPE_ASCII、ファイル データの変換も変換コントロール、および Windows の対応する文字の書式を設定します。 既定の転送は、場所、ファイルは同じ形式でサーバーに格納されているバイナリ モードは、です。  
  
 両方とも`pstrRemoteFile`と`pstrLocalFile`または完全な現在のディレクトリに対して相対的いずれかの部分修飾ファイル名であることができます。 円記号 (\\) またはいずれかの名前のディレクトリ区切り記号としてスラッシュ (/) を使用できます。 `GetFile`使用されるように、適切な文字にディレクトリ名の区切り記号を変換します。  
  
 `dwContext` の既定値をオーバーライドして、コンテキスト識別子を独自の値に設定します。 コンテキスト識別子がこの特定の操作に関連付けられている、`CFtpConnection`によって作成されたオブジェクトの[CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトです。 値が返される[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)識別は操作の状態をします。 記事を参照して[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)詳細については、コンテキスト識別子。  
  
##  <a name="a-nameopenfilea--cftpconnectionopenfile"></a><a name="openfile"></a>CFtpConnection::OpenFile  
 読み取りまたは書き込み用に FTP サーバー上にあるファイルを開くには、このメンバー関数を呼び出します。  
  
```  
CInternetFile* OpenFile(
    LPCTSTR pstrFileName,  
    DWORD dwAccess = GENERIC_READ,  
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrFileName`  
 開かれるファイルの名前を含む文字列へのポインター。  
  
 *dwAccess*  
 ファイルのアクセス方法を決定します。 GENERIC_READ または GENERIC_WRITE のいずれかができます。  
  
 `dwFlags`  
 その後の転送が発生する状況を指定します。 次の FTP_TRANSFER_ * 定数のいずれかになります。  
  
-   FTP_TRANSFER_TYPE_ASCII ファイルは、FTP ASCII (型 A) の転送方法を使用して転送されます。 変換コントロールと書式設定情報を対応するローカルです。  
  
-   FTP_TRANSFER_TYPE_BINARY ファイルは、(タイプ I) FTP's イメージの転送方法を使用してデータを転送します。 これとまったく同じデータを転送するファイルは、変更せずに存在します。 これは、既定の転送方法です。  
  
 `dwContext`  
 ファイルを開くためのコンテキストの識別子です。 参照してください**解説**の詳細については`dwContext`です。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CInternetFile](../../mfc/reference/cinternetfile-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 `OpenFile`次のような状況で使用する必要があります。  
  
-   アプリケーション データを持っているデータがローカル ファイルでないものを送信し、FTP サーバー上のファイルとして作成する必要があります。 1 回`OpenFile`、アプリケーションはファイルを開き[CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write) FTP ファイル データをサーバーに送信します。  
  
-   アプリケーションは、サーバーからファイルを取得し、アプリケーション制御のメモリ、ディスクに書き込む代わりに配置する必要があります。 アプリケーションを使用して[細かい](../../mfc/reference/cinternetfile-class.md#read)を使用した後`OpenFile`ファイルを開きます。  
  
-   アプリケーションでは、きめ細かいファイル転送の制御レベルが必要です。 たとえば、アプリケーションが、進行状況を表示できます。 コントロールは、ファイルのダウンロード中にファイル転送の状態の進行状況を示します。  
  
 呼び出した後`OpenFile`通話まで**CInternetConnection::Close**、アプリケーションを呼び出して、のみ[細かい](../../mfc/reference/cinternetfile-class.md#read)、 [CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write)、 **CInternetConnection::Close**、または[CFtpFileFind::FindFile](../../mfc/reference/cftpfilefind-class.md#findfile)します。 同じ FTP セッションの他の FTP 関数の呼び出しは失敗し、エラー コードを FTP_ETRANSFER_IN_PROGRESS に設定します。  
  
 `pstrFileName`パラメーターは、いずれか、部分的に修飾ファイル名、現在のディレクトリに相対パスまたは完全修飾を指定できます。 円記号 (\\) またはいずれかの名前のディレクトリ区切り記号としてスラッシュ (/) を使用できます。 `OpenFile`適切な文字にディレクトリ名の区切り記号を使用する前に変換します。  
  
 `dwContext` の既定値をオーバーライドして、コンテキスト識別子を独自の値に設定します。 コンテキスト識別子がこの特定の操作に関連付けられている、`CFtpConnection`によって作成されたオブジェクトの[CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトです。 値が返される[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)識別は操作の状態をします。 記事を参照して[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)詳細については、コンテキスト識別子。  
  
##  <a name="a-nameputfilea--cftpconnectionputfile"></a><a name="putfile"></a>CFtpConnection::PutFile  
 FTP サーバー上のファイルを保存するには、このメンバー関数を呼び出します。  
  
```  
BOOL PutFile(
    LPCTSTR pstrLocalFile,  
    LPCTSTR pstrRemoteFile,  
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrLocalFile`  
 ローカル システムから送信するファイルの名前を含む文字列へのポインター。  
  
 `pstrRemoteFile`  
 FTP サーバー上に作成するファイルの名前を含む文字列へのポインター。  
  
 `dwFlags`  
 ファイルの転送が発生する条件を指定します。 示す FTP_TRANSFER_ * 定数のいずれかを指定できる[OpenFile](#openfile)します。  
  
 `dwContext`  
 ファイルを配置するためのコンテキストの識別子です。 参照してください**解説**の詳細については`dwContext`です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのには呼び出すことができます。  
  
### <a name="remarks"></a>コメント  
 `PutFile`すべての FTP サーバー上のファイルを格納することに関連する操作を処理する高度なルーチン。 のみにデータを送信するか、ファイル転送に近い制御を必要とするアプリケーションを使用する必要があります[OpenFile](#openfile)と[CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write)します。  
  
 `dwContext` の既定値をオーバーライドして、コンテキスト識別子を独自の値に設定します。 コンテキスト識別子がこの特定の操作に関連付けられている、`CFtpConnection`によって作成されたオブジェクトの[CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトです。 値が返される[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)識別は操作の状態をします。 記事を参照して[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)詳細については、コンテキスト識別子。  
  
##  <a name="a-nameremovea--cftpconnectionremove"></a><a name="remove"></a>CFtpConnection::Remove  
 接続先のサーバーから、指定したファイルを削除するには、このメンバー関数を呼び出します。  
  
```  
BOOL Remove(LPCTSTR pstrFileName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrFileName`  
 削除するファイル名を含む文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのには呼び出すことができます。  
  
### <a name="remarks"></a>コメント  
 `pstrFileName`パラメーターは、いずれか、部分的に修飾ファイル名、現在のディレクトリに相対パスまたは完全修飾を指定できます。 円記号 (\\) またはいずれかの名前のディレクトリ区切り記号としてスラッシュ (/) を使用できます。 **削除**関数が使用されるように、適切な文字にディレクトリ名の区切り記号を変換します。  
  
##  <a name="a-nameremovedirectorya--cftpconnectionremovedirectory"></a><a name="removedirectory"></a>CFtpConnection::RemoveDirectory  
 接続先のサーバーから、指定したディレクトリを削除するには、このメンバー関数を呼び出します。  
  
```  
BOOL RemoveDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrDirName`  
 削除するディレクトリを含む文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのには呼び出すことができます。  
  
### <a name="remarks"></a>コメント  
 使用[GetCurrentDirectory](#getcurrentdirectory)をサーバーの現在の作業ディレクトリを判断します。 リモート システムが接続されていることをルート ディレクトリとは限りません。  
  
 `pstrDirName`パラメーターは、現在のディレクトリに対して相対的 filename が部分的または完全に修飾を指定できます。 円記号 (\\) またはいずれかの名前のディレクトリ区切り記号としてスラッシュ (/) を使用できます。 `RemoveDirectory`使用されるように、適切な文字にディレクトリ名の区切り記号を変換します。  
  
##  <a name="a-namerenamea--cftpconnectionrename"></a><a name="rename"></a>CFtpConnection::Rename  
 接続されているサーバー上の指定のファイルの名前を変更するには、このメンバー関数を呼び出します。  
  
```  
BOOL Rename(
    LPCTSTR pstrExisting,  
    LPCTSTR pstrNew);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrExisting`  
 名前を変更するファイルの現在の名前を含む文字列へのポインター。  
  
 `pstrNew`  
 ファイルの新しい名前を含む文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのには呼び出すことができます。  
  
### <a name="remarks"></a>コメント  
 `pstrExisting`と`pstrNew`パラメーターは、いずれか、部分的に修飾ファイル名、現在のディレクトリに相対パスまたは完全修飾を指定できます。 円記号 (\\) またはいずれかの名前のディレクトリ区切り記号としてスラッシュ (/) を使用できます。 **名前を変更**使用されるように、ディレクトリ名の区切り記号を適切な文字に変換します。  
  
##  <a name="a-namesetcurrentdirectorya--cftpconnectionsetcurrentdirectory"></a><a name="setcurrentdirectory"></a>CFtpConnection::SetCurrentDirectory  
 FTP サーバー上の別のディレクトリに変更するには、このメンバー関数を呼び出します。  
  
```  
BOOL SetCurrentDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrDirName`  
 ディレクトリの名前を含む文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのには呼び出すことができます。  
  
### <a name="remarks"></a>コメント  
 `pstrDirName`パラメーターは、現在のディレクトリに対して相対的 filename が部分的または完全に修飾を指定できます。 円記号 (\\) またはいずれかの名前のディレクトリ区切り記号としてスラッシュ (/) を使用できます。 `SetCurrentDirectory`使用されるように、適切な文字にディレクトリ名の区切り記号を変換します。  
  
 使用[GetCurrentDirectory](#getcurrentdirectory)を FTP サーバーの現在の作業ディレクトリを判断します。 リモート システムが接続されていることをルート ディレクトリとは限りません。  
  
## <a name="see-also"></a>関連項目  
 [関数のクラス](../../mfc/reference/cinternetconnection-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [関数のクラス](../../mfc/reference/cinternetconnection-class.md)   
 [CInternetSession クラス](../../mfc/reference/cinternetsession-class.md)

