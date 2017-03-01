---
title: "CFileFind クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFileFind
dev_langs:
- C++
helpviewer_keywords:
- files [C++], finding
- Internet files [C++], finding
- CFileFind class
- URLs [C++], searching for
- local files
- local files, searching for
ms.assetid: 9990068c-b023-4114-9580-a50182d15240
caps.latest.revision: 22
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
ms.openlocfilehash: d7e6500dfc0ff24f35dd021a54080eb7ba7f1655
ms.lasthandoff: 02/24/2017

---
# <a name="cfilefind-class"></a>CFileFind クラス
ローカル ファイルの検索を実行し、基本クラスは、[関数](../../mfc/reference/cgopherfilefind-class.md)と[関数](../../mfc/reference/cftpfilefind-class.md)、インターネット ファイル検索を実行します。  
  
## <a name="syntax"></a>構文  
  
```  
class CFileFind : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CFileFind::CFileFind](#cfilefind)|`CFileFind` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFileFind::Close](#close)|検索要求を終了します。|  
|[CFileFind::FindFile](#findfile)|指定したファイル名用のディレクトリを検索します。|  
|[呼び出しておく](#findnextfile)|以前の呼び出しからファイル検索を続行[FindFile](#findfile)します。|  
|[CFileFind::GetCreationTime](#getcreationtime)|ファイルが作成された日時を取得します。|  
|[CFileFind::GetFileName](#getfilename)|検索したファイルの拡張子を含む名前を取得します。|  
|[CFileFind::GetFilePath](#getfilepath)|検索したファイルの完全パスを取得します。|  
|[CFileFind::GetFileTitle](#getfiletitle)|検索したファイルのタイトルを取得します。 タイトルでは、拡張機能は含まれません。|  
|[CFileFind::GetFileURL](#getfileurl)|検索したファイルのファイル パスを含む URL を取得します。|  
|[CFileFind::GetLastAccessTime](#getlastaccesstime)|ファイルの最終アクセス時刻を取得します。|  
|[CFileFind::GetLastWriteTime](#getlastwritetime)|ファイルが最後に変更および保存時間を取得します。|  
|[CFileFind::GetLength](#getlength)|(バイト単位) を検索したファイルの長さを取得します。|  
|[CFileFind::GetRoot](#getroot)|検索したファイルのルート ディレクトリを取得します。|  
|[CFileFind::IsArchived](#isarchived)|検索したファイルがアーカイブになっているかどうかを判断します。|  
|[CFileFind::IsCompressed](#iscompressed)|検索したファイルが圧縮されているかを決定します。|  
|[CFileFind::IsDirectory](#isdirectory)|検索したファイルがディレクトリであるかどうかを判断します。|  
|[CFileFind::IsDots](#isdots)|かどうかを検索したファイルの名前、名前"です。"または".."、実際にはディレクトリであることを示します。|  
|[CFileFind::IsHidden](#ishidden)|検索したファイルが非表示を決定します。|  
|[CFileFind::IsNormal](#isnormal)|検索したファイルが正常かどうかを (つまり、属性を持っていないその他の)。|  
|[CFileFind::IsReadOnly](#isreadonly)|検索したファイルが読み取り専用かどうかをします。|  
|[CFileFind::IsSystem](#issystem)|検索したファイルがシステム ファイルであるかどうかを判断します。|  
|[CFileFind::IsTemporary](#istemporary)|検索したファイルが一時的なかどうかを判断します。|  
|[CFileFind::MatchesMask](#matchesmask)|検索するファイルの目的のファイル属性を示します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFileFind::CloseContext](#closecontext)|現在の検索ハンドルで指定されたファイルを閉じます。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CFileFind::m_pTM](#m_ptm)|ポインター、`CAtlTransactionManager`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 `CFileFind`検索を開始し、ファイルを検索し、タイトル、名前、またはファイルのパスを返すメンバー関数が含まれます。 インターネット検索では、メンバー関数は、 [GetFileURL](#getfileurl)ファイルの URL を返します。  
  
 `CFileFind`他の&2; つの MFC クラスの基本クラスは、特定のサーバーの種類を検索するように設計: `CGopherFileFind` gopher サーバー固有の動作と`CFtpFileFind`具体的には FTP サーバーで動作します。 同時に、これら&3; つのクラスは、ローカル コンピューターまたはリモート サーバーのいずれかのサーバー プロトコル、ファイルの種類や場所に関係なくのファイルを検索するクライアントのシームレスなメカニズムを提供します。  
  
 次のコードでは、各ファイルの名前を出力して、現在のディレクトリ内のすべてのファイルを列挙します。  
  
 [!code-cpp[NVC_MFCFiles #&31;](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_1.cpp)]  
  
 このコード例をシンプルにするには、C++ 標準ライブラリを使用して`cout`クラスです。 `cout`への呼び出しに行を置き換えることが`CListBox::AddString`、たとえば、グラフィカル ユーザー インターフェイスを備えたプログラムにします。  
  
 使用する方法の詳細についての`CFileFind`し、その他の WinInet クラスは、記事を参照して[WinInet を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CFileFind`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="a-namecfilefinda--cfilefindcfilefind"></a><a name="cfilefind"></a>CFileFind::CFileFind  
 このメンバー関数が呼び出されます、`CFileFind`オブジェクトを構築します。  
  
