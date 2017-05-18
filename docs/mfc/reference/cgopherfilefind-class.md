---
title: "クラスの関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGopherFileFind
- AFXINET/CGopherFileFind
- AFXINET/CGopherFileFind::CGopherFileFind
- AFXINET/CGopherFileFind::FindFile
- AFXINET/CGopherFileFind::FindNextFile
- AFXINET/CGopherFileFind::GetCreationTime
- AFXINET/CGopherFileFind::GetLastAccessTime
- AFXINET/CGopherFileFind::GetLastWriteTime
- AFXINET/CGopherFileFind::GetLength
- AFXINET/CGopherFileFind::GetLocator
- AFXINET/CGopherFileFind::GetScreenName
- AFXINET/CGopherFileFind::IsDots
dev_langs:
- C++
helpviewer_keywords:
- CGopherFileFind class
- file searches [C++]
ms.assetid: 8465a979-6323-496d-ab4b-e81383fb999d
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 93f30e83369ad1bff7222f26d0782eed11e73f66
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cgopherfilefind-class"></a>関数のクラス
gopher サーバーのインターネット ファイル検索を支援します。  
  
> [!NOTE]
>  クラスは、 `CGopherConnection`、 `CGopherFile`、 `CGopherFileFind`、`CGopherLocator`し、Windows XP のプラットフォームで機能しませんが、以前のプラットフォームで動作し続けますので、そのメンバーは廃止されました。  
  
## <a name="syntax"></a>構文  
  
```  
class CGopherFileFind : public CFileFind  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CGopherFileFind::CGopherFileFind](#cgopherfilefind)|`CGopherFileFind` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CGopherFileFind::FindFile](#findfile)|Gopher サーバー上のファイルを検索します。|  
|[CGopherFileFind::FindNextFile](#findnextfile)|以前の呼び出しからファイル検索を続行[FindFile](#findfile)します。|  
|[CGopherFileFind::GetCreationTime](#getcreationtime)|指定したファイルが作成された日時を取得します。|  
|[CGopherFileFind::GetLastAccessTime](#getlastaccesstime)|指定したファイルの最終アクセス時刻を取得します。|  
|[CGopherFileFind::GetLastWriteTime](#getlastwritetime)|指定したファイルに最後に書き込んだ時間を取得します。|  
|[CGopherFileFind::GetLength](#getlength)|(バイト単位) を検索したファイルの長さを取得します。|  
|[なった](#getlocator)|取得、`CGopherLocator`オブジェクトです。|  
|[CGopherFileFind::GetScreenName](#getscreenname)|Gopher 画面の名前を取得します。|  
|[CGopherFileFind::IsDots](#isdots)|ファイル反復処理中に現在のディレクトリとその親ディレクトリ マーカーをテストします。|  
  
## <a name="remarks"></a>コメント  
 `CGopherFileFind`検索を開始し、ファイルを検索し、ファイルの URL を返すメンバー関数が含まれます。  
  
 インターネットとローカル ファイルの検索を含めるために設計されて他の MFC クラス[関数](../../mfc/reference/cftpfilefind-class.md)と[CFileFind](../../mfc/reference/cfilefind-class.md)します。 と共に`CGopherFileFind`、これらのクラスは、サーバー プロトコル、ファイルの種類または場所 (ローカル コンピューターまたはリモート サーバーのいずれかです) に関係なく、特定のファイルを検索するユーザーのシームレスなメカニズムを提供。HTTP は検索に必要なファイルを直接操作をサポートしていないために、HTTP サーバーで検索するための MFC クラスがないことに注意してください。  
  
> [!NOTE]
> `CGopherFileFind`その基本クラスの次のメンバー関数をサポートしていません[CFileFind](../../mfc/reference/cfilefind-class.md):  
  
- [GetRoot](../../mfc/reference/cfilefind-class.md#getroot)  
  
- [GetFileName](../../mfc/reference/cfilefind-class.md#getfilename)  
  
- [まで含めた](../../mfc/reference/cfilefind-class.md#getfilepath)  
  
- [GetFileTitle](../../mfc/reference/cfilefind-class.md#getfiletitle)  
  
- [GetFileURL](../../mfc/reference/cfilefind-class.md#getfileurl)  
  
 さらを使用すると`CGopherFileFind`、`CFileFind`メンバー関数[IsDots](../../mfc/reference/cfilefind-class.md#isdots)は常に**FALSE**します。  
  
 使用する方法の詳細についての`CGopherFileFind`し、その他の WinInet クラスは、記事を参照して[WinInet を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CGopherFileFind`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxinet.h  
  
