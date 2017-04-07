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
- CFtpFileFind
- AFXINET/CFtpFileFind
- AFXINET/CFtpFileFind::CFtpFileFind
- AFXINET/CFtpFileFind::FindFile
- AFXINET/CFtpFileFind::FindNextFile
- AFXINET/CFtpFileFind::GetFileURL
dev_langs:
- C++
helpviewer_keywords:
- CFtpFileFind class
- file searches [C++]
ms.assetid: 9667cf01-657f-4b11-b9db-f11e5a7b4e4c
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
ms.openlocfilehash: 6e84282cc2f22e813ea44318d497c7e32e3280d8
ms.lasthandoff: 02/24/2017

---
# <a name="cftpfilefind-class"></a>関数のクラス
FTP サーバーのインターネット ファイル検索を支援します。  
  
## <a name="syntax"></a>構文  
  
```  
class CFtpFileFind : public CFileFind  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CFtpFileFind::CFtpFileFind](#cftpfilefind)|`CFtpFileFind` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFtpFileFind::FindFile](#findfile)|FTP サーバー上のファイルを検索します。|  
|[CFtpFileFind::FindNextFile](#findnextfile)|以前の呼び出しからファイル検索を続行[FindFile](#findfile)します。|  
|[CFtpFileFind::GetFileURL](#getfileurl)|検索したファイルのパスを含む URL を取得します。|  
  
## <a name="remarks"></a>コメント  
 `CFtpFileFind`検索を開始し、ファイルを検索し、URL またはファイルの内容を示すその他の情報を返すメンバー関数が含まれます。  
  
 インターネットとローカル ファイルの検索を含めるために設計されて他の MFC クラス[関数](../../mfc/reference/cgopherfilefind-class.md)と[CFileFind](../../mfc/reference/cfilefind-class.md)します。 と共に`CFtpFileFind`、これらのクラスが、クライアント、サーバーに関係なく、特定のファイルを検索するには、プロトコルまたはファイルの種類 (ローカル コンピューターまたはリモート サーバー) にシームレスなメカニズムを提供します。 HTTP は検索のために必要なファイルを直接操作をサポートしていないために、HTTP サーバーで検索するための MFC クラスがないことに注意してください。  
  
 使用する方法の詳細についての`CFtpFileFind`し、その他の WinInet クラスは、記事を参照して[WinInet を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)します。  
  
## <a name="example"></a>例  
 次のコードでは、FTP サーバーの現在のディレクトリ内のすべてのファイルを列挙する方法を示します。  
  
 [!code-cpp[NVC_MFCWinInet&#8;](../../mfc/codesnippet/cpp/cftpfilefind-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CFtpFileFind`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxinet.h  
  
##  <a name="cftpfilefind"></a>CFtpFileFind::CFtpFileFind  
 このメンバー関数が作成すると呼ばれる、`CFtpFileFind`オブジェクトです。  
  
```  
explicit CFtpFileFind(
    CFtpConnection* pConnection,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `pConnection`  
 ポインター、`CFtpConnection`オブジェクトです。 FTP 接続を取得するには、呼び出しを[CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)します。  
  
 `dwContext`  
 コンテキスト識別子、`CFtpFileFind`オブジェクトです。 参照してください**解説**の詳細については、このパラメーターにします。  
  
### <a name="remarks"></a>コメント  
 既定値`dwContext`MFC から送信される、`CFtpFileFind`オブジェクトから、 [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトの作成、`CFtpFileFind`オブジェクトです。 コンテキスト識別子を独自の値に設定する既定値をオーバーライドできます。 コンテキスト識別子が返される[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)特定ために使用するオブジェクトの状態をします。 記事を参照して[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)詳細については、コンテキスト識別子。  
  
### <a name="example"></a>例  
  このトピックの「クラスの概要の例を参照してください。  
  
##  <a name="findfile"></a>CFtpFileFind::FindFile  
 FTP ファイルを検索するには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,  
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrName`  
 検索するファイルの名前を含む文字列へのポインター。 場合**NULL**呼び出しは、ワイルドカード検索 (*) を実行します。  
  
 `dwFlags`  
 このセッションを処理する方法を示すフラグ。 これらのフラグは、ビットごとの OR 演算子 (|) を組み合わせるし、次に示します。  
  
-   INTERNET_FLAG_RELOAD は、ローカルにキャッシュされている場合でも、通信回線からデータを取得します。 これは、既定のフラグです。  
  
-   ローカルまたはすべてのゲートウェイのいずれか、データをキャッシュしません INTERNET_FLAG_DONT_CACHE しないでください。  
  
-   INTERNET_FLAG_RAW_DATA が生データを返す既定値を上書き ( [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) FTP の構造体)。  
  
-   Secure Sockets Layer や率とネットワーク上のトランザクションの INTERNET_FLAG_SECURE をセキュリティで保護 このフラグは、HTTP の要求のみに適用されます。  
  
-   INTERNET_FLAG_EXISTING_CONNECT 可能な場合は、新しいサーバーに既存の接続を再利用**FindFile**要求ごとに新しいセッションを作成する代わりに要求します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 拡張エラー情報を取得するには、Win32 関数を呼び出して[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)します。  
  
### <a name="remarks"></a>コメント  
 呼び出した後**FindFile** FTP の最初のファイルを取得するを呼び出すことができます[FindNextFile](#findnextfile)を後続の FTP のファイルを取得します。  
  
### <a name="example"></a>例  
  このトピックで前述の例を参照してください。  
  
##  <a name="findnextfile"></a>CFtpFileFind::FindNextFile  
 呼び出しで開始されたファイルの検索を続行するには、このメンバー関数を呼び出す、 [FindFile](#findfile)メンバー関数。  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>戻り値  
 多くのファイルがある場合は&0; 以外。見つかったファイルがディレクトリに最後の&1; つである場合、またはエラーが発生した場合は&0; します。 拡張エラー情報を取得するには、Win32 関数を呼び出して[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)します。 見つかったファイルがディレクトリに最後のファイルまたは一致するファイルが見つからないことができます、 `GetLastError` ERROR_NO_MORE_FILES を返します。  
  
### <a name="remarks"></a>コメント  
 属性関数を呼び出す前に少なくとも&1; 回、この関数を呼び出す必要があります (を参照してください[呼び出しておく](../../mfc/reference/cfilefind-class.md#findnextfile))。  
  
 `FindNextFile`Win32 関数をラップ[FindNextFile](http://msdn.microsoft.com/library/windows/desktop/aa364428)します。  
  
### <a name="example"></a>例  
  前述の例を参照してください。  
  
##  <a name="getfileurl"></a>CFtpFileFind::GetFileURL  
 指定されたファイルの URL を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ファイル名と Universal Resource Locator (URL) のパス。  
  
### <a name="remarks"></a>コメント  
 `GetFileURL`メンバー関数のような[CFileFind::GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath)形式で URL が返される点が、`ftp://moose/dir/file.txt`です。  
  
## <a name="see-also"></a>関連項目  
 [CFileFind クラス](../../mfc/reference/cfilefind-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [関数のクラス](../../mfc/reference/cgopherfilefind-class.md)   
 [CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile クラス](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile クラス](../../mfc/reference/chttpfile-class.md)

