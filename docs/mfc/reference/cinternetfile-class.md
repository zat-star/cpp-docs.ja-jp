---
title: "CInternetFile クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInternetFile
dev_langs:
- C++
helpviewer_keywords:
- CInternetFile class
- Internet files
- Internet files, CInternetFile class
ms.assetid: 96935681-ee71-4a8d-9783-5abc7b3e6f10
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
ms.openlocfilehash: 6e1d6227ebd642025e6b00019518d29080cf0454
ms.lasthandoff: 02/24/2017

---
# <a name="cinternetfile-class"></a>CInternetFile クラス
インターネット プロトコルを使用するリモート システム上のファイルにアクセスをできます。  
  
## <a name="syntax"></a>構文  
  
```  
class CInternetFile : public CStdioFile  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CInternetFile::CInternetFile](#cinternetfile)|`CInternetFile` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CInternetFile::Abort](#abort)|すべての警告およびエラーを無視して、ファイルを閉じます。|  
|[CInternetFile::Close](#close)|閉じる、`CInternetFile`とそのリソースを解放します。|  
|[CInternetFile::Flush](#flush)|書き込みバッファーの内容をフラッシュし、対象コンピューターにメモリ内のデータが書き込まれるようにします。|  
|[CInternetFile::GetLength](#getlength)|ファイルのサイズを返します。|  
|[細かい](#read)|指定したバイト数を読み取ります。|  
|[CInternetFile::ReadString](#readstring)|文字のストリームを読み取ります。|  
|[CInternetFile::Seek](#seek)|開いているファイルのポインターを移動します。|  
|[CInternetFile::SetReadBufferSize](#setreadbuffersize)|データの読み取りがバッファーのサイズを設定します。|  
|[CInternetFile::SetWriteBufferSize](#setwritebuffersize)|データの書き込み先のバッファーのサイズを設定します。|  
|[CInternetFile::Write](#write)|指定されたバイト数を書き込みます。|  
|[CInternetFile::WriteString](#writestring)|Null で終わる文字列をファイルに書き込みます。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CInternetFile::operator HINTERNET](#operator_hinternet)|インターネット ハンドルのキャスト演算子です。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CInternetFile::m_hFile](#m_hfile)|ファイルへのハンドル。|  
  
## <a name="remarks"></a>コメント  
 基本クラスを提供、 [CHttpFile](../../mfc/reference/chttpfile-class.md)と[CGopherFile](../../mfc/reference/cgopherfile-class.md)ファイル クラスです。 作成しないで、`CInternetFile`オブジェクトに直接します。 代わりを呼び出してその派生クラスのいずれかのオブジェクトを作成[CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile)または[しないで](../../mfc/reference/chttpconnection-class.md#openrequest)します。 作成することも、`CInternetFile`を呼び出してオブジェクト[CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile)します。  
  
 `CInternetFile`メンバー関数**開く**、 `LockRange`、 `UnlockRange`、および`Duplicate`は適用されていない`CInternetFile`します。 これらの関数を呼び出した場合、`CInternetFile`オブジェクトの取得は、[行わない](../../mfc/reference/cnotsupportedexception-class.md)します。  
  
 方法について説明する`CInternetFile`他のインターネットの MFC クラスと動作は、記事を参照して[WinInet を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 `CInternetFile`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxinet.h  
  
##  <a name="a-nameaborta--cinternetfileabort"></a><a name="abort"></a>CInternetFile::Abort  
 このオブジェクトに関連付けられているファイルを閉じ、ファイルを読み取りまたは書き込みが使用できなくなります。  
  
```  
virtual void Abort();
```  
  
### <a name="remarks"></a>コメント  
 オブジェクトを破棄する前に、ファイルを終了しなかった場合、デストラクターがファイルを閉じます。  
  
 例外を処理するときに**中止**とは異なります[閉じる](#close)の&2; つの重要な点です。 1 つは、**中止**エラーを無視するため、関数がエラーに例外をスローしません。 2 番目、**中止**しない**ASSERT**ファイルが開かれていない、または以前に閉じられました。  
  
##  <a name="a-namecinternetfilea--cinternetfilecinternetfile"></a><a name="cinternetfile"></a>CInternetFile::CInternetFile  
 このメンバー関数が呼び出されます、`CInternetFile`オブジェクトを作成します。  
  
```  
CInternetFile(
    HINTERNET hFile,  
    LPCTSTR pstrFileName,  
    CInternetConnection* pConnection,  
    BOOL bReadMode);

 