##  <a name="cgopherfilefind"></a>CGopherFileFind::CGopherFileFind  
 このメンバー関数が作成すると呼ばれる、`CGopherFileFind`オブジェクトです。  
  
```  
explicit CGopherFileFind(
    CGopherConnection* pConnection,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `pConnection`  
 ポインター、[関数](../../mfc/reference/cgopherconnection-class.md)オブジェクトです。  
  
 `dwContext`  
 操作のコンテキストの識別子です。 参照してください**解説**の詳細については`dwContext`です。  
  
### <a name="remarks"></a>コメント  
 既定値`dwContext`MFC から送信される、`CGopherFileFind`オブジェクトから、 [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトの作成、`CGopherFileFind`オブジェクトです。 構築する場合、`CGopherFileFind`オブジェクトのコンテキスト識別子を独自の値に設定する既定値をオーバーライドすることができます。 コンテキスト識別子が返される[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)特定ために使用するオブジェクトの状態をします。 記事を参照して[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)詳細については、コンテキスト識別子。  
  
##  <a name="findfile"></a>CGopherFileFind::FindFile  
 Gopher ファイルを検索するには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL FindFile(
    CGopherLocator& refLocator,  
    LPCTSTR pstrString,  
    DWORD dwFlags = INTERNET_FLAG_RELOAD);

 
virtual BOOL FindFile(
    LPCTSTR pstrString,  
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```  
  
### <a name="parameters"></a>パラメーター  
 `refLocator`  
 参照、[関数](../../mfc/reference/cgopherlocator-class.md)オブジェクトです。  
  
 *pstrString*  
 ファイル名を含む文字列へのポインター。  
  
 `dwFlags`  
 このセッションを処理する方法を示すフラグ。 有効なフラグは次のとおりです。  
  
-   INTERNET_FLAG_RELOAD は、ローカルにキャッシュされている場合でも、リモート サーバーからデータを取得します。  
  
-   ローカルまたはすべてのゲートウェイのいずれか、データをキャッシュしません INTERNET_FLAG_DONT_CACHE しないでください。  
  
-   Secure Sockets Layer または率とネットワーク上のセキュリティで保護されたトランザクションの INTERNET_FLAG_SECURE 要求 このフラグは、HTTP の要求のみに適用されます。  
  
-   INTERNET_FLAG_USE_EXISTING 可能な場合は、新しいサーバーに既存の接続を再利用**FindFile**要求ごとに新しいセッションを作成する代わりに要求します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 拡張エラー情報を取得するには、Win32 関数を呼び出して[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)します。  
  
