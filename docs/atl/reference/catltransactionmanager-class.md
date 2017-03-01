---
title: "CAtlTransactionManager クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlTransactionManager
- atltransactionmanager/ATL::CAtlTransactionManager
dev_langs:
- C++
helpviewer_keywords:
- CAtlTransactionManager class
ms.assetid: b01732dc-1d16-4b42-bfac-b137fca2b740
caps.latest.revision: 25
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
ms.openlocfilehash: bc6162eaf1a4c8c3848a32e861019ff50e4f850c
ms.lasthandoff: 02/24/2017

---
# <a name="catltransactionmanager-class"></a>CAtlTransactionManager クラス
CAtlTransactionManager クラスでは、カーネル トランザクション マネージャー (KTM) の関数のラッパーを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CAtlTransactionManager;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[~ CAtlTransactionManager](#dtor)|CAtlTransactionManager デストラクターです。|  
|[CAtlTransactionManager](#catltransactionmanager)|CAtlTransactionManager コンス トラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[閉じる](#close)|1 つのトランザクション ハンドルを閉じます。|  
|[コミット](#commit)|トランザクションをコミットすることを要求します。|  
|[作成します。](#create)|トランザクション ハンドルを作成します。|  
|[CreateFile](#createfile)|作成するか、ファイル、ファイル ストリーム、またはトランザクション処理された操作とディレクトリを開きます。|  
|[DeleteFile](#deletefile)|トランザクション処理された操作として、既存のファイルを削除します。|  
|[FindFirstFile](#findfirstfile)|トランザクション処理された操作として、ディレクトリのファイルまたはサブディレクトリを検索します。|  
|[向上した点](#getfileattributes)|トランザクション処理された操作として、指定したファイルまたはディレクトリのファイル システム属性を取得します。|  
|[GetFileAttributesEx](#getfileattributesex)|トランザクション処理された操作として、指定したファイルまたはディレクトリのファイル システム属性を取得します。|  
|[GetHandle](#gethandle)|トランザクション ハンドルを返します。|  
|[IsFallback](#isfallback)|フォールバックの呼び出しを有効にするかどうかを決定します。|  
|[MoveFile](#movefile)|既存のファイルまたはトランザクション処理された操作としてその子を含む、ディレクトリに移動します。|  
|[RegCreateKeyEx](#regcreatekeyex)|指定されたレジストリ キーを作成し、トランザクションに関連付けます。 キーが既に存在する場合、関数では、それが表示されます。|  
|[RegDeleteKey](#regdeletekey)|トランザクション処理された操作として、レジストリの指定したプラットフォーム固有のビューからサブキーとその値を削除します。|  
|[RegOpenKeyEx](#regopenkeyex)|指定されたレジストリ キーを開き、トランザクションに関連付けます。|  
|[ロールバック](#rollback)|トランザクションをロールバックするように要求します。|  
|[SetFileAttributes](#setfileattributes)|トランザクション処理された操作として、ファイルまたはディレクトリの属性を設定します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[m_bFallback](#m_bfallback)|`TRUE`フォールバックがサポートされている場合`FALSE`それ以外の場合。|  
|[m_hTransaction](#m_htransaction)|トランザクションのハンドルです。|  
  
## <a name="remarks"></a>コメント  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [ATL::CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atltransactionmanager.h  
  
##  <a name="a-namedtora--catltransactionmanager"></a><a name="dtor"></a>~ CAtlTransactionManager  
 CAtlTransactionManager デストラクターです。  
  
```
virtual ~CAtlTransactionManager();
```  
  
### <a name="remarks"></a>コメント  
 、通常の処理で、トランザクションが自動的にコミットされ終了します。 例外のアンワインド中にデストラクターが呼び出されると、トランザクションがロールバックされ、終了します。  
  
##  <a name="a-namecatltransactionmanagera--catltransactionmanager"></a><a name="catltransactionmanager"></a>CAtlTransactionManager  
 CAtlTransactionManager コンス トラクターです。  
  
```
CAtlTransactionManager(BOOL bFallback = TRUE, BOOL bAutoCreateTransaction = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bFallback`  
 `TRUE`フォールバックのサポートを示します。 トランザクション処理された関数が失敗した場合、クラスは自動的に「非トランザクション」関数を呼び出します。 `FALSE`「予備」の呼び出しがないことを示します。  
  
 `bAutoCreateTransaction`  
 `TRUE`コンス トラクターにトランザクション ハンドラーが自動的に作成されることを示します。 `FALSE`はないことを示します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameclosea--close"></a><a name="close"></a>閉じる  
 トランザクション ハンドルを閉じます。  
  
```
inline BOOL Close();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は `TRUE`。それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
 このラッパーを呼び出す、`CloseHandle`関数です。 メソッドは、デストラクターでは自動的に呼び出されます。  
  
##  <a name="a-namecommita--commit"></a><a name="commit"></a>コミット  
 トランザクションをコミットすることを要求します。  
  
```
inline BOOL Commit();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は `TRUE`。それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
 このラッパーを呼び出す、`CommitTransaction`関数です。 メソッドは、デストラクターでは自動的に呼び出されます。  
  
##  <a name="a-namecreatea--create"></a><a name="create"></a>作成します。  
 トランザクション ハンドルを作成します。  
  
```
inline BOOL Create();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は `TRUE`。それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
 このラッパーを呼び出す、`CreateTransaction`関数です。 チェックしてください。  
  
##  <a name="a-namecreatefilea--createfile"></a><a name="createfile"></a>CreateFile  
 作成するか、ファイル、ファイル ストリーム、またはトランザクション処理された操作とディレクトリを開きます。  
  
```
inline HANDLE CreateFile(
  LPCTSTR lpFileName,
    DWORD dwDesiredAccess,
    DWORD dwShareMode,
    LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    DWORD dwCreationDisposition,
    DWORD dwFlagsAndAttributes,
    HANDLE hTemplateFile);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFileName`  
 作成したり開いたりオブジェクトの名前。  
  
 `dwDesiredAccess`  
 読み取り、書き込み、またはどちらも、両方とも (ゼロ) としてまとめることができるオブジェクトにアクセスします。 最もよく使用される値は GENERIC_READ、GENERIC_WRITE、またはその両方: GENERIC_READ |GENERIC_WRITE します。  
  
 `dwShareMode`  
 オブジェクトが読み取り、書き込み、両方を削除、または、これらのすべての共有モード: FILE_SHARE_DELETE、FILE_SHARE_READ、FILE_SHARE_WRITE は 0 です。  
  
 `lpSecurityAttributes`  
 オプションのセキュリティ記述子が含まれています。 また、返されたハンドルを子プロセスが継承できるかどうかをも判断する SECURITY_ATTRIBUTES 構造体へのポインター。 パラメーターは、場合`NULL`します。  
  
 `dwCreationDisposition`  
 存在し、存在しないファイルに実行するアクション。 このパラメーターは、組み合わせることはできません、次の値のいずれかを指定する必要があります: CREATE_ALWAYS、CREATE_NEW、OPEN_ALWAYS、OPEN_EXISTING、または TRUNCATE_EXISTING です。  
  
 `dwFlagsAndAttributes`  
 ファイル属性とフラグです。 このパラメーターは、使用可能なファイル属性 (FILE_ATTRIBUTE_ *) の任意の組み合わせを含めることができます。 その他のすべてのファイル属性は、FILE_ATTRIBUTE_NORMAL をオーバーライドします。 このパラメーターは、フラグの組み合わせを含めることも (file_flag _\*) バッファー動作の制御、アクセス モード、およびその他の特殊なフラグです。 これらを組み合わせて、任意の FILE_ATTRIBUTE_ で\*値。  
  
 `hTemplateFile`  
 GENERIC_READ アクセス権を持つテンプレート ファイルに有効なハンドル。 テンプレート ファイルは、ファイルの属性と作成されるファイルの拡張属性を提供します。 このパラメーターは、`NULL` に設定できます。  
  
### <a name="return-value"></a>戻り値  
 オブジェクトへのアクセスに使用できるハンドルを返します。  
  
### <a name="remarks"></a>コメント  
 このラッパーを呼び出す、`CreateFileTransacted`関数です。  
  
##  <a name="a-namedeletefilea--deletefile"></a><a name="deletefile"></a>DeleteFile  
 トランザクション処理された操作として、既存のファイルを削除します。  
  
```
inline BOOL DeleteFile(LPCTSTR lpFileName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFileName`  
 削除するファイルの名前。  
  
### <a name="remarks"></a>コメント  
 このラッパーを呼び出す、`DeleteFileTransacted`関数です。  
  
##  <a name="a-namefindfirstfilea--findfirstfile"></a><a name="findfirstfile"></a>FindFirstFile  
 トランザクション処理された操作として、ディレクトリのファイルまたはサブディレクトリを検索します。  
  
```
inline HANDLE FindFirstFile(
  LPCTSTR lpFileName,
  WIN32_FIND_DATA* pNextInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFileName`  
 ディレクトリまたはパス、およびファイル名を検索します。 このパラメーターは、アスタリスク (*) や疑問符 () () などのワイルドカード文字を含めることができます。  
  
 `pNextInfo`  
 検索したファイルまたはサブディレクトリに関する情報を受け取る WIN32_FIND_DATA 構造体へのポインター。  
  
### <a name="return-value"></a>戻り値  
 戻り値は、検索ハンドルに、関数が成功すると、`FindNextFile`または`FindClose`です。 関数が失敗またはで検索文字列からファイルを検索に失敗したかどうか、`lpFileName`パラメーター、戻り値は、INVALID_HANDLE_VALUE です。  
  
### <a name="remarks"></a>コメント  
 このラッパーを呼び出す、`FindFirstFileTransacted`関数です。  
  
##  <a name="a-namegetfileattributesa--getfileattributes"></a><a name="getfileattributes"></a>向上した点  
 トランザクション処理された操作として、指定したファイルまたはディレクトリのファイル システム属性を取得します。  
  
```
inline DWORD GetFileAttributes(LPCTSTR lpFileName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFileName`  
 ファイルまたはディレクトリの名前。  
  
### <a name="remarks"></a>コメント  
 このラッパーを呼び出す、`GetFileAttributesTransacted`関数です。  
  
##  <a name="a-namegetfileattributesexa--getfileattributesex"></a><a name="getfileattributesex"></a>GetFileAttributesEx  
 トランザクション処理された操作として、指定したファイルまたはディレクトリのファイル システム属性を取得します。  
  
```
inline BOOL GetFileAttributesEx(
    LPCTSTR lpFileName,
    GET_FILEEX_INFO_LEVELS fInfoLevelId,
    LPVOID lpFileInformation);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFileName`  
 ファイルまたはディレクトリの名前。  
  
 `fInfoLevelId`  
 取得する属性情報のレベル。  
  
 `lpFileInformation`  
 属性の情報を受け取るバッファーへのポインター。 このバッファーに格納されている属性情報の種類の値によって決まります`fInfoLevelId`します。 場合、`fInfoLevelId`パラメーターは GetFileExInfoStandard し、このパラメーターが WIN32_FILE_ATTRIBUTE_DATA 構造体をポイントします。  
  
### <a name="remarks"></a>コメント  
 このラッパーを呼び出す、`GetFileAttributesTransacted`関数です。  
  
##  <a name="a-namegethandlea--gethandle"></a><a name="gethandle"></a>GetHandle  
 トランザクション ハンドルを返します。  
  
```
HANDLE GetHandle() const;
```  
  
### <a name="return-value"></a>戻り値  
 クラスのトランザクション ハンドルを返します。 返します。`NULL`場合、`CAtlTransactionManager`ハンドルにアタッチされていません。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameisfallbacka--isfallback"></a><a name="isfallback"></a>IsFallback  
 フォールバックの呼び出しを有効にするかどうかを決定します。  
  
```
BOOL IsFallback() const;
```  
  
### <a name="return-value"></a>戻り値  
 返します。`TRUE`クラスは、フォールバック呼び出しをサポートしています。 それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namembfallbacka--mbfallback"></a><a name="m_bfallback"></a>m_bFallback  
 `TRUE`フォールバックがサポートされている場合`FALSE`それ以外の場合。  
  
```
BOOL m_bFallback;
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namemhtransactiona--mhtransaction"></a><a name="m_htransaction"></a>m_hTransaction  
 トランザクションのハンドルです。  
  
```
HANDLE m_hTransaction;
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namemovefilea--movefile"></a><a name="movefile"></a>MoveFile  
 既存のファイルまたはトランザクション処理された操作としてその子を含む、ディレクトリに移動します。  
  
```
inline BOOL MoveFile(LPCTSTR lpOldFileName, LPCTSTR lpNewFileName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpOldFileName`  
 既存のファイルまたはローカル コンピューター上のディレクトリの現在の名前。  
  
 `lpNewFileName`  
 ファイルまたはディレクトリの新しい名前。 この名前が既に存在していません。 新しいファイルが別のファイル システムまたはドライブにあります。 新しいディレクトリは、同じドライブにある必要があります。  
  
### <a name="remarks"></a>コメント  
 このラッパーを呼び出す、`MoveFileTransacted`関数です。  
  
##  <a name="a-nameregcreatekeyexa--regcreatekeyex"></a><a name="regcreatekeyex"></a>RegCreateKeyEx  
 指定されたレジストリ キーを作成し、トランザクションに関連付けます。 キーが既に存在する場合、関数では、それが表示されます。  
  
```
inline LSTATUS RegCreateKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD dwReserved,
    LPTSTR lpClass,
    DWORD dwOptions,
    REGSAM samDesired,
    CONST LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    PHKEY phkResult,
    LPDWORD lpdwDisposition);
```  
  
### <a name="parameters"></a>パラメーター  
 `hKey`  
 開いているレジストリ キーへのハンドル。  
  
 `lpSubKey`  
 この関数を開くか作成するサブキーの名前。  
  
 `dwReserved`  
 このパラメーターは予約されており、0 にする必要があります。  
  
 `lpClass`  
 このキーのユーザー定義のクラスです。 このパラメーターは無視できます。 このパラメーターは、NULL を指定できます。  
  
 `dwOptions`  
 このパラメーターは、次の値のいずれかを指定できます: REG_OPTION_BACKUP_RESTORE、REG_OPTION_NON_VOLATILE、または REG_OPTION_VOLATILE です。  
  
 `samDesired`  
 キーのアクセス権を指定するマスクです。  
  
 `lpSecurityAttributes`  
 返されたハンドルを子プロセスが継承できるかどうかを決定する SECURITY_ATTRIBUTES 構造体へのポインター。 場合`lpSecurityAttributes`は`NULL`ハンドルは継承できません。  
  
 `phkResult`  
 開くか作成されたキーへのハンドルを受け取る変数へのポインター。 キーが定義済みのレジストリ キーのいずれかでない場合は、呼び出し、`RegCloseKey`ハンドルの使用が完了した後に機能します。  
  
 `lpdwDisposition`  
 可能な値に次のいずれかを受け取る変数へのポインター。 ポインター。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は、error_success を返しますを返します。 関数が失敗した場合は、Winerror.h で定義されている&0; 以外のエラー コードは、戻り値。  
  
### <a name="remarks"></a>コメント  
 このラッパーを呼び出す、`RegCreateKeyTransacted`関数です。  
  
##  <a name="a-nameregdeletekeya--regdeletekey"></a><a name="regdeletekey"></a>RegDeleteKey  
 トランザクション処理された操作として、レジストリの指定したプラットフォーム固有のビューからサブキーとその値を削除します。  
  
```
inline LSTATUS RegDeleteKeyEx(HKEY hKey, LPCTSTR lpSubKey);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`hKey`|開いているレジストリ キーへのハンドル。|  
|`lpSubKey`|削除するキーの名前。|  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は、error_success を返しますを返します。 関数が失敗した場合は、Winerror.h で定義されている&0; 以外のエラー コードは、戻り値。  
  
### <a name="remarks"></a>コメント  
 このラッパーを呼び出す、`RegDeleteKeyTransacted`関数です。  
  
##  <a name="a-nameregopenkeyexa--regopenkeyex"></a><a name="regopenkeyex"></a>RegOpenKeyEx  
 指定されたレジストリ キーを開き、トランザクションに関連付けます。  
  
```
inline LSTATUS RegOpenKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD ulOptions,
    REGSAM samDesired,
    PHKEY phkResult);
```  
  
### <a name="parameters"></a>パラメーター  
 `hKey`  
 開いているレジストリ キーへのハンドル。  
  
 `lpSubKey`  
 開かれているレジストリ サブキーの名前。  
  
 `ulOptions`  
 このパラメーターは予約されており、0 にする必要があります。  
  
 `samDesired`  
 キーのアクセス権を指定するマスクです。  
  
 `phkResult`  
 開くか作成されたキーへのハンドルを受け取る変数へのポインター。 キーが定義済みのレジストリ キーのいずれかでない場合は、呼び出し、`RegCloseKey`ハンドルの使用が完了した後に機能します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は、error_success を返しますを返します。 戻り値は、Winerror.h で定義されている&0; 以外のエラー コード、関数が失敗した場合、します。  
  
### <a name="remarks"></a>コメント  
 このラッパーを呼び出す、`RegOpenKeyTransacted`関数です。  
  
##  <a name="a-namerollbacka--rollback"></a><a name="rollback"></a>ロールバック  
 トランザクションをロールバックするように要求します。  
  
```
inline BOOL Rollback();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は `TRUE`。それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
 このラッパーを呼び出す、`RollbackTransaction`関数です。  
  
##  <a name="a-namesetfileattributesa--setfileattributes"></a><a name="setfileattributes"></a>SetFileAttributes  
 トランザクション処理された操作として、ファイルまたはディレクトリの属性を設定します。  
  
```
inline BOOL SetFileAttributes(LPCTSTR lpFileName, DWORD dwAttributes);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFileName`  
 ファイルまたはディレクトリの名前。  
  
 `dwAttributes`  
 ファイルに対して設定するファイル属性。 詳細については、次を参照してください。 [SetFileAttributesTransacted](http://go.microsoft.com/fwlink/linkid=158699)します。  
  
### <a name="remarks"></a>コメント  
 このラッパーを呼び出す、`SetFileAttributesTransacted`関数です。  
  
## <a name="see-also"></a>関連項目  
 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)