```  
CFileFind();  
CFileFind(CAtlTransactionManager* pTM);
```  
  
### <a name="parameters"></a>パラメーター  
 `pTM`  
 CAtlTransactionManager オブジェクトへのポインター。  
  
### <a name="example"></a>例  
  例を参照してください[CFileFind::GetFileName](#getfilename)します。  
  
##  <a name="a-nameclosea--cfilefindclose"></a><a name="close"></a>CFileFind::Close  
 このメンバー関数を呼び出して検索を終了し、コンテキストをリセットし、すべてのリソースを解放します。  
  
```  
void Close();
```  
  
### <a name="remarks"></a>コメント  
 呼び出した後**閉じる**、新しいを作成する必要はありません`CFileFind`呼び出す前にインスタンス[FindFile](#findfile)新しい検索を開始します。  
  
### <a name="example"></a>例  
  例を参照してください[CFileFind::GetFileName](#getfilename)します。  
  
##  <a name="a-nameclosecontexta--cfilefindclosecontext"></a><a name="closecontext"></a>CFileFind::CloseContext  
 現在の検索ハンドルで指定されたファイルを閉じます。  
  
```  
virtual void CloseContext();
```  
  
### <a name="remarks"></a>コメント  
 検索ハンドルの現在の値で指定されたファイルを閉じます。 既定の動作を変更するには、この関数をオーバーライドします。  
  
 呼び出す必要があります、 [FindFile](#findfile)または[FindNextFile](#findnextfile)関数を&1; 回以上する有効な検索ハンドルを取得します。 **FindFile**と`FindNextFile`関数では、検索のハンドルを使用して、指定した名前に一致する名前を持つファイルを検索します。  
  
##  <a name="a-namefindfilea--cfilefindfindfile"></a><a name="findfile"></a>CFileFind::FindFile  
 ファイル検索を開始するには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,  
    DWORD dwUnused = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrName`  
 検索するファイルの名前を含む文字列へのポインター。 渡した場合**NULL**の`pstrName`、 **FindFile**は、ワイルドカード (*.\*) 検索します。  
  
 *dwUnused*  
 予約する**FindFile**派生クラスです。 0 でなければなりません。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 拡張エラー情報を取得するには、Win32 関数を呼び出して[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)します。  
  
### <a name="remarks"></a>コメント  
 呼び出した後**FindFile**ファイル検索を開始する[FindNextFile](#findnextfile)を後続のファイルを取得します。 呼び出す必要があります`FindNextFile`を少なくとも&1; 回を呼び出す前に、次の属性のメンバー関数。  
  
- [GetCreationTime](#getcreationtime)  
  
- [GetFileName](#getfilename)  
  
- [GetFileTitle](#getfiletitle)  
  
- [まで含めた](#getfilepath)  
  
- [GetFileURL](#getfileurl)  
  
- [GetLastAccessTime](#getlastaccesstime)  
  
- [GetLastWriteTime](#getlastwritetime)  
  
- [GetLength](#getlength)  
  
- [GetRoot](#getroot)  
  
- [IsArchived](#isarchived)  
  
- [IsCompressed](#iscompressed)  
  
- [IsDirectory](#isdirectory)  
  
- [IsDots](#isdots)  
  
- [IsHidden](#ishidden)  
  
- [IsNormal](#isnormal)  
  
- [IsReadOnly](#isreadonly)  
  
- [IsSystem](#issystem)  
  
- [IsTemporary](#istemporary)  
  
- [は](#matchesmask)  
  
### <a name="example"></a>例  
  例を参照してください[CFileFind::IsDirectory](#isdirectory)します。  
  
##  <a name="a-namefindnextfilea--cfilefindfindnextfile"></a><a name="findnextfile"></a>呼び出しておく  
 以前の呼び出しからファイル検索を続行するには、このメンバー関数を呼び出す[FindFile](#findfile)します。  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>戻り値  
 多くのファイルがある場合は&0; 以外。見つかったファイルがディレクトリに最後の&1; つである場合、またはエラーが発生した場合は&0; します。 拡張エラー情報を取得するには、Win32 関数を呼び出して[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)します。 見つかったファイルがディレクトリに最後のファイルまたは一致するファイルが見つからないことができます、 `GetLastError` ERROR_NO_MORE_FILES を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります`FindNextFile`を少なくとも&1; 回を呼び出す前に、次の属性のメンバー関数。  
  
- [GetCreationTime](#getcreationtime)  
  
- [GetFileName](#getfilename)  
  
- [GetFileTitle](#getfiletitle)  
  
- [まで含めた](#getfilepath)  
  
- [GetFileURL](#getfileurl)  
  
- [GetLastAccessTime](#getlastaccesstime)  
  
- [GetLastWriteTime](#getlastwritetime)  
  
- [GetLength](#getlength)  
  
- [GetRoot](#getroot)  
  
- [IsArchived](#isarchived)  
  
- [IsCompressed](#iscompressed)  
  
- [IsDirectory](#isdirectory)  
  
- [IsDots](#isdots)  
  
- [IsHidden](#ishidden)  
  
- [IsNormal](#isnormal)  
  
- [IsReadOnly](#isreadonly)  
  
- [IsSystem](#issystem)  
  
- [IsTemporary](#istemporary)  
  
- [は](#matchesmask)  
  
 `FindNextFile`Win32 関数をラップ[FindNextFile](http://msdn.microsoft.com/library/windows/desktop/aa364428)します。  
  
### <a name="example"></a>例  
  例を参照してください[CFileFind::IsDirectory](#isdirectory)します。  
  
##  <a name="a-namegetcreationtimea--cfilefindgetcreationtime"></a><a name="getcreationtime"></a>CFileFind::GetCreationTime  
 指定したファイルが作成された時刻を取得するには、このメンバー関数を呼び出します。  
  
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
 成功した場合は 0 以外。それ以外の場合は 0 を返します。 `GetCreationTime`場合にのみ、0 を返します[FindNextFile](#findnextfile)は決してこので呼び出されて`CFileFind`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも&1; 回`GetCreationTime`します。  
  
> [!NOTE]
>  すべてのファイル システムでは、同じセマンティクスを使用して、この関数によって返される、タイムスタンプを実装します。 この関数は、基になるファイル システムまたはサーバーがサポートしない場合、時間属性を維持するその他のタイム スタンプ関数によって返される同じ値を返すことがあります。 参照してください、 [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造での時刻の書式に関する情報。 返される時刻をいくつかのオペレーティング システムでは、ファイルが存在するコンピューターにゾーンのローカル時刻でです。 Win32 を参照してください[詳細](http://msdn.microsoft.com/library/windows/desktop/ms724277)API の詳細。  
  
### <a name="example"></a>例  
  例を参照してください[CFileFind::GetLength](#getlength)します。  
  
##  <a name="a-namegetfilenamea--cfilefindgetfilename"></a><a name="getfilename"></a>CFileFind::GetFileName  
 このメンバー関数を呼び出して、検索されたファイルの名前を取得します。  
  
```  
virtual CString GetFileName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 最後に見つかったファイルの名前。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile) GetFileName を呼び出す前に少なくとも&1; 回です。  
  
 `GetFileName`3 つの&1; つ`CFileFind`を何らかの形式のファイル名を返すメンバー関数。 次の一覧には、3 つと、その違いについて説明します。  
  
- `GetFileName`拡張子を含むファイル名を返します。 たとえばを呼び出す`GetFileName`ファイルに関するユーザー メッセージを生成する`c:\myhtml\myfile.txt`ファイル名を返します`myfile.txt`します。  
  
- [まで含めた](#getfilepath)ファイルの完全なパスを返します。 たとえばを呼び出す`GetFilePath`ファイルに関するユーザー メッセージを生成する`c:\myhtml\myfile.txt`ファイル パスを返します`c:\myhtml\myfile.txt`します。  
  
- [GetFileTitle](#getfiletitle)ファイル拡張子を除く、ファイル名を返します。 たとえばを呼び出す`GetFileTitle`ファイルに関するユーザー メッセージを生成する`c:\myhtml\myfile.txt`ファイルのタイトルを取得`myfile`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles&#32;](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_2.cpp)]  
  
##  <a name="a-namegetfilepatha--cfilefindgetfilepath"></a><a name="getfilepath"></a>CFileFind::GetFilePath  
 指定されたファイルの完全なパスを取得するには、このメンバー関数を呼び出します。  
  
```  
virtual CString GetFilePath() const;  
```  
  
### <a name="return-value"></a>戻り値  
 指定されたファイルのパス。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも&1; 回`GetFilePath`します。  
  
 `GetFilePath`3 つの&1; つ`CFileFind`を何らかの形式のファイル名を返すメンバー関数。 次の一覧には、3 つと、その違いについて説明します。  
  
- [GetFileName](#getfilename)拡張子を含む、ファイル名を返します。 たとえばを呼び出す`GetFileName`ファイルに関するユーザー メッセージを生成する`c:\myhtml\myfile.txt`ファイル名を返します`myfile.txt`します。  
  
- `GetFilePath`ファイルの完全なパスを返します。 たとえばを呼び出す`GetFilePath`ファイルに関するユーザー メッセージを生成する`c:\myhtml\myfile.txt`ファイル パスを返します`c:\myhtml\myfile.txt`します。  
  
- [GetFileTitle](#getfiletitle)ファイル拡張子を除く、ファイル名を返します。 たとえばを呼び出す`GetFileTitle`ファイルに関するユーザー メッセージを生成する`c:\myhtml\myfile.txt`ファイルのタイトルを取得`myfile`します。  
  
### <a name="example"></a>例  
  例を参照してください[CFileFind::GetFileName](#getfilename)します。  
  
##  <a name="a-namegetfiletitlea--cfilefindgetfiletitle"></a><a name="getfiletitle"></a>CFileFind::GetFileTitle  
 検索したファイルのタイトルを取得するには、このメンバー関数を呼び出します。  
  
```  
virtual CString GetFileTitle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ファイルのタイトルです。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも&1; 回`GetFileTitle`します。  
  
 `GetFileTitle`3 つの&1; つ`CFileFind`を何らかの形式のファイル名を返すメンバー関数。 次の一覧には、3 つと、その違いについて説明します。  
  
- [GetFileName](#getfilename)拡張子を含む、ファイル名を返します。 たとえばを呼び出す`GetFileName`ファイルに関するユーザー メッセージを生成する`c:\myhtml\myfile.txt`ファイル名を返します`myfile.txt`します。  
  
- [まで含めた](#getfilepath)ファイルの完全なパスを返します。 たとえばを呼び出す`GetFilePath`ファイルに関するユーザー メッセージを生成する`c:\myhtml\myfile.txt`ファイル パスを返します`c:\myhtml\myfile.txt`します。  
  
- `GetFileTitle`ファイル拡張子を除く、ファイル名を返します。 たとえばを呼び出す`GetFileTitle`ファイルに関するユーザー メッセージを生成する`c:\myhtml\myfile.txt`ファイルのタイトルを取得`myfile`します。  
  
### <a name="example"></a>例  
  例を参照してください[CFileFind::GetFileName](#getfilename)します。  
  
##  <a name="a-namegetfileurla--cfilefindgetfileurl"></a><a name="getfileurl"></a>CFileFind::GetFileURL  
 指定された URL を取得するには、このメンバー関数を呼び出します。  
  
```  
virtual CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>戻り値  
 完全な URL。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも&1; 回`GetFileURL`します。  
  
 `GetFileURL`メンバー関数のような[まで含めた](#getfilepath)形式で URL が返される点が、`file://path`です。 たとえばを呼び出す`GetFileURL`の完全な URL を取得する`myfile.txt`URL を返します`file://c:\myhtml\myfile.txt`します。  
  
### <a name="example"></a>例  
  例を参照してください[CFileFind::GetFileName](#getfilename)します。  
  
##  <a name="a-namegetlastaccesstimea--cfilefindgetlastaccesstime"></a><a name="getlastaccesstime"></a>CFileFind::GetLastAccessTime  
 指定したファイルの最終アクセス時刻を取得するには、このメンバー関数を呼び出します。  
  
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
 成功した場合は 0 以外。それ以外の場合は 0 を返します。 `GetLastAccessTime`場合にのみ、0 を返します[FindNextFile](#findnextfile)は決してこので呼び出されて`CFileFind`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも&1; 回`GetLastAccessTime`します。  
  
> [!NOTE]
>  すべてのファイル システムでは、同じセマンティクスを使用して、この関数によって返される、タイムスタンプを実装します。 この関数は、基になるファイル システムまたはサーバーがサポートしない場合、時間属性を維持するその他のタイム スタンプ関数によって返される同じ値を返すことがあります。 参照してください、 [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造での時刻の書式に関する情報。 返される時刻をいくつかのオペレーティング システムでは、ファイルが存在するコンピューターにゾーンのローカル時刻でです。 Win32 を参照してください[詳細](http://msdn.microsoft.com/library/windows/desktop/ms724277)API の詳細。  
  
### <a name="example"></a>例  
  例を参照してください[CFileFind::GetLength](#getlength)します。  
  
##  <a name="a-namegetlastwritetimea--cfilefindgetlastwritetime"></a><a name="getlastwritetime"></a>CFileFind::GetLastWriteTime  
 最後に、ファイルが変更された時刻を取得するには、このメンバー関数を呼び出します。  
  
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
 成功した場合は 0 以外。それ以外の場合は 0 を返します。 `GetLastWriteTime`場合にのみ、0 を返します[FindNextFile](#findnextfile)は決してこので呼び出されて`CFileFind`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも&1; 回`GetLastWriteTime`します。  
  
> [!NOTE]
>  すべてのファイル システムでは、同じセマンティクスを使用して、この関数によって返される、タイムスタンプを実装します。 この関数は、基になるファイル システムまたはサーバーがサポートしない場合、時間属性を維持するその他のタイム スタンプ関数によって返される同じ値を返すことがあります。 参照してください、 [Win32_Find_Data](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造での時刻の書式に関する情報。 返される時刻をいくつかのオペレーティング システムでは、ファイルが存在するコンピューターにゾーンのローカル時刻でです。 Win32 を参照してください[詳細](http://msdn.microsoft.com/library/windows/desktop/ms724277)API の詳細。  
  
### <a name="example"></a>例  
  例を参照してください[CFileFind::GetLength](#getlength)します。  
  
##  <a name="a-namegetlengtha--cfilefindgetlength"></a><a name="getlength"></a>CFileFind::GetLength  
 このメンバー関数を呼び出して、見つかったファイルのバイトの長さを取得します。  
  
```  
ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>戻り値  
 (バイト単位) を検索したファイルの長さ。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも&1; 回`GetLength`します。  
  
 `GetLength`Win32 構造を使用して[WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)を取得し、ファイル サイズの値を返します (バイト単位) にします。  
  
> [!NOTE]
>  MFC 7.0 以降`GetLength`64 ビット整数型をサポートしています。 以前、ライブラリのこのより新しいバージョンで構築された既存のコードについては、切り捨ての警告があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles #&33;](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_3.cpp)]  
  
##  <a name="a-namegetroota--cfilefindgetroot"></a><a name="getroot"></a>CFileFind::GetRoot  
 検索したファイルのルートを取得するには、このメンバー関数を呼び出します。  
  
```  
virtual CString GetRoot() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アクティブな検索のルートです。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも&1; 回`GetRoot`します。  
  
 このメンバー関数は、ドライブ指定子と検索を開始するために使用するパス名を返します。 などを呼び出す[FindFile](#findfile)と`*.dat`結果`GetRoot`空の文字列を返すことです。 など、パスを渡して`c:\windows\system\*.dll`、 **FindFile**結果`GetRoot`返す`c:\windows\system\`します。  
  
### <a name="example"></a>例  
  例を参照してください[CFileFind::GetFileName](#getfilename)します。  
  
##  <a name="a-nameisarchiveda--cfilefindisarchived"></a><a name="isarchived"></a>CFileFind::IsArchived  
 検索したファイルがアーカイブになっているかどうかを判断するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsArchived() const;  
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションをマークするアーカイブ ファイルではバックアップまたは削除、FILE_ATTRIBUTE_ARCHIVE で識別されるファイル属性を[WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造体。  
  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも&1; 回`IsArchived`します。  
  
 メンバー関数を参照してください[は](#matchesmask)ファイル属性の完全な一覧についてです。  
  
### <a name="example"></a>例  
  例を参照してください[CFileFind::GetLength](#getlength)します。  
  
##  <a name="a-nameiscompresseda--cfilefindiscompressed"></a><a name="iscompressed"></a>CFileFind::IsCompressed  
 検索したファイルが圧縮されているかを判断するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsCompressed() const;  
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 圧縮されたファイルが FILE_ATTRIBUTE_COMPRESSED でマークされた、ファイル属性がで識別される、 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造体。 ファイルの場合は、この属性は、すべてのファイルにデータが圧縮されているを示します。 ディレクトリの場合は、この属性は、圧縮は、新しく作成されたファイルとサブディレクトリの既定値を示します。  
  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも&1; 回`IsCompressed`します。  
  
 メンバー関数を参照してください[は](#matchesmask)ファイル属性の完全な一覧についてです。  
  
### <a name="example"></a>例  
  例を参照してください[CFileFind::GetLength](#getlength)します。  
  
##  <a name="a-nameisdirectorya--cfilefindisdirectory"></a><a name="isdirectory"></a>CFileFind::IsDirectory  
 検索したファイルがディレクトリであるかを判断するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsDirectory() const;  
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ディレクトリのファイルが FILE_ATTRIBUTE_DIRECTORY で識別されるファイル属性でマークされた、 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造体。  
  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも&1; 回`IsDirectory`します。  
  
 メンバー関数を参照してください[は](#matchesmask)ファイル属性の完全な一覧についてです。  
  
### <a name="example"></a>例  
 この小さなプログラムでは、再帰の回数が、C:\ ドライブのすべてのディレクトリをディレクトリの名前を出力します。  
  
 [!code-cpp[NVC_MFCFiles #&34;](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_4.cpp)]  
  
##  <a name="a-nameisdotsa--cfilefindisdots"></a><a name="isdots"></a>CFileFind::IsDots  
 ファイル反復処理中に現在のディレクトリとその親ディレクトリのマーカーをテストするには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL IsDots() const;  
```  
  
### <a name="return-value"></a>戻り値  
 検索したファイルに名前がある場合、0 以外の値"です。"または".."、見つかったファイルが実際にはディレクトリです。 それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも&1; 回`IsDots`します。  
  
### <a name="example"></a>例  
  例を参照してください[CFileFind::IsDirectory](#isdirectory)します。  
  
##  <a name="a-nameishiddena--cfilefindishidden"></a><a name="ishidden"></a>CFileFind::IsHidden  
 検索したファイルが非表示を決定するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsHidden() const;  
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 FILE_ATTRIBUTE_HIDDEN でマークされた、非表示のファイルのファイル属性が識別される、 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造体。 隠しファイルは、通常のディレクトリ一覧には含まれません。  
  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも&1; 回`IsHidden`します。  
  
 メンバー関数を参照してください[は](#matchesmask)ファイル属性の完全な一覧についてです。  
  
### <a name="example"></a>例  
  例を参照してください[CFileFind::GetLength](#getlength)します。  
  
##  <a name="a-nameisnormala--cfilefindisnormal"></a><a name="isnormal"></a>CFileFind::IsNormal  
 検索したファイルが通常のファイルであるかを判断するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsNormal() const;  
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 FILE_ATTRIBUTE_NORMAL でマークされたファイル、ファイル属性の識別、 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造体。 通常のファイルには、他の属性セットがありません。 その他のすべてのファイル属性は、この属性をオーバーライドします。  
  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも&1; 回`IsNormal`します。  
  
 メンバー関数を参照してください[は](#matchesmask)ファイル属性の完全な一覧についてです。  
  
### <a name="example"></a>例  
  例を参照してください[CFileFind::GetLength](#getlength)します。  
  
##  <a name="a-nameisreadonlya--cfilefindisreadonly"></a><a name="isreadonly"></a>CFileFind::IsReadOnly  
 このメンバー関数を呼び出して、検索されたファイルが読み取り専用であるかどうか。  
  
```  
BOOL IsReadOnly() const;  
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 読み取り専用ファイルが FILE_ATTRIBUTE_READONLY でマークされた、ファイル属性がで識別される、 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造体。 アプリケーションは、この種類のファイルを読み取ることができますが、書き込むことやそれを削除できません。  
  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも&1; 回`IsReadOnly`します。  
  
 メンバー関数を参照してください[は](#matchesmask)ファイル属性の完全な一覧についてです。  
  
### <a name="example"></a>例  
  例を参照してください[CFileFind::GetLength](#getlength)します。  
  
##  <a name="a-nameissystema--cfilefindissystem"></a><a name="issystem"></a>CFileFind::IsSystem  
 検索したファイルがシステム ファイルであるかを判断するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsSystem() const;  
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 システム ファイルが、FILE_ATTRIBUTE_SYSTEM でマークされた、ファイル属性がで識別される、 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造体。 システム ファイルは、一部では、または排他的、オペレーティング システムによって使用されます。  
  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも&1; 回`IsSystem`します。  
  
 メンバー関数を参照してください[は](#matchesmask)ファイル属性の完全な一覧についてです。  
  
### <a name="example"></a>例  
  例を参照してください[CFileFind::GetLength](#getlength)します。  
  
##  <a name="a-nameistemporarya--cfilefindistemporary"></a><a name="istemporary"></a>CFileFind::IsTemporary  
 検索したファイルが一時ファイルを確認するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsTemporary() const;  
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 一時ファイルが FILE_ATTRIBUTE_TEMPORARY でマークされた、ファイル属性がで識別される、 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造体。 一時ファイルは、一時的な記憶域に使用されます。 アプリケーションは、絶対に必要な場合にのみ、ファイルに書き込む必要があります。 ファイルのデータの大部分は、ファイルがすぐに削除されるため、メディアに書き込まれずに、メモリに残ります。  
  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも&1; 回`IsTemporary`します。  
  
 メンバー関数を参照してください[は](#matchesmask)ファイル属性の完全な一覧についてです。  
  
### <a name="example"></a>例  
  例を参照してください[CFileFind::GetLength](#getlength)します。  
  
##  <a name="a-namemptma--cfilefindmptm"></a><a name="m_ptm"></a>CFileFind::m_pTM  
 ポインター、`CAtlTransactionManager`オブジェクトです。  
  
```  
CAtlTransactionManager* m_pTM;  
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namematchesmaska--cfilefindmatchesmask"></a><a name="matchesmask"></a>CFileFind::MatchesMask  
 検索したファイルのファイル属性をテストするには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL MatchesMask(DWORD dwMask) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `dwMask`  
 識別される&1; つまたは複数のファイル属性を指定します、 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)検索したファイルの構造です。 複数の属性を検索するには、ビットごとの OR を使用して (|) 演算子。 次の属性の任意の組み合わせは許容されます。  
  
-   FILE_ATTRIBUTE_ARCHIVE ファイルは、アーカイブ ファイルです。 アプリケーションでは、この属性を使用して、ファイルをバックアップまたは削除をマークします。  
  
-   FILE_ATTRIBUTE_COMPRESSED ファイルまたはディレクトリが圧縮されます。 ファイルのすべてのファイルにデータが圧縮されていることを意味します。 ディレクトリで圧縮が新しく作成されたファイルとサブディレクトリの既定値であることを意味します。  
  
-   FILE_ATTRIBUTE_DIRECTORY ファイルは、ディレクトリです。  
  
-   FILE_ATTRIBUTE_NORMAL ファイルには、他の属性セットがありません。 この属性は、単独で使用される場合にのみ有効です。 その他のすべてのファイル属性は、この属性をオーバーライドします。  
  
-   FILE_ATTRIBUTE_HIDDEN ファイルは表示されません。 通常のディレクトリ一覧に含めるには  
  
-   FILE_ATTRIBUTE_READONLY ファイルは読み取り専用です。 アプリケーションは、ファイルの読み取りことはできませんからの書き込みしたり削除できます。  
  
-   FILE_ATTRIBUTE_SYSTEM ファイルの一部であるか、オペレーティング システムによって排他的に使用されます。  
  
-   一時的な記憶域 FILE_ATTRIBUTE_TEMPORARY ファイルを使用しています。 アプリケーションは、絶対に必要な場合にのみ、ファイルに書き込む必要があります。 ファイルのデータの大部分は、ファイルがすぐに削除されるため、メディアに書き込まれずに、メモリに残ります。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 拡張エラー情報を取得するには、Win32 関数を呼び出して[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)します。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも&1; 回`MatchesMask`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles&#35;](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_5.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [関数のクラス](../../mfc/reference/cftpfilefind-class.md)   
 [関数のクラス](../../mfc/reference/cgopherfilefind-class.md)   
 [CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile クラス](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile クラス](../../mfc/reference/chttpfile-class.md)