### <a name="remarks"></a>コメント  
 呼び出した後**FindFile** gopher の最初のオブジェクトを取得するを呼び出すことができます[FindNextFile](#findnextfile)後続 gopher ファイルを取得します。  
  
##  <a name="findnextfile"></a>CGopherFileFind::FindNextFile  
 呼び出しで開始されたファイルの検索を続行するには、このメンバー関数を呼び出す[CGopherFileFind::FindFile](#findfile)します。  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>戻り値  
 多くのファイルがある場合は&0; 以外。見つかったファイルがディレクトリに最後の&1; つである場合、またはエラーが発生した場合は&0; します。 拡張エラー情報を取得するには、Win32 関数を呼び出して[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)します。 見つかったファイルがディレクトリに最後のファイルまたは一致するファイルが見つからないことができます、 `GetLastError` ERROR_NO_MORE_FILES を返します。  
  
##  <a name="getcreationtime"></a>CGopherFileFind::GetCreationTime  
 現在のファイルの作成時間を取得します。  
  
```  
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetCreationTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pTimeStamp`  
 ポインター、 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)ファイルが作成された日時を保持します。  
  
 `refTime`  
 参照、 [CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外。それ以外の場合は 0 を返します。 `GetCreationTime`場合にのみ、0 を返します[FindNextFile](#findnextfile)は決してこので呼び出されて`CGopherFileFind`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも&1; 回`GetCreationTime`します。  
  
> [!NOTE]
>  すべてのファイル システムでは、同じセマンティクスを使用して、この関数によって返される、タイムスタンプを実装します。 この関数は、基になるファイル システムまたはサーバーがサポートしない場合、時間属性を維持するその他のタイムスタンプ関数によって返される同じ値を返す可能性があります。 参照してください、 [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造での時刻の書式に関する情報。 一部のオペレーティング システムは、ファイルが存在するコンピューターにゾーンのローカル時刻では返される時刻です。 Win32 を参照してください[詳細](http://msdn.microsoft.com/library/windows/desktop/ms724277)API の詳細。  
  
##  <a name="getlastaccesstime"></a>CGopherFileFind::GetLastAccessTime  
 指定したファイルの最終アクセス時刻を取得します。  
  
```  
virtual BOOL GetLastAccessTime(CTime& refTime) const;  
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `refTime`  
 参照、 [CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクトです。  
  
 `pTimeStamp`  
 ポインター、 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)ファイルの最終アクセス時刻が格納されています。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外。それ以外の場合は 0 を返します。 `GetLastAccessTime`場合にのみ、0 を返します[FindNextFile](#findnextfile)は決してこので呼び出されて`CGopherFileFind`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも&1; 回`GetLastAccessTime`します。  
  
> [!NOTE]
>  すべてのファイル システムでは、同じセマンティクスを使用して、この関数によって返される、タイムスタンプを実装します。 この関数は、基になるファイル システムまたはサーバーがサポートしない場合、時間属性を維持するその他のタイムスタンプ関数によって返される同じ値を返す可能性があります。 参照してください、 [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造での時刻の書式に関する情報。 一部のオペレーティング システムは、ファイルが存在するコンピューターにゾーンのローカル時刻では返される時刻です。 Win32 を参照してください[詳細](http://msdn.microsoft.com/library/windows/desktop/ms724277)API の詳細。  
  
##  <a name="getlastwritetime"></a>CGopherFileFind::GetLastWriteTime  
 ファイルが変更された最終時刻を取得します。  
  
```  
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetLastWriteTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pTimeStamp`  
 ポインター、 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)ファイルに最後に書き込んだ日時を保持します。  
  
 `refTime`  
 参照、 [CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外。それ以外の場合は 0 を返します。 `GetLastWriteTime`場合にのみ、0 を返します[FindNextFile](#findnextfile)は決してこので呼び出されて`CGopherFileFind`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも&1; 回`GetLastWriteTime`します。  
  
> [!NOTE]
>  すべてのファイル システムでは、同じセマンティクスを使用して、この関数によって返される、タイムスタンプを実装します。 この関数は、基になるファイル システムまたはサーバーがサポートしない場合、時間属性を維持するその他のタイムスタンプ関数によって返される同じ値を返す可能性があります。 参照してください、 [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造での時刻の書式に関する情報。 一部のオペレーティング システムは、ファイルが存在するコンピューターにゾーンのローカル時刻では返される時刻です。 Win32 を参照してください[詳細](http://msdn.microsoft.com/library/windows/desktop/ms724277)API の詳細。  
  
##  <a name="getlength"></a>CGopherFileFind::GetLength  
 検索したファイルのバイト単位の長さを取得するには、このメンバー関数を呼び出します。  
  
```  
virtual ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>戻り値  
 見つかったファイルの長さ、(バイト単位)。  
  
### <a name="remarks"></a>コメント  
 `GetLength`Win32 構造を使用して[WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)バイト単位でのファイル サイズの値を取得します。  
  
> [!NOTE]
>  MFC 7.0 以降`GetLength`64 ビット整数型をサポートしています。 ライブラリのこのより新しいバージョンで構築された既存のコードは、切り捨ての警告があります。  
  
### <a name="example"></a>例  
  例を参照してください[結び付けてその中](../../mfc/reference/cfile-class.md#getlength)(基本クラスの実装)。  
  
##  <a name="getlocator"></a>なった  
 取得するには、このメンバー関数を呼び出す、[関数](../../mfc/reference/cgopherlocator-class.md)オブジェクトを[FindFile](#findfile)を使用して、gopher ファイルを検索します。  
  
```  
CGopherLocator GetLocator() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `CGopherLocator` オブジェクト。  
  
##  <a name="getscreenname"></a>CGopherFileFind::GetScreenName  
 Gopher 画面の名前を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetScreenName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 Gopher 画面の名前。  
  
##  <a name="isdots"></a>CGopherFileFind::IsDots  
 ファイル反復処理中に現在のディレクトリとその親ディレクトリ マーカーをテストします。  
  
```  
virtual BOOL IsDots() const;  
```  
  
### <a name="return-value"></a>戻り値  
 検索したファイルに名前がある場合、0 以外の値"です。"または".."、見つかったファイルが実際にはディレクトリです。 それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも&1; 回`IsDots`します。  
  
## <a name="see-also"></a>関連項目  
 [CFileFind クラス](../../mfc/reference/cfilefind-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [関数のクラス](../../mfc/reference/cftpfilefind-class.md)   
 [CFileFind クラス](../../mfc/reference/cfilefind-class.md)   
 [CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile クラス](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile クラス](../../mfc/reference/chttpfile-class.md)

