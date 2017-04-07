---
title: "CMFCFilterChunkValueImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl::Clear
- AFXWIN/CMFCFilterChunkValueImpl::CopyChunk
- AFXWIN/CMFCFilterChunkValueImpl::CopyFrom
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkGUID
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkPID
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkType
- AFXWIN/CMFCFilterChunkValueImpl::GetString
- AFXWIN/CMFCFilterChunkValueImpl::GetValue
- AFXWIN/CMFCFilterChunkValueImpl::GetValueNoAlloc
- AFXWIN/CMFCFilterChunkValueImpl::IsValid
- AFXWIN/CMFCFilterChunkValueImpl::SetBoolValue
- AFXWIN/CMFCFilterChunkValueImpl::SetDwordValue
- AFXWIN/CMFCFilterChunkValueImpl::SetFileTimeValue
- AFXWIN/CMFCFilterChunkValueImpl::SetInt64Value
- AFXWIN/CMFCFilterChunkValueImpl::SetIntValue
- AFXWIN/CMFCFilterChunkValueImpl::SetLongValue
- AFXWIN/CMFCFilterChunkValueImpl::SetSystemTimeValue
- AFXWIN/CMFCFilterChunkValueImpl::SetTextValue
- AFXWIN/CMFCFilterChunkValueImpl::SetChunk
dev_langs:
- C++
helpviewer_keywords:
- CMFCFilterChunkValueImpl class
ms.assetid: 3c833f23-5b88-4d08-9e09-ca6a8aec88bf
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
ms.openlocfilehash: 8de3cba19a60b8022df96a9edafd13677fa3fecb
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcfilterchunkvalueimpl-class"></a>CMFCFilterChunkValueImpl クラス
これは、チャンクとプロパティ値のペアのロジックを単純化するクラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCFilterChunkValueImpl : public ATL::IFilterChunkValue;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl:: ~ CMFCFilterChunkValueImpl](#_dtorcmfcfilterchunkvalueimpl)|オブジェクトを破棄します。|  
|[CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl](#cmfcfilterchunkvalueimpl)|オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl::Clear](#clear)|ChunkValue をクリアします。|  
|[CMFCFilterChunkValueImpl::CopyChunk](#copychunk)|このチャンクをチャンクの特性を記述する構造体にコピーします。|  
|[CMFCFilterChunkValueImpl::CopyFrom](#copyfrom)|その他の値からこのチャンク値を初期化します。|  
|[CMFCFilterChunkValueImpl::GetChunkGUID](#getchunkguid)|GUID のチャンクを取得します。|  
|[CMFCFilterChunkValueImpl::GetChunkPID](#getchunkpid)|チャンクの PID (プロパティ ID) を取得します。|  
|[CMFCFilterChunkValueImpl::GetChunkType](#getchunktype)|チャンクの種類を取得します。|  
|[CMFCFilterChunkValueImpl::GetString](#getstring)|取得、文字列値。|  
|[CMFCFilterChunkValueImpl::GetValue](#getvalue)|割り当てられた propvariant として値を取得します。|  
|[CMFCFilterChunkValueImpl::GetValueNoAlloc](#getvaluenoalloc)|割り当てられた以外を返します (内部値) の値です。|  
|[CMFCFilterChunkValueImpl::IsValid](#isvalid)|このプロパティの値が有効であるかどうかどうかをチェックします。|  
|[CMFCFilterChunkValueImpl::SetBoolValue](#setboolvalue)|オーバーロードされます。 ブール値をキー プロパティを設定します。|  
|[CMFCFilterChunkValueImpl::SetDwordValue](#setdwordvalue)|DWORD へのキー プロパティを設定します。|  
|[CMFCFilterChunkValueImpl::SetFileTimeValue](#setfiletimevalue)|Filetime のキー プロパティを設定します。|  
|[CMFCFilterChunkValueImpl::SetInt64Value](#setint64value)|キーは int64 にプロパティを設定します。|  
|[CMFCFilterChunkValueImpl::SetIntValue](#setintvalue)|Int へのキー プロパティを設定します。|  
|[CMFCFilterChunkValueImpl::SetLongValue](#setlongvalue)|キー長整数型にプロパティを設定します。|  
|[CMFCFilterChunkValueImpl::SetSystemTimeValue](#setsystemtimevalue)|SystemTime にキー プロパティを設定します。|  
|[CMFCFilterChunkValueImpl::SetTextValue](#settextvalue)|Unicode 文字列にキー プロパティを設定します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl::SetChunk](#setchunk)|チャンクの共通プロパティを設定するヘルパー関数。|  
  
## <a name="remarks"></a>コメント  
 正しい種類の CMFCFilterChunkValueImpl クラスの作成だけで使用するには  
  
 例:  
  
 CMFCFilterChunkValueImpl チャンクです。  
  
 hr = チャンクです。SetBoolValue(PKEY_IsAttachment, true) です。  
  
 または  
  
 hr = チャンクです。SetFileTimeValue (PKEY_ItemDate、ftLastModified) です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ATL::IFilterChunkValue`  
  
 [CMFCFilterChunkValueImpl](../../mfc/reference/cmfcfilterchunkvalueimpl-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="clear"></a>CMFCFilterChunkValueImpl::Clear  
 ChunkValue をクリアします。  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="cmfcfilterchunkvalueimpl"></a>CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl  
 オブジェクトを構築します。  
  
```  
CMFCFilterChunkValueImpl();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="_dtorcmfcfilterchunkvalueimpl"></a>CMFCFilterChunkValueImpl:: ~ CMFCFilterChunkValueImpl  
 オブジェクトを破棄します。  
  
```  
virtual ~CMFCFilterChunkValueImpl();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="copychunk"></a>CMFCFilterChunkValueImpl::CopyChunk  
 このチャンクをチャンクの特性を記述する構造体にコピーします。  
  
```  
HRESULT CopyChunk(STAT_CHUNK* pStatChunk);
```  
  
### <a name="parameters"></a>パラメーター  
 `pStatChunk`  
 チャンクの特性を記述する対象値へのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は S_OKそれ以外の場合はエラー コード。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="copyfrom"></a>CMFCFilterChunkValueImpl::CopyFrom  
 その他の値からこのチャンク値を初期化します。  
  
```  
void CopyFrom (IFilterChunkValue* pValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `pValue`  
 コピーするソース値を指定します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getchunkguid"></a>CMFCFilterChunkValueImpl::GetChunkGUID  
 GUID のチャンクを取得します。  
  
```  
REFGUID GetChunkGUID() const;  
```  
  
### <a name="return-value"></a>戻り値  
 チャンクを識別する GUID への参照。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getchunkpid"></a>CMFCFilterChunkValueImpl::GetChunkPID  
 チャンクの PID (プロパティ ID) を取得します。  
  
```  
DWORD GetChunkPID() const;  
```  
  
### <a name="return-value"></a>戻り値  
 プロパティ ID を含む DWORD 値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getchunktype"></a>CMFCFilterChunkValueImpl::GetChunkType  
 チャンクの種類を取得します。  
  
```  
CHUNKSTATE GetChunkType() const;  
```  
  
### <a name="return-value"></a>戻り値  
 CHUNKSTATE 列挙値、現在のチャンクが、テキスト型のプロパティまたは値型のプロパティかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getstring"></a>CMFCFilterChunkValueImpl::GetString  
 文字列値を取得します。  
  
```  
CString &GetString();
```  
  
### <a name="return-value"></a>戻り値  
 チャンク値を含む文字列。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getvalue"></a>CMFCFilterChunkValueImpl::GetValue  
 割り当てられた propvariant として値を取得します。  
  
```  
HRESULT GetValue(PROPVARIANT** ppPropVariant);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppPropVariant`  
 関数から制御が戻るとき、このパラメーターには、チャンク値が含まれています。  
  
### <a name="return-value"></a>戻り値  
 PROPVARIANT が正常に割り当てられているし、チャンク値に正常にコピーされた場合は S_OK`ppPropVariant`以外の場合はエラー コード。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getvaluenoalloc"></a>CMFCFilterChunkValueImpl::GetValueNoAlloc  
 未割り当て (内部値) の値を返します。  
  
```  
PROPVARIANT GetValueNoAlloc ();
```  
  
### <a name="return-value"></a>戻り値  
 現在のチャンク値を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isvalid"></a>CMFCFilterChunkValueImpl::IsValid  
 このプロパティの値が有効であるかどうかどうかをチェックします。  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`現在のチャンク値が無効である場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setboolvalue"></a>CMFCFilterChunkValueImpl::SetBoolValue  
 オーバーロードされます。 ブール値をキー プロパティを設定します。  
  
```  
HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,  
    BOOL bVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);

 
HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,  
    VARIANT_BOOL bVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>パラメーター  
 `pkey`  
 プロパティのキーを指定します。  
  
 `bVal`  
 設定するチャンク値を指定します。  
  
 `chunkType`  
 フラグは、このチャンクが text 型または値型のプロパティを含めるかどうかを指定します。 フラグの値は、CHUNKSTATE 列挙から取得されます。  
  
 `locale`  
 言語とサブ言語のテキストのチャンクに関連付けられています。 ドキュメントのインデクサーはチャンクのロケールを使用して、適切な単語がテキストの分割を実行できます。 1 つのチャンクが text 型でも VT_LPWSTR、VT_LPSTR、または VT_BSTR のデータ型を持つ値型の場合は、このフィールドは無視されます。  
  
 `cwcLenSource`  
 現在のチャンクの派生元のソース テキストの文字数。 値が&0; では、ソース テキストと派生のテキスト文字の対応を示します。 0 以外の値は、このような直接的な対応関係が存在しないことを意味します。  
  
 `cwcStartSource`  
 派生のチャンクをソース テキストのソースのチャンクで起動元のオフセット。  
  
 `chunkBreakType`  
 前のチャンクでは、現在のチャンクから分離した中断の種類。 値は CHUNK_BREAKTYPE 列挙体です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は S_OKそれ以外の場合はエラー コード。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setchunk"></a>CMFCFilterChunkValueImpl::SetChunk  
 チャンクの共通プロパティを設定するヘルパー関数。  
  
```  
HRESULT SetChunk(
    REFPROPERTYKEY pkey,  
    CHUNKSTATE chunkType=CHUNK_VALUE,  
    LCID locale=0,  
    DWORD cwcLenSource=0,  
    DWORD cwcStartSource=0,  
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>パラメーター  
 `pkey`  
 プロパティのキーを指定します。  
  
 `chunkType`  
 フラグは、このチャンクが text 型または値型のプロパティを含めるかどうかを指定します。 フラグの値は、CHUNKSTATE 列挙から取得されます。  
  
 `locale`  
 言語とサブ言語のテキストのチャンクに関連付けられています。 ドキュメントのインデクサーはチャンクのロケールを使用して、適切な単語がテキストの分割を実行できます。 1 つのチャンクが text 型でも VT_LPWSTR、VT_LPSTR、または VT_BSTR のデータ型を持つ値型の場合は、このフィールドは無視されます。  
  
 `cwcLenSource`  
 現在のチャンクの派生元のソース テキストの文字数。 値が&0; では、ソース テキストと派生のテキスト文字の対応を示します。 0 以外の値は、このような直接的な対応関係が存在しないことを意味します。  
  
 `cwcStartSource`  
 派生のチャンクをソース テキストのソースのチャンクで起動元のオフセット。  
  
 `chunkBreakType`  
 前のチャンクでは、現在のチャンクから分離した中断の種類。 値は CHUNK_BREAKTYPE 列挙体です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は S_OKそれ以外の場合のエラー コードです。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setdwordvalue"></a>CMFCFilterChunkValueImpl::SetDwordValue  
 DWORD へのキーのプロパティを設定します。  
  
```  
HRESULT SetDwordValue(
    REFPROPERTYKEY pkey,  
    DWORD dwVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>パラメーター  
 `pkey`  
 プロパティのキーを指定します。  
  
 `dwVal`  
 設定するチャンク値を指定します。  
  
 `chunkType`  
 フラグは、このチャンクが text 型または値型のプロパティを含めるかどうかを指定します。 フラグの値は、CHUNKSTATE 列挙から取得されます。  
  
 `locale`  
 言語とサブ言語のテキストのチャンクに関連付けられています。 ドキュメントのインデクサーはチャンクのロケールを使用して、適切な単語がテキストの分割を実行できます。 1 つのチャンクが text 型でも VT_LPWSTR、VT_LPSTR、または VT_BSTR のデータ型を持つ値型の場合は、このフィールドは無視されます。  
  
 `cwcLenSource`  
 現在のチャンクの派生元のソース テキストの文字数。 値が&0; では、ソース テキストと派生のテキスト文字の対応を示します。 0 以外の値は、このような直接的な対応関係が存在しないことを意味します。  
  
 `cwcStartSource`  
 派生のチャンクをソース テキストのソースのチャンクで起動元のオフセット。  
  
 `chunkBreakType`  
 前のチャンクでは、現在のチャンクから分離した中断の種類。 値は CHUNK_BREAKTYPE 列挙体です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は S_OKそれ以外の場合はエラー コード。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setfiletimevalue"></a>CMFCFilterChunkValueImpl::SetFileTimeValue  
 キー、filetime にプロパティを設定します。  
  
```  
HRESULT SetFileTimeValue(
    REFPROPERTYKEY pkey,  
    FILETIME dtVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>パラメーター  
 `pkey`  
 プロパティのキーを指定します。  
  
 `dtVal`  
 設定するチャンク値を指定します。  
  
 `chunkType`  
 フラグは、このチャンクが text 型または値型のプロパティを含めるかどうかを指定します。 フラグの値は、CHUNKSTATE 列挙から取得されます。  
  
 `locale`  
 言語とサブ言語のテキストのチャンクに関連付けられています。 ドキュメントのインデクサーはチャンクのロケールを使用して、適切な単語がテキストの分割を実行できます。 1 つのチャンクが text 型でも VT_LPWSTR、VT_LPSTR、または VT_BSTR のデータ型を持つ値型の場合は、このフィールドは無視されます。  
  
 `cwcLenSource`  
 現在のチャンクの派生元のソース テキストの文字数。 値が&0; では、ソース テキストと派生のテキスト文字の対応を示します。 0 以外の値は、このような直接的な対応関係が存在しないことを意味します。  
  
 `cwcStartSource`  
 派生のチャンクをソース テキストのソースのチャンクで起動元のオフセット。  
  
 `chunkBreakType`  
 前のチャンクでは、現在のチャンクから分離した中断の種類。 値は CHUNK_BREAKTYPE 列挙体です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は S_OKそれ以外の場合はエラー コード。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setint64value"></a>CMFCFilterChunkValueImpl::SetInt64Value  
 キーは int64 にプロパティを設定します。  
  
```  
HRESULT SetInt64Value(
    REFPROPERTYKEY pkey,  
    __int64 nVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>パラメーター  
 `pkey`  
 プロパティのキーを指定します。  
  
 `nVal`  
 設定するチャンク値を指定します。  
  
 `chunkType`  
 フラグは、このチャンクが text 型または値型のプロパティを含めるかどうかを指定します。 フラグの値は、CHUNKSTATE 列挙から取得されます。  
  
 `locale`  
 言語とサブ言語のテキストのチャンクに関連付けられています。 ドキュメントのインデクサーはチャンクのロケールを使用して、適切な単語がテキストの分割を実行できます。 1 つのチャンクが text 型でも VT_LPWSTR、VT_LPSTR、または VT_BSTR のデータ型を持つ値型の場合は、このフィールドは無視されます。  
  
 `cwcLenSource`  
 現在のチャンクの派生元のソース テキストの文字数。 値が&0; では、ソース テキストと派生のテキスト文字の対応を示します。 0 以外の値は、このような直接的な対応関係が存在しないことを意味します。  
  
 `cwcStartSource`  
 派生のチャンクをソース テキストのソースのチャンクで起動元のオフセット。  
  
 `chunkBreakType`  
 前のチャンクでは、現在のチャンクから分離した中断の種類。 値は CHUNK_BREAKTYPE 列挙体です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は S_OKそれ以外の場合はエラー コード。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setintvalue"></a>CMFCFilterChunkValueImpl::SetIntValue  
 キーに int プロパティを設定します。  
  
```  
HRESULT SetIntValue(
    REFPROPERTYKEY pkey,  
    int nVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>パラメーター  
 `pkey`  
 プロパティのキーを指定します。  
  
 `nVal`  
 設定するチャンク値を指定します。  
  
 `chunkType`  
 フラグは、このチャンクが text 型または値型のプロパティを含めるかどうかを指定します。 フラグの値は、CHUNKSTATE 列挙から取得されます。  
  
 `locale`  
 言語とサブ言語のテキストのチャンクに関連付けられています。 ドキュメントのインデクサーはチャンクのロケールを使用して、適切な単語がテキストの分割を実行できます。 1 つのチャンクが text 型でも VT_LPWSTR、VT_LPSTR、または VT_BSTR のデータ型を持つ値型の場合は、このフィールドは無視されます。  
  
 `cwcLenSource`  
 現在のチャンクの派生元のソース テキストの文字数。 値が&0; では、ソース テキストと派生のテキスト文字の対応を示します。 0 以外の値は、このような直接的な対応関係が存在しないことを意味します。  
  
 `cwcStartSource`  
 派生のチャンクをソース テキストのソースのチャンクで起動元のオフセット。  
  
 `chunkBreakType`  
 前のチャンクでは、現在のチャンクから分離した中断の種類。 値は CHUNK_BREAKTYPE 列挙体です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は S_OKそれ以外の場合はエラー コード。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setlongvalue"></a>CMFCFilterChunkValueImpl::SetLongValue  
 キー長整数型にプロパティを設定します。  
  
```  
HRESULT SetLongValue(
    REFPROPERTYKEY pkey,  
    long lVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>パラメーター  
 `pkey`  
 プロパティのキーを指定します。  
  
 `lVal`  
 設定するチャンク値を指定します。  
  
 `chunkType`  
 フラグは、このチャンクが text 型または値型のプロパティを含めるかどうかを指定します。 フラグの値は、CHUNKSTATE 列挙から取得されます。  
  
 `locale`  
 言語とサブ言語のテキストのチャンクに関連付けられています。 ドキュメントのインデクサーはチャンクのロケールを使用して、適切な単語がテキストの分割を実行できます。 1 つのチャンクが text 型でも VT_LPWSTR、VT_LPSTR、または VT_BSTR のデータ型を持つ値型の場合は、このフィールドは無視されます。  
  
 `cwcLenSource`  
 現在のチャンクの派生元のソース テキストの文字数。 値が&0; では、ソース テキストと派生のテキスト文字の対応を示します。 0 以外の値は、このような直接的な対応関係が存在しないことを意味します。  
  
 `cwcStartSource`  
 派生のチャンクをソース テキストのソースのチャンクで起動元のオフセット。  
  
 `chunkBreakType`  
 前のチャンクでは、現在のチャンクから分離した中断の種類。 値は CHUNK_BREAKTYPE 列挙体です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は S_OKそれ以外の場合はエラー コード。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setsystemtimevalue"></a>CMFCFilterChunkValueImpl::SetSystemTimeValue  
 SystemTime にキー プロパティを設定します。  
  
```  
HRESULT SetSystemTimeValue(
    REFPROPERTYKEY pkey,  
    const SYSTEMTIME& systemTime,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale=0,  
    DWORD cwcLenSource=0,  
    DWORD cwcStartSource=0,  
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>パラメーター  
 `pkey`  
 プロパティのキーを指定します。  
  
 `systemTime`  
 設定するチャンク値を指定します。  
  
 `chunkType`  
 フラグは、このチャンクが text 型または値型のプロパティを含めるかどうかを指定します。 フラグの値は、CHUNKSTATE 列挙から取得されます。  
  
 `locale`  
 言語とサブ言語のテキストのチャンクに関連付けられています。 ドキュメントのインデクサーはチャンクのロケールを使用して、適切な単語がテキストの分割を実行できます。 1 つのチャンクが text 型でも VT_LPWSTR、VT_LPSTR、または VT_BSTR のデータ型を持つ値型の場合は、このフィールドは無視されます。  
  
 `cwcLenSource`  
 現在のチャンクの派生元のソース テキストの文字数。 値が&0; では、ソース テキストと派生のテキスト文字の対応を示します。 0 以外の値は、このような直接的な対応関係が存在しないことを意味します。  
  
 `cwcStartSource`  
 派生のチャンクをソース テキストのソースのチャンクで起動元のオフセット。  
  
 `chunkBreakType`  
 前のチャンクでは、現在のチャンクから分離した中断の種類。 値は CHUNK_BREAKTYPE 列挙体です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は S_OKそれ以外の場合はエラー コード。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="settextvalue"></a>CMFCFilterChunkValueImpl::SetTextValue  
 Unicode 文字列にキー プロパティを設定します。  
  
```  
HRESULT SetTextValue(
    REFPROPERTYKEY pkey,  
    LPCTSTR pszValue,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>パラメーター  
 `pkey`  
 プロパティのキーを指定します。  
  
 `pszValue`  
 設定するチャンク値を指定します。  
  
 `chunkType`  
 フラグは、このチャンクが text 型または値型のプロパティを含めるかどうかを指定します。 フラグの値は、CHUNKSTATE 列挙から取得されます。  
  
 `locale`  
 言語とサブ言語のテキストのチャンクに関連付けられています。 ドキュメントのインデクサーはチャンクのロケールを使用して、適切な単語がテキストの分割を実行できます。 1 つのチャンクが text 型でも VT_LPWSTR、VT_LPSTR、または VT_BSTR のデータ型を持つ値型の場合は、このフィールドは無視されます。  
  
 `cwcLenSource`  
 現在のチャンクの派生元のソース テキストの文字数。 値が&0; では、ソース テキストと派生のテキスト文字の対応を示します。 0 以外の値は、このような直接的な対応関係が存在しないことを意味します。  
  
 `cwcStartSource`  
 派生のチャンクをソース テキストのソースのチャンクで起動元のオフセット。  
  
 `chunkBreakType`  
 前のチャンクでは、現在のチャンクから分離した中断の種類。 値は CHUNK_BREAKTYPE 列挙体です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は S_OKそれ以外の場合はエラー コード。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