CInternetFile(
    HINTERNET hFile,  
    HINTERNET hSession,  
    LPCTSTR pstrFileName,  
    LPCTSTR pstrServer,  
    DWORD_PTR dwContext,  
    BOOL bReadMode);
```  
  
### <a name="parameters"></a>パラメーター  
 `hFile`  
 インターネット ファイルへのハンドル。  
  
 `pstrFileName`  
 ファイル名を含む文字列へのポインター。  
  
 `pConnection`  
 ポインター、[関数](../../mfc/reference/cinternetconnection-class.md)オブジェクトです。  
  
 *bReadMode*  
 ファイルが読み取り専用であるかどうかを示します。  
  
 `hSession`  
 インターネット セッションへのハンドル。  
  
 `pstrServer`  
 サーバーの名前を含む文字列へのポインター。  
  
 `dwContext`  
 コンテキスト識別子、`CInternetFile`オブジェクトです。 参照してください[WinInet の基礎](../../mfc/wininet-basics.md)詳細については、コンテキスト識別子。  
  
### <a name="remarks"></a>コメント  
 作成しないで、`CInternetFile`オブジェクトに直接します。 代わりを呼び出してその派生クラスのいずれかのオブジェクトを作成[CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile)または[しないで](../../mfc/reference/chttpconnection-class.md#openrequest)します。 作成することも、`CInternetFile`を呼び出してオブジェクト[CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile)します。  
  
##  <a name="a-nameclosea--cinternetfileclose"></a><a name="close"></a>CInternetFile::Close  
 閉じる、`CInternetFile`のリソースを解放します。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>コメント  
 書き込みのため、ファイルが開かれた場合は、暗黙の呼び出しに[フラッシュ](#flush)バッファリングされたすべてのデータを確保するためには、ホストに書き込まれます。 呼び出す必要があります**閉じる**ファイルの使用が終了したとします。  
  
##  <a name="a-nameflusha--cinternetfileflush"></a><a name="flush"></a>CInternetFile::Flush  
 書き込みバッファーの内容をフラッシュするには、このメンバー関数を呼び出します。  
  
```  
virtual void Flush();
```  
  
### <a name="remarks"></a>コメント  
 使用`Flush`メモリ内のすべてのデータがターゲット コンピューターに実際に書き込まれたことを保証するために、ホスト コンピューターとのトランザクションの完了を保証するためにします。 `Flush`有効になるのみ`CInternetFile`オブジェクトを開いて書き込む。  
  
##  <a name="a-namegetlengtha--cinternetfilegetlength"></a><a name="getlength"></a>CInternetFile::GetLength  
 ファイルのサイズを返します。  
  
```  
virtual ULONGLONG GetLength() const;  
```  
  
##  <a name="a-namemhfilea--cinternetfilemhfile"></a><a name="m_hfile"></a>CInternetFile::m_hFile  
 このオブジェクトに関連付けられているファイルへのハンドル。  
  
```  
HINTERNET m_hFile;  
```  
  
##  <a name="a-nameoperatorhinterneta--cinternetfileoperator-hinternet"></a><a name="operator_hinternet"></a>CInternetFile::operator HINTERNET  
 この演算子を使用して、現在のインターネット セッションの Windows ハンドルを取得します。  
  
```  
operator HINTERNET() const;  
```  
  
##  <a name="a-namereada--cinternetfileread"></a><a name="read"></a>細かい  
 このメンバー関数を呼び出して、指定されたメモリに読み込みます。`lpvBuf` を先頭として、`nCount` で指定されたバイト数を読み込みます。  
  
```  
virtual UINT Read(
    void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpBuf`  
 ファイル データを読み込むメモリ アドレスへのポインター。  
  
 `nCount`  
 書き込むバイト数。  
  
### <a name="return-value"></a>戻り値  
 バッファーに転送するバイト数。 ファイルの末尾に達した場合、戻り値は、`nCount` より小さくなることがあります。  
  
### <a name="remarks"></a>コメント  
 関数は実際に読み取ったバイト数を返します。ファイルの末尾に達した場合、`nCount` より小さくなることがあります。 ファイルの読み取り中にエラーが発生した場合、関数、[表す](../../mfc/reference/cinternetexception-class.md)エラーを説明するオブジェクト。 ファイルの末尾を越える読み取りはエラーとは見なされず、例外がスローされないことに注意してください。  
  
 呼び出すすべてのデータが取得されるようにするには、アプリケーションを継続する必要があります、**細かい**メソッドまで、0 を返します。  
  
##  <a name="a-namereadstringa--cinternetfilereadstring"></a><a name="readstring"></a>CInternetFile::ReadString  
 改行文字が見つかるまでの文字のストリームを読み取るには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL ReadString(CString& rString);

 
virtual LPTSTR ReadString(
    LPTSTR pstr,  
    UINT nMax);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstr`  
 読み取られる行が格納される文字列へのポインター。  
  
 `nMax`  
 読み取る文字の最大数。  
  
 `rString`  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)読み取りの行を受け取るオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 取得されたプレーンなデータを格納しているバッファーへのポインター、 [CInternetFile](../../mfc/reference/cinternetfile-class.md)オブジェクトです。 このメソッドに渡されたバッファーのデータ型に関係なくデータ (たとえば、Unicode に変換) の任意の操作を行わず、期待の構造体に返されるデータをマップする必要がありますので、まるで、 **void\* **型が返されました。  
  
 **NULL**場合はブール値、またはすべてのデータを読み取り中にファイルの終端に達した場合**FALSE**読み取らずに、データ ファイルの終端に達した場合。  
  
