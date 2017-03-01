---
title: "CAtlTemporaryFile クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlTemporaryFile
- ATL.CAtlTemporaryFile
- ATL::CAtlTemporaryFile
dev_langs:
- C++
helpviewer_keywords:
- CAtlTemporaryFile class
ms.assetid: 05f0f2a5-94f6-4594-8dae-b114292ff5f9
caps.latest.revision: 18
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
ms.openlocfilehash: 9673c5a137feddb0eb696945ec6abeb5f3cb062e
ms.lasthandoff: 02/24/2017

---
# <a name="catltemporaryfile-class"></a>CAtlTemporaryFile クラス
このクラスは、作成および一時ファイルを使用するメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CAtlTemporaryFile
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)|コンストラクターです。|  
|[CAtlTemporaryFile:: ~ CAtlTemporaryFile](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlTemporaryFile::Close](#close)|一時ファイルを閉じるには、このメソッドを呼び出して、その内容を削除するか、または指定したファイル名で保存しています。|  
|[CAtlTemporaryFile::Create](#create)|一時ファイルを作成するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::Flush](#flush)|このメソッドを呼び出して強制的に一時ファイルに書き込まれるファイル バッファーの残りの部分。|  
|[CAtlTemporaryFile::GetPosition](#getposition)|現在のファイル ポインターの位置を取得するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::GetSize](#getsize)|一時ファイルのバイト単位のサイズを取得するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::HandsOff](#handsoff)|ファイルの関連付けを解除するには、このメソッドを呼び出して、`CAtlTemporaryFile`オブジェクトです。|  
|[CAtlTemporaryFile::HandsOn](#handson)|既存の一時ファイルを開き、ファイルの末尾にカーソルを移動するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::LockRange](#lockrange)|他のプロセスがアプリケーションにアクセスすることを防ぐために、ファイル内の領域をロックするには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::Read](#read)|ファイル ポインターが指す位置以降にある一時ファイルからデータを読み取るには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::Seek](#seek)|一時ファイルのファイル ポインターを移動するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::SetSize](#setsize)|一時ファイルのサイズを設定するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::TempFileName](#tempfilename)|このメソッドを呼び出して、一時ファイルの名前を返します。|  
|[CAtlTemporaryFile::UnlockRange](#unlockrange)|一時ファイルの領域のロックを解除するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::Write](#write)|ファイル ポインターが指す位置以降にある一時ファイルにデータを書き込むには、このメソッドを呼び出します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlTemporaryFile::operator ハンドル](#operator_handle)|一時ファイルにハンドルを返します。|  
  
## <a name="remarks"></a>コメント  
 `CAtlTemporaryFile`作成し、一時ファイルを使用できるようになります。 ファイルが自動的にという名前、開くを閉じると、および削除します。 ファイルの内容は、ファイルが閉じられた後に必要な場合は、指定した名前の新しいファイルに保存できます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlfile.h  
  
## <a name="example"></a>例  
 例を参照してください[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)します。  
  
##  <a name="a-namecatltemporaryfilea--catltemporaryfilecatltemporaryfile"></a><a name="catltemporaryfile"></a>CAtlTemporaryFile::CAtlTemporaryFile  
 コンストラクターです。  
  
```
CAtlTemporaryFile() throw();
```  
  
### <a name="remarks"></a>コメント  
 ファイルが実際に開いていないへの呼び出しが行われるまで[CAtlTemporaryFile::Create](#create)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&73;](../../atl/codesnippet/cpp/catltemporaryfile-class_1.cpp)]  
  
##  <a name="a-namedtora--catltemporaryfilecatltemporaryfile"></a><a name="dtor"></a>CAtlTemporaryFile:: ~ CAtlTemporaryFile  
 デストラクターです。  
  
```
~CAtlTemporaryFile() throw();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターの呼び出し[CAtlTemporaryFile::Close](#close)します。  
  
##  <a name="a-nameclosea--catltemporaryfileclose"></a><a name="close"></a>CAtlTemporaryFile::Close  
 一時ファイルを閉じるには、このメソッドを呼び出して、その内容を削除するか、または指定したファイル名で保存しています。  
  
```
HRESULT Close(LPCTSTR szNewName = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *szNewName*  
 一時ファイルの内容を格納する新しいファイルの名前。 この引数が NULL の場合は、一時ファイルの内容が削除されます。  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="example"></a>例  
 例を参照してください[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)します。  
  
##  <a name="a-namecreatea--catltemporaryfilecreate"></a><a name="create"></a>CAtlTemporaryFile::Create  
 一時ファイルを作成するには、このメソッドを呼び出します。  
  
```
HRESULT Create(LPCTSTR pszDir = NULL, DWORD dwDesiredAccess = GENERIC_WRITE) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszDir`  
 一時ファイルのパス。 これが NULL の場合、 [GetTempPath](http://msdn.microsoft.com/library/windows/desktop/aa364992)パスを割り当てるには、呼び出されます。  
  
 `dwDesiredAccess`  
 必要なアクセスします。 参照してください`dwDesiredAccess`で[CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="example"></a>例  
 例を参照してください[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)します。  
  
##  <a name="a-nameflusha--catltemporaryfileflush"></a><a name="flush"></a>CAtlTemporaryFile::Flush  
 このメソッドを呼び出して強制的に一時ファイルに書き込まれるファイル バッファーの残りの部分。  
  
```
HRESULT Flush() throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="remarks"></a>コメント  
 ような[CAtlTemporaryFile::HandsOff](#handsoff)ファイルが閉じられていない点が異なります。  
  
### <a name="example"></a>例  
 例を参照してください[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)します。  
  
##  <a name="a-namegetpositiona--catltemporaryfilegetposition"></a><a name="getposition"></a>CAtlTemporaryFile::GetPosition  
 現在のファイル ポインターの位置を取得するには、このメソッドを呼び出します。  
  
```
HRESULT GetPosition(ULONGLONG& nPos) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nPos`  
 内のバイト位置。  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="remarks"></a>コメント  
 ファイル ポインターの位置を変更するには、使用[CAtlTemporaryFile::Seek](#seek)します。  
  
##  <a name="a-namegetsizea--catltemporaryfilegetsize"></a><a name="getsize"></a>CAtlTemporaryFile::GetSize  
 一時ファイルのバイト単位のサイズを取得するには、このメソッドを呼び出します。  
  
```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nLen`  
 ファイル内のバイト数。  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
##  <a name="a-namehandsoffa--catltemporaryfilehandsoff"></a><a name="handsoff"></a>CAtlTemporaryFile::HandsOff  
 ファイルの関連付けを解除するには、このメソッドを呼び出して、`CAtlTemporaryFile`オブジェクトです。  
  
```
HRESULT HandsOff() throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="remarks"></a>コメント  
 `HandsOff`[CAtlTemporaryFile::HandsOn](#handson)オブジェクト、ファイルの関連付けを解除して、再接続し、必要な場合に使用されます。 `HandsOff`強制的に一時ファイルに書き込まれるファイル バッファーの残りの部分とし、ファイルを閉じます。 閉じて、ファイルを完全に削除するか、閉じる、名前が指定されたファイルの内容を保持して、使用する[CAtlTemporaryFile::Close](#close)します。  
  
##  <a name="a-namehandsona--catltemporaryfilehandson"></a><a name="handson"></a>CAtlTemporaryFile::HandsOn  
 既存の一時ファイルを開き、ファイルの末尾にカーソルを移動するには、このメソッドを呼び出します。  
  
```
HRESULT HandsOn() throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="remarks"></a>コメント  
 [CAtlTemporaryFile::HandsOff](#handsoff)と`HandsOn`オブジェクト、ファイルの関連付けを解除して、再接続し、必要な場合に使用されます。  
  
##  <a name="a-namelockrangea--catltemporaryfilelockrange"></a><a name="lockrange"></a>CAtlTemporaryFile::LockRange  
 その他のプロセスがアクセスできないようにする一時ファイル内の領域をロックするには、このメソッドを呼び出します。  
  
```
HRESULT LockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nPos`  
 ロックの開始位置を示すファイル内の位置。  
  
 `nCount`  
 ロックするバイト範囲の長さ。  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="remarks"></a>コメント  
 ファイル内のバイトをロックすると、他のプロセスがそれらのバイトにアクセスできなくなります。 ファイルの&1; つ以上の領域をロックすることができますが、重なり合う領域は使用できません。 領域を正常にロックを解除するには使用[CAtlTemporaryFile::UnlockRange](#unlockrange)、以前にロックされた領域に正確に一致バイトの範囲を確認します。 `LockRange`マージされず、隣接する領域です。2 つのロックされた領域が隣接している場合は、必要がありますロックを解除する各とは別にします。  
  
##  <a name="a-nameoperatorhandlea--catltemporaryfileoperator-handle"></a><a name="operator_handle"></a>CAtlTemporaryFile::operator ハンドル  
 一時ファイルにハンドルを返します。  
  
```  
operator HANDLE() throw();
```  
  
##  <a name="a-namereada--catltemporaryfileread"></a><a name="read"></a>CAtlTemporaryFile::Read  
 ファイル ポインターが指す位置以降にある一時ファイルからデータを読み取るには、このメソッドを呼び出します。  
  
```
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pBuffer`  
 ファイルから読み取られたデータを受け取るバッファーへのポインター。  
  
 `nBufSize`  
 バイト単位のバッファー サイズ。  
  
 `nBytesRead`  
 読み取られたバイト数。  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="remarks"></a>コメント  
 呼び出し[CAtlFile::Read](../../atl/reference/catlfile-class.md#read)します。 ファイル ポインターの位置を変更するには、呼び出す[CAtlTemporaryFile::Seek](#seek)します。  
  
### <a name="example"></a>例  
 例を参照してください[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)します。  
  
##  <a name="a-nameseeka--catltemporaryfileseek"></a><a name="seek"></a>CAtlTemporaryFile::Seek  
 一時ファイルのファイル ポインターを移動するには、このメソッドを呼び出します。  
  
```
HRESULT Seek(LONGLONG nOffset, DWORD dwFrom = FILE_CURRENT) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nOffset`  
 バイト単位で指定された開始位置からのオフセット*dwFrom します。*  
  
 `dwFrom`  
 (FILE_BEGIN、FILE_CURRENT、または FILE_END) の開始位置。  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="remarks"></a>コメント  
 呼び出し[CAtlFile::Seek](../../atl/reference/catlfile-class.md#seek)します。 現在のファイル ポインターの位置を取得するを呼び出す[CAtlTemporaryFile::GetPosition](#getposition)します。  
  
### <a name="example"></a>例  
 例を参照してください[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)します。  
  
##  <a name="a-namesetsizea--catltemporaryfilesetsize"></a><a name="setsize"></a>CAtlTemporaryFile::SetSize  
 一時ファイルのサイズを設定するには、このメソッドを呼び出します。  
  
```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nNewLen`  
 ファイルのバイトの新しい長さ。  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="remarks"></a>コメント  
 呼び出し[CAtlFile::SetSize](../../atl/reference/catlfile-class.md#setsize)します。 返された場合は、ファイル ポインターは、ファイルの末尾に配置されます。  
  
##  <a name="a-nametempfilenamea--catltemporaryfiletempfilename"></a><a name="tempfilename"></a>CAtlTemporaryFile::TempFileName  
 一時ファイルの名前を返すには、このメソッドを呼び出します。  
  
```
LPCTSTR TempFileName() throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します。、`LPCTSTR`ファイル名 をポイントします。  
  
### <a name="remarks"></a>コメント  
 ファイル名が生成される[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)への呼び出しで、 [GetTempFile](http://msdn.microsoft.com/library/windows/desktop/aa364991) [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]関数です。 ファイル拡張子には、一時ファイル用 tfr「と」常になります。  
  
##  <a name="a-nameunlockrangea--catltemporaryfileunlockrange"></a><a name="unlockrange"></a>CAtlTemporaryFile::UnlockRange  
 一時ファイルの領域のロックを解除するには、このメソッドを呼び出します。  
  
```
HRESULT UnlockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nPos`  
 ロックの解除を開始する位置を示すファイル内の位置。  
  
 `nCount`  
 ロックを解除するバイト範囲の長さ。  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="remarks"></a>コメント  
 呼び出し[CAtlFile::UnlockRange](../../atl/reference/catlfile-class.md#unlockrange)します。  
  
##  <a name="a-namewritea--catltemporaryfilewrite"></a><a name="write"></a>CAtlTemporaryFile::Write  
 ファイル ポインターが指す位置以降にある一時ファイルにデータを書き込むには、このメソッドを呼び出します。  
  
```
HRESULT Write(  
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pBuffer`  
 ファイルに書き込まれるデータを保持するバッファー。  
  
 `nBufSize`  
 バッファーからの転送バイト数。  
  
 `pnBytesWritten`  
 書き込むバイト数。  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="remarks"></a>コメント  
 呼び出し[CAtlFile::Write](../../atl/reference/catlfile-class.md#write)します。  
  
### <a name="example"></a>例  
 例を参照してください[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CAtlFile クラス](../../atl/reference/catlfile-class.md)