### <a name="remarks"></a>コメント  
 この関数で参照されるメモリに、その結果、行を配置する、`pstr`パラメーター。 文字の読み取りを停止することで指定された文字の最大数に達したとき`nMax`します。 バッファーは、常に終端の null 文字を受け取ります。  
  
 呼び出した場合`ReadString`最初に呼び出さず[SetReadBufferSize](#setreadbuffersize)、4096 バイトのバッファーが表示されます。  
  
##  <a name="a-nameseeka--cinternetfileseek"></a><a name="seek"></a>CInternetFile::Seek  
 このメンバー関数を呼び出して以前に開いたファイルのポインターを移動します。  
  
```  
virtual ULONGLONG Seek(
    LONGLONG lOffset,  
    UINT nFrom);
```  
  
### <a name="parameters"></a>パラメーター  
 `lOffset`  
 ファイルの読み取り/書き込みのポインターを移動するバイト オフセットします。  
  
 `nFrom`  
 オフセットの相対参照します。 次の値のいずれかを指定する必要があります。  
  
- **CFile::begin**ファイル ポインターを移動`lOff`ファイルの先頭からのバイト数を転送します。  
  
- **CFile::current**ファイル ポインターを移動`lOff`ファイル内の現在位置からのバイト。  
  
- **CFile::end**ファイル ポインターを移動`lOff`ファイルの末尾からのバイト。 `lOff`負の値を既存のファイルにする必要があります。ファイルの末尾を超える正の値を求めます。  
  
### <a name="return-value"></a>戻り値  
 新しいバイトを要求した位置が; 有効な場合、ファイルの先頭からのオフセットそれ以外の場合、値は未定義と[表す](../../mfc/reference/cinternetexception-class.md)オブジェクトがスローされます。  
  
### <a name="remarks"></a>コメント  
 `Seek`関数を使用するファイルの内容へのランダム アクセス、ポインターを移動して、指定した時間絶対的または相対的です。 データは、検索中に実際には読み込まれません。  
  
 この時点でこのメンバー関数への呼び出しはのみと関連付けられたデータ サポート`CHttpFile`オブジェクトです。 FTP または gopher 要求に対してはサポートされません。 呼び出した場合`Seek`これらのサポートされていないサービスの&1; つは、処理、バックアップするを Win32 エラー コード**ERROR_INTERNET_INVALID_OPERATION**します。  
  
 ファイルを開いたときに、ファイル ポインターがオフセット 0 で、ファイルの先頭には。  
  
> [!NOTE]
>  使用して`Seek`への暗黙の呼び出しが発生する可能性があります[フラッシュ](#flush)します。  
  
### <a name="example"></a>例  
  基本クラスの実装の例を参照してください ( [CFile::Seek](../../mfc/reference/cfile-class.md#seek))。  
  
##  <a name="a-namesetreadbuffersizea--cinternetfilesetreadbuffersize"></a><a name="setreadbuffersize"></a>CInternetFile::SetReadBufferSize  
 使用される一時的な読み取りバッファーのサイズを設定するには、このメンバー関数を呼び出す、 `CInternetFile`-派生オブジェクト。  
  
```  
BOOL SetReadBufferSize(UINT nReadSize);
```  
  
### <a name="parameters"></a>パラメーター  
 *nReadSize*  
 バイト単位のバッファー サイズ。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのには呼び出すことができます。  
  
### <a name="remarks"></a>コメント  
 基になる WinInet Api はバッファー処理を実行ではなくバッファー サイズ、アプリケーションを読み取るデータの量に関係なく、効率的にデータを読み取ることができるように選択します。 各呼び出し場合[読み取り](#read)通常で大量 (たとえば、4 つまたは複数のキロバイト)、データの必要はありませんバッファー。 ただしを呼び出す場合**読み取り**少量のデータを取得または使用する場合[ReadString](#readstring)読み取りバッファーは、アプリケーションのパフォーマンスを向上し、一度に&1; 行ずつを読み取る。  
  
 既定では、`CInternetFile`オブジェクトでは提供されません。 このメンバー関数を呼び出した場合は、読み取りアクセスのため、ファイルが開かれたことを確認する必要があります。  
  
 いつでも、バッファー サイズを増やすことができますが、バッファーを縮小効果はありません。 呼び出した場合[ReadString](#readstring)最初に呼び出さず`SetReadBufferSize`、4096 バイトのバッファーが表示されます。  
  
##  <a name="a-namesetwritebuffersizea--cinternetfilesetwritebuffersize"></a><a name="setwritebuffersize"></a>CInternetFile::SetWriteBufferSize  
 使用される一時的な書き込みバッファーのサイズを設定するには、このメンバー関数を呼び出す、 `CInternetFile`-派生オブジェクト。  
  
```  
BOOL SetWriteBufferSize(UINT nWriteSize);
```  
  
### <a name="parameters"></a>パラメーター  
 *nWriteSize*  
 バッファーのサイズ (バイト単位)。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのには呼び出すことができます。  
  
### <a name="remarks"></a>コメント  
 デバッグ情報を基になる、WinInet Api は、バッファリングを実行しないようを使うと、アプリケーションを記述するデータの量に関係なく効率的にデータを書き込むバッファー サイズに選択します。 各呼び出し場合[書き込み](#write)消費量は通常、(たとえば、次の&4; つまたは複数キロバイト一度に)、データの必要はありませんバッファー。 ただしを呼び出す場合[書き込み](#write)書き込みバッファー小さいデータ チャンクの書き込みは、アプリケーションのパフォーマンスが向上します。  
  
 既定では、`CInternetFile`オブジェクトでは提供されません。 このメンバー関数を呼び出した場合は、書き込みアクセスのため、ファイルが開かれたことを確認する必要があります。 いつでも書き込みバッファーのサイズを変更できますが、そのようにすると、暗黙的に呼び出す[フラッシュ](#flush)します。  
  
##  <a name="a-namewritea--cinternetfilewrite"></a><a name="write"></a>CInternetFile::Write  
 このメンバー関数を呼び出して指定されたメモリへの書き込み`lpvBuf`、指定された数 (バイト単位) の`nCount`です。  
  
```  
virtual void Write(
    const void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpBuf`  
 書き込まれる最初のバイトへのポインター。  
  
 `nCount`  
 書き込むバイト数を指定します。  
  
### <a name="remarks"></a>コメント  
 データの書き込み中にエラーが発生した場合、関数、[表す](../../mfc/reference/cinternetexception-class.md)エラーを説明するオブジェクト。  
  
##  <a name="a-namewritestringa--cinternetfilewritestring"></a><a name="writestring"></a>CInternetFile::WriteString  
 この関数は、null で終わる文字列を関連付けられたファイルに書き込みます。  
  
```  
virtual void WriteString(LPCTSTR pstr);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstr`  
 書き込むコンテンツを含む文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 データの書き込み中にエラーが発生した場合、関数、[表す](../../mfc/reference/cinternetexception-class.md)エラーを説明するオブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [CStdioFile クラス](../../mfc/reference/cstdiofile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [関数のクラス](../../mfc/reference/cinternetconnection-class.md)

