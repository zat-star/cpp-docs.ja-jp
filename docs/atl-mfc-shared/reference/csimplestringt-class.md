---
title: "CSimpleStringT クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CSimpleStringT
- ATL::CSimpleStringT
- ATL::CSimpleStringT<BaseType>
- ATL.CSimpleStringT<BaseType>
- CSimpleStringT
dev_langs:
- C++
helpviewer_keywords:
- shared classes, CSimpleStringT
- strings [C++], ATL class
- CSimpleStringT class
ms.assetid: 15814fcb-5b8f-4425-a97e-3b61fc9b48d8
caps.latest.revision: 17
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
ms.sourcegitcommit: 1a00023e4d3e31ddb6381e90a50231449b1de18d
ms.openlocfilehash: e273aff69b9c8dbea4fb829798b2e9d58351b9dd
ms.lasthandoff: 02/28/2017

---
# <a name="csimplestringt-class"></a>CSimpleStringT クラス
このクラスを表します。、`CSimpleStringT`オブジェクトです。  
  
## <a name="syntax"></a>構文  
  
```
template <typename BaseType>
class CSimpleStringT
```  
  
### <a name="parameters"></a>パラメーター  
 `BaseType`  
 String クラスの文字型。 次のいずれかの値を指定します。  
  
- `char`(ANSI 文字列を)。  
  
- `wchar_t`(Unicode 文字列を)。  
  
- **TCHAR** (の ANSI および Unicode 文字列)。  

## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleStringT::PCXSTR](#pcxstr)|定数文字列へのポインター。|  
|[CSimpleStringT::PXSTR](#pxstr)|文字列へのポインター。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleStringT::CSimpleStringT](#ctor)|構築`CSimpleStringT`さまざまな方法でオブジェクトです。|  
|[CSimpleStringT:: ~ CSimpleStringT](#dtor)|デストラクターです。|  

  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleStringT::Append](#append)|追加、`CSimpleStringT`を既存のオブジェクト`CSimpleStringT`オブジェクトです。|  
|[CSimpleStringT::AppendChar](#appendchar)|文字を追加すると、既存`CSimpleStringT`オブジェクトです。|  
|[CSimpleStringT::CopyChars](#copychars)|文字または文字を別の文字列にコピーします。|  
|[CSimpleStringT::CopyCharsOverlapped](#copycharsoverlapped)|バッファーが重複して別の文字列に文字または文字をコピーします。|  
|[CSimpleStringT::Empty](#empty)|文字列の長さがゼロにします。|  
|[CSimpleStringT::FreeExtra](#freeextra)|文字列オブジェクトに割り当てられているすべての余分なメモリを解放します。|  
|[CSimpleStringT::GetAllocLength](#getalloclength)|割り当て済みの長さを取得、`CSimpleStringT`オブジェクトです。|  
|[CSimpleStringT::GetAt](#getat)|指定された位置に文字を返します。|  
|[CSimpleStringT::GetBuffer](#getbuffer)|ポインターの文字を返し、`CSimpleStringT`です。|  
|[CSimpleStringT::GetBufferSetLength](#getbuffersetlength)|ポインターで文字を返し、 `CSimpleStringT`、指定の長さに切り捨てです。|  
|[CSimpleStringT::GetLength](#getlength)|文字数を返す、`CSimpleStringT`オブジェクトです。|  
|[CSimpleStringT::GetManager](#getmanager)|メモリ マネージャーの取得、`CSimpleStringT`オブジェクトです。|  
|[CSimpleStringT::GetString](#getstring)|文字の文字列を取得します。|  
|[CSimpleStringT::IsEmpty](#isempty)|テストするかどうか、`CSimpleStringT`オブジェクトには文字は含まれません。|  
|[CSimpleStringT::LockBuffer](#lockbuffer)|参照カウントを無効にし、バッファー内の文字列を保護します。|  
|[CSimpleStringT::Preallocate](#preallocate)|文字バッファーを特定の量のメモリを割り当てます。|  
|[CSimpleStringT::ReleaseBuffer](#releasebuffer)|によって返されたバッファーの制御を`GetBuffer`します。|  
|[CSimpleStringT::ReleaseBufferSetLength](#releasebuffersetlength)|によって返されたバッファーの制御を`GetBuffer`します。|  
|[CSimpleStringT::SetAt](#setat)|指定された位置に文字を設定します。|  
|[CSimpleStringT::SetManager](#setmanager)|メモリ マネージャーの設定、`CSimpleStringT`オブジェクトです。|  
|[CSimpleStringT::SetString](#setstring)|文字列を設定、`CSimpleStringT`オブジェクトです。|  
|[CSimpleStringT::StringLength](#stringlength)|指定した文字列内の文字数を返します。|  
|[CSimpleStringT::Truncate](#truncate)|指定された長さに文字列を切り捨てます。|  
|[CSimpleStringT::UnlockBuffer](#unlockbuffer)|参照カウントを使用し、バッファー内の文字列を解放します。|  

### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleStringT::operator PCXSTR](#operator_pcxstr)|格納される文字に直接アクセスする、`CSimpleStringT`オブジェクトを C スタイルの文字列として。|  
|[CSimpleStringT::operator\[\]](#operator_at)|指定された位置に文字を返します: 演算子の代替の`GetAt`です。|  
|[CSimpleStringT::operator + = 演算子](#operator_add_eq)|既存の文字列の末尾に新しい文字列を連結します。|  
|[CSimpleStringT::operator =](#operator_eq)|新しい値を代入する`CSimpleStringT`オブジェクトです。|  
  
### <a name="remarks"></a>コメント  
 `CSimpleStringT`Visual C でサポートされているさまざまな文字列クラスの基本クラスです。 基本的なバッファー操作、文字列オブジェクトのメモリ管理のための最小限のサポートを提供します。 高度な文字列オブジェクトを参照してください。 [CStringT クラス](../../atl-mfc-shared/reference/cstringt-class.md)します。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlsimpstr.h  


## <a name="a-nameappenda-csimplestringtappend"></a><a name="append"></a>CSimpleStringT::Append
追加、`CSimpleStringT`を既存のオブジェクト`CSimpleStringT`オブジェクトです。  
  
### <a name="syntax"></a>構文  
  
```  
void Append(const CSimpleStringT& strSrc); 
void Append(PCXSTR pszSrc, int nLength); 
void Append(PCXSTR pszSrc);
```  
#### <a name="parameters"></a>パラメーター  
 `strSrc`  
 `CSimpleStringT`追加するオブジェクト。  
  
 `pszSrc`  
 追加する文字を含む文字列へのポインター。  
  
 `nLength`  
 追加する文字数。  
  
### <a name="remarks"></a>コメント  
 既存を追加するには、このメソッドを呼び出す`CSimpleStringT`オブジェクト間`CSimpleStringT`オブジェクトです。  
  
### <a name="example"></a>例  
 次の例は、`CSimpleStringT::Append` の使い方を示しています。  
  
```cpp  
CSimpleString str1(pMgr), str2(pMgr);
str1.SetString(_T("Soccer is"));
str2.SetString(_T(" an elegant game"));
str1.Append(str2);
ASSERT(_tcscmp(str1, _T("Soccer is an elegant game")) == 0);
```
  
##  <a name="a-nameappendchara-csimplestringtappendchar"></a><a name="appendchar"></a>CSimpleStringT::AppendChar
文字を追加すると、既存`CSimpleStringT`オブジェクトです。  
  
### <a name="syntax"></a>構文  
  
```  
void AppendChar(XCHAR ch);
```  
#### <a name="parameters"></a>パラメーター  
 *ch*  
 追加される文字  
  
### <a name="remarks"></a>コメント  
 指定した文字を既存の末尾に追加するには、この関数を呼び出す`CSimpleStringT`オブジェクトです。  
  
##  <a name="a-namecopycharsa-csimplestringtcopychars"></a><a name="copychars"></a>CSimpleStringT::CopyChars  
 文字または文字のコピー、`CSimpleStringT`オブジェクトです。  
  
### <a name="syntax"></a>構文  
  
```  
static void CopyChars(
  XCHAR* pchDest,
  const XCHAR* pchSrc, 
  int nChars) throw();
```  
#### <a name="parameters"></a>パラメーター  
 `pchDest`  
 文字の文字列へのポインター。  
  
 `pchSrc`  
 コピーする文字を含む文字列へのポインター。  
  
 `nChars`  
 数`pchSrc`コピーする文字。  
  
### <a name="remarks"></a>コメント  
 文字をコピーするには、このメソッドを呼び出す`pchSrc`に、`pchDest`文字列。  
  
### <a name="example"></a>例  
 次の例は、`CSimpleStringT::CopyChars` の使い方を示しています。  
  
```cpp  
CSimpleString str(_T("xxxxxxxxxxxxxxxxxxx"), 20, pMgr);
TCHAR* pszSrc = _T("Hello world!");
_tprintf_s(_T("%s\n"), str);
str.CopyChars(str.GetBuffer(), pszSrc, 12);
_tprintf_s(_T("%s\n"), str);
```
  
##  <a name="a-namecopycharsoverlappeda--csimplestringtcopycharsoverlapped"></a><a name="copycharsoverlapped"></a>CSimpleStringT::CopyCharsOverlapped
文字または文字のコピー、`CSimpleStringT`オブジェクトです。  
  
### <a name="syntax"></a>構文  
  
```  
static void CopyCharsOverlapped(
  XCHAR* pchDest,
  const XCHAR* pchSrc,
  int nChars) throw(); 
```  
#### <a name="parameters"></a>パラメーター  
 `pchDest`  
 文字の文字列へのポインター。  
  
 `pchSrc`  
 コピーする文字を含む文字列へのポインター。  
  
 `nChars`  
 数`pchSrc`コピーする文字。  
  
### <a name="remarks"></a>コメント  
 文字をコピーするには、このメソッドを呼び出す`pchSrc`に、`pchDest`文字列。 異なり`CopyChars`、`CopyCharsOverlapped`が重なる可能性がある文字バッファーからコピーするための安全な方法を提供します。  
  
### <a name="example"></a>例  
 例を参照してください[CSimpleStringT::CopyChars](#copychars)、またはソース コードを`CSimpleStringT::SetString`(atlsimpstr.h にあります)。  
  
##  <a name="a-namectora--csimplestringtcsimplestringt"></a><a name="ctor"></a>CSimpleStringT::CSimpleStringT  
 `CSimpleStringT` オブジェクトを構築します。  
  
### <a name="syntax"></a>構文  
  
```  
CSimpleStringT(const XCHAR* pchSrc, int nLength, IAtlStringMgr* pStringMgr); 
CSimpleStringT(PCXSTR pszSrc, IAtlStringMgr* pStringMgr); 
CSimpleStringT(const CSimpleStringT& strSrc); 
explicit CSimpleStringT(IAtlStringMgr* pStringMgr) throw(); 
```  
#### <a name="parameters"></a>パラメーター  
 `strSrc`  
 既存の`CSimpleStringT`オブジェクトにコピーされる`CSimpleStringT`オブジェクトです。  
  
 `pchSrc`  
 長さの文字の配列へのポインター `nLength`、null 終端ではありません。  
  
 `pszSrc`  
 これにコピーされる null で終わる文字列`CSimpleStringT`オブジェクトです。  
  
 `nLength`  
 内の文字の数のカウント`pch`します。  
  
 `pStringMgr`  
 メモリ マネージャーへのポインター、`CSimpleStringT`オブジェクトです。 詳細については`IAtlStringMgr`とメモリ管理を`CSimpleStringT`を参照してください[メモリ管理と CStringT](../memory-management-with-cstringt.md)します。  
  
### <a name="remarks"></a>コメント  
 新しい `CSimpleStringT` オブジェクトを構築します。 コンス トラクターは、入力データを新しい割り当て済み記憶域にコピー、するために、メモリ不足例外があります。  
  
### <a name="example"></a>例  
 次の例では、使用`CSimpleStringT::CSimpleStringT`ATL を使用して、 `typedef` `CSimpleString`します。 `CSimpleString`一般的に使用される、クラス テンプレートの特殊`CSimpleStringT`します。  
  
```cpp  
CSimpleString s1(pMgr);
// Empty string
CSimpleString s2(_T("cat"), pMgr);
// From a C string literal

CSimpleString s3(s2);
// Copy constructor
CSimpleString s4(s2 + _T(" ") + s3);

// From a string expression
CSimpleString s5(_T("xxxxxx"), 6, pMgr);
// s5 = "xxxxxx"   
```

  
##  <a name="a-nameemptya--csimplestringtempty"></a><a name="empty"></a>CSimpleStringT::Empty
これにより、`CSimpleStringT`オブジェクトの空の文字列と、必要に応じてメモリを解放します。  
  
### <a name="syntax"></a>構文  
  
```  
void Empty() throw();  
```  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[文字列: CString の例外の後処理](../cstring-exception-cleanup.md)します。  
  
### <a name="example"></a>例  
 次の例は、`CSimpleStringT::Empty` の使い方を示しています。  
  
```cpp  
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());  
```  
  
##  <a name="a-namefreeextraa--csimplestringtfreeextra"></a><a name="freeextra"></a>CSimpleStringT::FreeExtra
文字列に割り当てられているが、不要になったすべての余分なメモリを解放します。  
  
### <a name="syntax"></a>構文  
  
```  
void FreeExtra(); 
```  
### <a name="remarks"></a>コメント  
 文字列オブジェクトによって使用されたメモリのオーバーヘッドが減ります。 メソッドによって返される正確な長さのバッファーを再割り当て[GetLength](#getlength)します。  
  
### <a name="example"></a>例  
```cpp  
CAtlString basestr;
IAtlStringMgr* pMgr;

pMgr= basestr.GetManager();
ASSERT(pMgr != NULL);

// Create a CSimpleString with 28 characters
CSimpleString str(_T("Many sports are fun to play."), 28, pMgr);
_tprintf_s(_T("Alloc length is %d, String length is %d\n"),
   str.GetAllocLength(), str.GetLength());

// Assigning a smaller string won't cause CSimpleString to free its 
// memory, because it assumes the string will grow again anyway.
str = _T("Soccer is best!");
_tprintf_s(_T("Alloc length is %d, String length is %d\n"),
   str.GetAllocLength(), str.GetLength());

// This call forces CSimpleString to release the extra 
// memory it doesn't need.
str.FreeExtra();
_tprintf_s(_T("Alloc length is %d, String length is %d\n"),
   str.GetAllocLength(), str.GetLength());
```
  
### <a name="remarks"></a>コメント  
 この例の出力は次のとおりです。  
  
 `Alloc length is 1031, String length is 1024`  
  
 `Alloc length is 1031, String length is 15`  
  
 `Alloc length is 15, String length is 15`  
  
##  <a name="a-namegetalloclengtha--csimplestringtgetalloclength"></a><a name="getalloclength"></a>CSimpleStringT::GetAllocLength  
割り当て済みの長さを取得、`CSimpleStringT`オブジェクトです。  
  
### <a name="syntax"></a>構文  
  
```  
int GetAllocLength() const throw();  
```  
### <a name="return-value"></a>戻り値  
 このオブジェクトに割り当てられている文字数。  
  
### <a name="remarks"></a>コメント  
 これに割り当てられた文字の数を確認するには、このメソッドを呼び出す`CSimpleStringT`オブジェクトです。 参照してください[FreeExtra](#freeextra)この関数の呼び出しの例です。  
  
##  <a name="a-namegetata--csimplestringtgetat"></a><a name="getat"></a>CSimpleStringT::GetAt  
1 つの文字を返す、`CSimpleStringT`オブジェクトです。  
  
### <a name="syntax"></a>構文  
  
```  
XCHAR GetAt(int iChar) const;
```  
#### <a name="parameters"></a>パラメーター  
 `iChar`  
 内の文字の&0; から始まるインデックス、`CSimpleStringT`オブジェクトです。 `iChar`パラメーターが 0 より大きいで、かつによって返される値より小さくする必要があります[GetLength](#getlength)します。 それ以外の場合、`GetAt`例外が発生します。  
  
### <a name="return-value"></a>戻り値  
 `XCHAR`文字列の指定した位置にある文字を含めることです。  
  
### <a name="remarks"></a>コメント  
 指定された&1; つの文字を返すには、このメソッドを呼び出す`iChar`します。 オーバー ロードされた添字 (`[]`) 演算子は、便利なエイリアスの`GetAt`です。 使用して例外を生成せず、null の終端記号はアドレス指定可能な`GetAt`です。 ただし、これはカウントされないによって`GetLength`、返される値は 0 です。  
  
### <a name="example"></a>例  
 次の例では、使用して`CSimpleStringT::GetAt`します。  
  
```cpp  
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(s.GetAt(2) == _T('c'));
```
  
##  <a name="a-namegetbuffera--csimplestringtgetbuffer"></a><a name="getbuffer"></a>CSimpleStringT::GetBuffer  
ポインターの内部文字バッファーを返し、`CSimpleStringT`オブジェクトです。  
  
### <a name="syntax"></a>構文  
  
```  
PXSTR GetBuffer(int nMinBufferLength); 
PXSTR GetBuffer();
```  
#### <a name="parameters"></a>パラメーター  
 `nMinBufferLength`  
 文字バッファーに保持できる文字の最小数。 この値は、null 終端文字用の領域は含まれません。  
  
 場合`nMinBufferLength`が現在のバッファーの長さより大きい`GetBuffer`現在のバッファーの破棄、要求されたサイズのバッファーに置き換えられますおよびオブジェクトの参照カウントを&0; にリセットします。 以前を呼び出した場合[LockBuffer](#lockbuffer)このバッファーでバッファーのロックが失われました。  
  
### <a name="return-value"></a>戻り値  
 `PXSTR`オブジェクトの (null で終わる) 文字バッファーへのポインター。  
  
### <a name="remarks"></a>コメント  
 バッファーの内容を返すには、このメソッドを呼び出して、`CSimpleStringT`オブジェクトです。 返された`PXSTR`定数ではありませんし、したがっての直接的な変更では、`CSimpleStringT`内容です。  
  
 によって返されたポインターを使用する場合`GetBuffer`文字列の内容を変更するを呼び出す必要があります[ReleaseBuffer](#releasebuffer)以外を使用する前に`CSimpleStringT`メンバー メソッドです。  
  
 によって返されるアドレス`GetBuffer`呼び出しの後に有効なできない可能性があります`ReleaseBuffer`ため追加`CSimpleStringT`操作が発生することができます、`CSimpleStringT`を再割り当てするバッファー。 長さを変更しない場合、バッファーが再割り当てできません、`CSimpleStringT`です。  
  
 バッファー メモリは、自動的に解放されるときに、`CSimpleStringT`オブジェクトは破棄されます。  
  
 文字列の長さ自分で、終端の null 文字は追加されません。 バッファーを解放するときに、最終的な文字列の長さを指定する必要があります、`ReleaseBuffer`です。 終端の null 文字を付けている場合は、–&1; (既定値) の長さを渡す必要があります。 `ReleaseBuffer`バッファーの長さを決定します。  
  
 満たすために十分なメモリがある場合、`GetBuffer`要求と、このメソッドをスロー関数 * します。  
  
### <a name="example"></a>例  
```cpp  
CSimpleString s(_T("abcd"), pMgr);
LPTSTR pBuffer = s.GetBuffer(10);
int sizeOfBuffer = s.GetAllocLength();

// Directly access CSimpleString buffer
_tcscpy_s(pBuffer, sizeOfBuffer, _T("Hello"));
ASSERT(_tcscmp(s, _T("Hello")) == 0);
s.ReleaseBuffer();   
```
  
##  <a name="a-namegetbuffersetlengtha--csimplestringtgetbuffersetlength"></a><a name="getbuffersetlength"></a>CSimpleStringT::GetBufferSetLength  
内部文字バッファーへのポインターを返す、`CSimpleStringT`オブジェクト、切り捨てまたはで指定された長さと正確に一致する必要がある場合は、その長さを増大している`nLength`します。  
  
### <a name="syntax"></a>構文  
  
```  
PXSTR GetBufferSetLength(int nLength);
```  
#### <a name="parameters"></a>パラメーター  
 `nLength`  
 正確なサイズ、`CSimpleStringT`文字内で文字バッファー。  
  
### <a name="return-value"></a>戻り値  
 A`PXSTR`オブジェクトの (null で終わる) 文字バッファーへのポインター。  
  
### <a name="remarks"></a>コメント  
 内部バッファーの指定された長さを取得するには、このメソッドを呼び出して、`CSimpleStringT`オブジェクトです。 返された`PXSTR`のポインターは`const`の直接的な変更ができるので`CSimpleStringT`内容です。  
  
 によって返されたポインターを使用する場合[GetBufferSetLength](#getbuffersetlength)文字列の内容を変更するには、呼び出す`ReleaseBuffer`の内部状態を更新する`CsimpleStringT`以外を使用する前に`CSimpleStringT`メソッドです。  
  
 によって返されるアドレス`GetBufferSetLength`呼び出しの後に有効なできない可能性があります`ReleaseBuffer`ため追加`CSimpleStringT`操作が発生することができます、`CSimpleStringT`を再割り当てするバッファー。 長さを変更しない場合は、バッファーを再割り当てされません、`CSimpleStringT`です。  
  
 バッファー メモリは、自動的に解放されるときに、`CSimpleStringT`オブジェクトは破棄されます。  
  
 文字列の長さ自分で場合、は、終端の null 文字をいない追加できません。 使用して、バッファーを解放する場合は、最終的な文字列の長さを指定する必要があります`ReleaseBuffer`します。 呼び出したときに、終端の null 文字を追加するかどうかは`ReleaseBuffer`に長さを –&1; (既定値) を渡す`ReleaseBuffer`と`ReleaseBuffer`を実行、`strlen`バッファーの長さを判断するのです。  
  
 参照カウントの詳細については、次の記事を参照してください。  
  
- [参照カウントをオブジェクトの有効期間を管理する](http://msdn.microsoft.com/library/windows/desktop/ms687260)windows SDK。 
  
- [参照カウントを実装する](http://msdn.microsoft.com/library/windows/desktop/ms693431)windows SDK。
  
- [参照カウントを管理するためのルール](http://msdn.microsoft.com/library/windows/desktop/ms692481)windows SDK。  
  
### <a name="example"></a>例  
 次の例は、`CSimpleStringT::GetBufferSetLength` の使い方を示しています。  
  
```cpp  
CSimpleString str(pMgr);
LPTSTR pstr = str.GetBufferSetLength(3);
pstr[0] = _T('C');
pstr[1] = _T('u');
pstr[2] = _T('p');

// No need for trailing zero or call to ReleaseBuffer() 
// because GetBufferSetLength() set it for us.

str += _T(" soccer is best!");
ASSERT(_tcscmp(str, _T("Cup soccer is best!")) == 0);
```
  
##  <a name="a-namegetlengtha--csimplestringtgetlength"></a><a name="getlength"></a>CSimpleStringT::GetLength  
文字数を返す、`CSimpleStringT`オブジェクトです。  
  
### <a name="syntax"></a>構文  
  
```  
int GetLength() const throw();  
```  
### <a name="return-value"></a>戻り値  
 文字列の文字の数。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出して、オブジェクトの文字の数を返します。 カウントでは、null 終端文字は含まれません。  
  
 マルチバイト文字セット (MBCS)、`GetLength`カウントが 1 つのマルチバイト文字内の各 8 ビット文字; は、潜在顧客と後続バイトが 2 つのバイト数としてカウントされます。 参照してください[FreeExtra](#freeextra)この関数の呼び出しの例です。  
  
##  <a name="a-namegetmanagera--csimplestringtgetmanager"></a><a name="getmanager"></a>CSimpleStringT::GetManager  
メモリ マネージャーの取得、`CSimpleStringT`オブジェクトです。  
  
### <a name="syntax"></a>構文  
  
```  
IAtlStringMgr* GetManager() const throw();  
```  
### <a name="return-value"></a>戻り値  
 メモリ マネージャーへのポインター、`CSimpleStringT`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 Manager で使用されるメモリを取得するには、このメソッドを呼び出して、`CSimpleStringT`オブジェクトです。 メモリ マネージャーと文字列オブジェクトの詳細については、次を参照してください。[メモリ管理と CStringT](../memory-management-with-cstringt.md)します。  
  
##  <a name="a-namegetstringa--csimplestringtgetstring"></a><a name="getstring"></a>CSimpleStringT::GetString
文字の文字列を取得します。  
  
### <a name="syntax"></a>構文  
  
```  
PCXSTR GetString() const throw();
```  
### <a name="return-value"></a>戻り値  
 Null で終わる文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 関連付けられている文字の文字列を取得するには、このメソッドを呼び出して、`CSimpleStringT`オブジェクトです。  
  
> [!NOTE]
>  返された`PCXSTR`ポインターが`const`の直接的な変更で許可されていない`CSimpleStringT`内容です。  
  
### <a name="example"></a>例  
 次の例は、`CSimpleStringT::GetString` の使い方を示しています。  
  
```cpp  
CSimpleString str(pMgr);
str += _T("Cup soccer is best!");
_tprintf_s(_T("%s"), str.GetString());
```
  
##  <a name="a-nameisemptya--csimplestringtisempty"></a><a name="isempty"></a>CSimpleStringT::IsEmpty  
テスト、`CSimpleStringT`空の状態のオブジェクト。  
  
### <a name="syntax"></a>構文  
  
```  
bool IsEmpty() const throw();  
```  
### <a name="return-value"></a>戻り値  
 返します。 **true**場合、`CSimpleStringT`オブジェクトには長さが 0 以外の場合**false**します。  
  
### <a name="remarks"></a>コメント  
 オブジェクトに、空の文字列が含まれているかどうかは、このメソッドを呼び出します。  
  
### <a name="example"></a>例  
 次の例は、`CSimpleStringT::IsEmpty` の使い方を示しています。  
  
```cpp  
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```
  
##  <a name="a-namelockbuffera--csimplestringtlockbuffer"></a><a name="lockbuffer"></a>CSimpleStringT::LockBuffer  
参照カウントを無効にし、バッファー内の文字列を保護します。  
  
### <a name="syntax"></a>構文  
  
```  
PXSTR LockBuffer();
```  
### <a name="return-value"></a>戻り値  
 ポインター、`CSimpleStringT`オブジェクトまたは null で終わる文字列。  
  
### <a name="remarks"></a>コメント  
 バッファーをロックするには、このメソッドを呼び出して、`CSimpleStringT`オブジェクトです。 呼び出して`LockBuffer`、参照カウントを –&1; に、文字列のコピーを作成します。 参照カウント値が-1 の場合は、バッファー内の文字列は「ロック」の状態であると見なされます。 ロックされた状態のときに、文字列は&2; つの方法で保護されています。  
  
-   他の文字列を取得できませんデータへの参照、ロックされた文字列の場合でも、ロックされた文字列に割り当てられている文字列。  
  
-   その他の文字列がロックされている文字列をコピーした場合でも、ロックされた文字列は、別の文字列を参照ことはありません。  
  
 バッファー内の文字列をロックは、文字列のバッファーに排他的に保持は変更されることを確認します。  
  
 使用が完了した後`LockBuffer`、呼び出す[として](#unlockbuffer)参照カウントを 1 にリセットされます。  
  
> [!NOTE]
>  呼び出した場合[GetBuffer](#getbuffer)でロックされているバッファーを設定、`GetBuffer`パラメーター`nMinBufferLength`から現在のバッファーの長さより大きいバッファーのロックが失われます。 このような呼び出しを`GetBuffer`現在のバッファーを破棄、要求されたサイズのバッファーに置き換えられ、参照カウントを&0; にリセットします。  
  
 参照カウントの詳細については、次の記事を参照してください。  
  
- [参照カウントをオブジェクトの有効期間を管理する](http://msdn.microsoft.com/library/windows/desktop/ms687260)windows SDK  
  
- [参照カウントを実装する](http://msdn.microsoft.com/library/windows/desktop/ms693431)windows SDK  
  
- [参照カウントを管理するためのルール](http://msdn.microsoft.com/library/windows/desktop/ms692481)windows SDK  
  
### <a name="example"></a>例  
 次の例は、`CSimpleStringT::LockBuffer` の使い方を示しています。  
  
```cpp  
CSimpleString str(_T("Hello"), pMgr);
TCHAR ch;

str.LockBuffer();
ch = str.GetAt(2);
_tprintf_s(_T("%c"), ch);
str.UnlockBuffer();
```
  
##  <a name="a-nameoperatorata--csimplestringtoperator"></a><a name="operator_at"></a>CSimpleStringT::operator\[\]  
文字配列の&1; つの文字にアクセスするには、この関数を呼び出します。  
  
### <a name="syntax"></a>構文  
  
```  
XCHAR operator[](int iChar) const;
```  
#### <a name="parameters"></a>パラメーター  
 `iChar`  
 文字列内の文字の&0; から始まるインデックス。  
  
### <a name="remarks"></a>コメント  
 オーバー ロードされた添字 (`[]`) 演算子で&0; から始まるインデックスで指定した単一の文字を返します`iChar`します。 この演算子は、便利に代わるもの、 [GetAt](#getat)メンバー関数。  
  
> [!NOTE]
>  添字を使用することができます (`[]`) 内の文字の値を取得する演算子、 `CSimpleStringT`、内の文字の値を変更するのには使用できません、`CSimpleStringT`です。  
  
### <a name="example"></a>例  
 次の例では、使用**CSimpleStringT::operator:operator[]**します。  
  
```cpp  
CSimpleString s(_T("abc"), pMgr);
ASSERT(s[1] == _T('b'));
```
  
## <a name="a-nameoperatorata--csimplestringtoperator-"></a><a name="operator_at"></a>CSimpleStringT::operator\[\]
文字配列の&1; つの文字にアクセスするには、この関数を呼び出します。  
  
### <a name="syntax"></a>構文  
  
```   
XCHAR operator[](int iChar) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `iChar`  
 文字列内の文字の&0; から始まるインデックス。  
  
### <a name="remarks"></a>コメント  
 オーバー ロードされた添字 (`[]`) 演算子で&0; から始まるインデックスで指定した単一の文字を返します`iChar`します。 この演算子は、便利に代わるもの、 [GetAt](#getat)メンバー関数。  
  
> [!NOTE]
>  添字を使用することができます (`[]`) 内の文字の値を取得する演算子、 `CSimpleStringT`、内の文字の値を変更するのには使用できません、`CSimpleStringT`です。  
  
  
##  <a name="a-nameoperatoraddeqa--csimplestringtoperator-"></a><a name="operator_add_eq"></a>CSimpleStringT::operator + = 演算子  
新しい文字列または文字を既存の文字列の末尾に結合します。  
  
### <a name="syntax"></a>構文  
  
```  
CSimpleStringT& operator +=(PCXSTR pszSrc); 
CSimpleStringT& operator +=(const CSimpleStringT& strSrc); 
template<int t_nSize>  
CSimpleStringT& operator+=(const CStaticString< XCHAR, t_nSize >& strSrc); 
CSimpleStringT& operator +=(char ch); 
CSimpleStringT& operator +=(unsigned char ch); 
CSimpleStringT& operator +=(wchar_t ch);
```  
#### <a name="parameters"></a>パラメーター  
 `pszSrc`  
 Null で終わる文字列へのポインター。  
  
 `strSrc`  
 既存へのポインター`CSimpleStringT`オブジェクトです。  
  
 *ch*  
 追加される文字。  
  
### <a name="remarks"></a>コメント  
 この演算子は別`CSimpleStringT`オブジェクトまたは文字。 メモリ不足連結演算子を使用する文字が次のように追加されて、新しい記憶域を割り当てることができるため、例外が発生する`CSimpleStringT`オブジェクトです。  
  
### <a name="example"></a>例  
 次の例では、使用**CSimpleStringT::operator + =**です。  
  
```cpp  
CSimpleString str(_T("abc"), pMgr);
ASSERT(_tcscmp((str += _T("def")), _T("abcdef")) == 0);
```
  
##  <a name="a-nameoperatoreqa--csimplestringtoperator-"></a><a name="operator_eq"></a>CSimpleStringT::operator =  
新しい値を代入する`CSimpleStringT`オブジェクトです。  
  
### <a name="syntax"></a>構文  
  
```  
CSimpleStringT& operator =(PCXSTR pszSrc); 
CSimpleStringT& operator =(const CSimpleStringT& strSrc);
```  
#### <a name="parameters"></a>パラメーター  
 `pszSrc`  
 Null で終わる文字列へのポインター。  
  
 `strSrc`  
 既存へのポインター`CSimpleStringT`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 コピー先の文字列 (左側) は、新しいデータを格納するのに十分な大きさが既に、新しいメモリ割り当ては実行されません。 メモリ不足例外が発生するは、代入演算子を使用すると、新しいストレージが多くの場合、その結果を保持するために割り当てられているため`CSimpleStringT`オブジェクトです。  
  
### <a name="example"></a>例  
 次の例では、使用**CSimpleStringT::operator =**です。  
  
```cpp  
CSimpleString s1(pMgr), s2(pMgr);
// Empty CSimpleStringT objects

s1 = _T("cat");
// s1 = "cat"
ASSERT(_tcscmp(s1, _T("cat")) == 0);

s2 = s1;               // s1 and s2 each = "cat"
ASSERT(_tcscmp(s2, _T("cat")) == 0);

s1 = _T("the ") + s1;      
// Or expressions
ASSERT(_tcscmp(s1, _T("the cat")) == 0);

s1 = _T("x");
// Or just individual characters
ASSERT(_tcscmp(s1, _T("x")) == 0);
```
  
##  <a name="a-nameoperatorpcxstra--csimplestringtoperator-pcxstr"></a><a name="operator_pcxstr"></a>CSimpleStringT::operator PCXSTR  

 格納される文字に直接アクセスする、`CSimpleStringT`オブジェクトを C スタイルの文字列として。  
  
### <a name="syntax"></a>構文  
  
```  
operator PCXSTR() const throw();
```  
### <a name="return-value"></a>戻り値  
 文字列のデータを指すポインター。  
  
### <a name="remarks"></a>コメント  
 文字はコピーされません。ポインターのみが返されます。 この演算子に注意してください。 変更した場合、`CString`オブジェクト、ポインターを無効にするメモリの割り当ての変更が発生した文字ポインターを取得した後です。  
  
### <a name="example"></a>例  
 次の例では、使用**CSimpleStringT::operator PCXSTR**します。  
  
```cpp  
// If the prototype of a function is known to the compiler, 
// the PCXSTR cast operator may be invoked implicitly.

CSimpleString strSports(L"Soccer is Best!", pMgr);
WCHAR sz[1024];

wcscpy_s(sz, strSports);

// If the prototype isn't known or is a va_arg prototype, 
// you must invoke the cast operator explicitly. For example, 
// the va_arg part of a call to swprintf_s() needs the cast:

swprintf_s(sz, 1024, L"I think that %s!\n", (PCWSTR)strSports);

// While the format parameter is known to be an PCXSTR and 
// therefore doesn't need the cast:

swprintf_s(sz, 1024, strSports);

// Note that some situations are ambiguous. This line will 
// put the address of the strSports object to stdout:

wcout << strSports;

// while this line will put the content of the string out:

wcout << (PCWSTR)strSports;   
``` 
  
##  <a name="a-namepcxstra--csimplestringtpcxstr"></a><a name="pcxstr"></a>CSimpleStringT::PCXSTR
定数文字列へのポインター。  
  
### <a name="syntax"></a>構文  
  
```  
typedef ChTraitsBase< BaseType >::PCXSTR PCXSTR;    
```  
##  <a name="a-namepreallocatea--csimplestringtpreallocate"></a><a name="preallocate"></a>CSimpleStringT::Preallocate  
一定のバイトを割り当て、`CSimpleStringT`オブジェクトです。  
  
### <a name="syntax"></a>構文  
  
```  
void Preallocate( int nLength);
```  
#### <a name="parameters"></a>パラメーター  
 `nLength`  
 正確なサイズ、`CSimpleStringT`文字内で文字バッファー。  
  
### <a name="remarks"></a>コメント  
 特定のバッファー サイズを割り当てることは、このメソッドを呼び出して、`CSimpleStringT`オブジェクトです。  
  
 `CSimpleStringT`生成、`STATUS_NO_MEMORY`文字バッファーに領域を割り当てることがない場合。 WIN32 API 関数により既定では、メモリの割り当てが実行される`HeapAlloc`または`HeapReAlloc`です。  
  
### <a name="example"></a>例  
 次の例は、`CSimpleStringT::Preallocate` の使い方を示しています。  
  
```cpp  
CSimpleString str(pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
str.Preallocate(100);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
```
  
##  <a name="a-namepxstra--csimplestringtpxstr"></a><a name="pxstr"></a>CSimpleStringT::PXSTR  
文字列へのポインター。  
  
### <a name="syntax"></a>構文  
  
```  
typedef ChTraitsBase< BaseType >::PXSTR PXSTR;  
```  
##  <a name="a-namereleasebuffera--csimplestringtreleasebuffer"></a><a name="releasebuffer"></a>CSimpleStringT::ReleaseBuffer  
によって割り当てられるバッファーの制御を[GetBuffer](#getbuffer)します。  
  
### <a name="syntax"></a>構文  
  
```  
void ReleaseBuffer(int nNewLength = -1);
```  
#### <a name="parameters"></a>パラメーター  
 `nNewLength`  
 文字列の文字、null 終端文字をカウントしませんの新しい長さ。 -1 の既定値の設定、文字列が null の場合は終了、`CSimpleStringT`サイズ文字列の現在の長さにします。  
  
### <a name="remarks"></a>コメント  
 再割り当てしますか、文字列オブジェクトのバッファーを解放するには、このメソッドを呼び出します。 バッファーに文字列は null で終了を省略することがわかっている場合、`nNewLength`引数。 場合は、文字列が null でない終了を使用して`nNewLength`その長さを指定します。 によって返されるアドレス[GetBuffer](#getbuffer)呼び出しの後に有効な`ReleaseBuffer`またはその他の`CSimpleStringT`操作します。  
  
### <a name="example"></a>例  
 次の例は、`CSimpleStringT::ReleaseBuffer` の使い方を示しています。  
  
```cpp  
const int bufferSize = 1024;
CSimpleString s(_T("abc"), pMgr);
LPTSTR p = s.GetBuffer(bufferSize);
_tcscpy_s(p, bufferSize, _T("abc"));

  // use the buffer directly
ASSERT(s.GetLength() == 3);

// String length = 3
s.ReleaseBuffer();

// Surplus memory released, p is now invalid.
ASSERT(s.GetLength() == 3);

// Length still 3
```
  
##  <a name="a-namereleasebuffersetlengtha--csimplestringtreleasebuffersetlength"></a><a name="releasebuffersetlength"></a>CSimpleStringT::ReleaseBufferSetLength

によって割り当てられるバッファーの制御を[GetBuffer](#getbuffer)します。  
  
### <a name="syntax"></a>構文  
  
```  
void ReleaseBufferSetLength(int nNewLength);
```  
#### <a name="parameters"></a>パラメーター  
 `nNewLength`  
 解放されている文字列の長さ  
  
### <a name="remarks"></a>コメント  
 この関数は、機能的にはのような[ReleaseBuffer](#releasebuffer)する点を除いて、有効な長さの文字列オブジェクトを渡す必要があります。  
  
##  <a name="a-namesetata--csimplestringtsetat"></a><a name="setat"></a>CSimpleStringT::SetAt  
設定の&1; 文字を`CSimpleStringT`オブジェクトです。  
  
### <a name="syntax"></a>構文  
  
```  
void SetAt(int iChar, XCHAR ch);
```  
#### <a name="parameters"></a>パラメーター  
 `iChar`  
 内の文字の&0; から始まるインデックス、`CSimpleStringT`オブジェクトです。 `iChar`パラメーターが 0 より大きいで、かつによって返される値より小さくする必要があります[GetLength](#getlength)します。  
  
 *ch*  
 新しい文字です。  
  
### <a name="remarks"></a>コメント  
 ある文字を上書きするには、このメソッドを呼び出す`iChar`します。 場合は、このメソッドに、文字列は拡大しません`iChar`既存の文字列の範囲を超えています。  
  
### <a name="example"></a>例  
 次の例は、`CSimpleStringT::SetAt` の使い方を示しています。  
  
```cpp  
CSimpleString s(_T("abcdef"), pMgr);
s.SetAt(1, _T('a'));
ASSERT(_tcscmp(s, _T("aacdef")) == 0);
``` 
  
##  <a name="a-namesetmanagera--csimplestringtsetmanager"></a><a name="setmanager"></a>CSimpleStringT::SetManager  
メモリ マネージャーの指定、`CSimpleStringT`オブジェクトです。  
  
### <a name="syntax"></a>構文  
  
```  
void SetManager(IAtlStringMgr* pStringMgr);
```  
#### <a name="parameters"></a>パラメーター  
 `pStringMgr`  
 新しいメモリ マネージャーへのポインター。  
  
### <a name="remarks"></a>コメント  
 Manager で使用される新しいメモリを指定するには、このメソッドを呼び出して、`CSimpleStringT`オブジェクトです。 メモリ マネージャーと文字列オブジェクトの詳細については、次を参照してください。[メモリ管理と CStringT](../memory-management-with-cstringt.md)します。  
  
### <a name="example"></a>例  
 次の例は、`CSimpleStringT::SetManager` の使い方を示しています。  
  
```cpp  
CSimpleString s(pMgr);
s.SetManager(pCustomMgr);
```
  
##  <a name="a-namesetstringa--csimplestringtsetstring"></a><a name="setstring"></a>CSimpleStringT::SetString  
文字列を設定、`CSimpleStringT`オブジェクトです。  
  
### <a name="syntax"></a>構文  
  
```  
void SetString(PCXSTR pszSrc, int nLength); 
void SetString(PCXSTR pszSrc);
```  
#### <a name="parameters"></a>パラメーター  
 `pszSrc`  
 Null で終わる文字列へのポインター。  
  
 `nLength`  
 内の文字の数のカウント`pszSrc`します。  
  
### <a name="remarks"></a>コメント  
 文字列をコピー、`CSimpleStringT`オブジェクトです。 `SetString`バッファー内の古い文字列データが上書きされます。  
  
 両方のバージョンの`SetString`をチェックするかどうか`pszSrc`null ポインターの場合は、スローする場合は、 **E_INVALIDARG**エラー。  
  
 パラメーターを&1; つのバージョンの`SetString`が必要ですが`pszSrc`null で終わる文字列を指すようです。  
  
 2 つのパラメーターのバージョンの`SetString`も期待しています`pszSrc`null で終わる文字列を指定します。 使用して`nLength`文字列の長さとして null 終端文字が最初に発生した場合を除き、します。  
  
 2 つのパラメーターのバージョンの`SetString`かどうかも確認するかどうか`pszSrc`には、現在のバッファーに場所を示す`CSimpleStringT`します。 この特殊なケースで`SetString`文字列データをバッファーにコピーされる際、文字列データを上書きしないメモリ コピー関数を使用します。  
  
### <a name="example"></a>例  
 次の例は、`CSimpleStringT::SetString` の使い方を示しています。  
  
```cpp  
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(_tcscmp(s, _T("abcdef")) == 0);
s.SetString(_T("Soccer"), 6);
ASSERT(_tcscmp(s, _T("Soccer")) == 0);
```
  
##  <a name="a-namestringlengtha--csimplestringtstringlength"></a><a name="stringlength"></a>CSimpleStringT::StringLength  
指定した文字列内の文字数を返します。  
  
### <a name="syntax"></a>構文  
  
```  
ATL_NOINLINE static int StringLength(PCXSTR psz) throw();
```  
#### <a name="parameters"></a>パラメーター  
 `psz`  
 Null で終わる文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 文字数`psz`; null 終端文字をカウントしません。  
  
### <a name="remarks"></a>コメント  
 指す文字列の文字数を取得するには、このメソッドを呼び出す`psz`します。  
  
### <a name="example"></a>例  
 次の例は、`CSimpleStringT::StringLength` の使い方を示しています。  
  
```cpp  
ASSERT(CSimpleString::StringLength(_T("soccer")) == 6);
``` 
  
##  <a name="a-nametruncatea--csimplestringttruncate"></a><a name="truncate"></a>CSimpleStringT::Truncate
新しい長さに文字列を切り捨てます。  
  
### <a name="syntax"></a>構文  
  
```  
void Truncate(int nNewLength);
```  
#### <a name="parameters"></a>パラメーター  
 `nNewLength`  
 文字列の新しい長さ。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出して、新しい長さに文字列の内容を切り捨てます。  
  
> [!NOTE]
>  これには、割り当てられたバッファーの長さは影響しません。 現在のバッファーを増減するには、次を参照してください。 [FreeExtra](#freeextra)と[Preallocate](#preallocate)します。  
  
### <a name="example"></a>例  
 次の例は、`CSimpleStringT::Truncate` の使い方を示しています。  
  
```cpp  
CSimpleString str(_T("abcdefghi"), pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
str.Truncate(4);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
``` 
  
##  <a name="a-nameunlockbuffera--csimplestringtunlockbuffer"></a><a name="unlockbuffer"></a>CSimpleStringT::UnlockBuffer
 バッファーのロックを解除、`CSimpleStringT`オブジェクトです。  
  
### <a name="syntax"></a>構文  
  
```  
void UnlockBuffer() throw();
```  
### <a name="remarks"></a>コメント  
 文字列の参照カウントを 1 にリセットするには、このメソッドを呼び出します。  
  
 `CSimpleStringT`デストラクターが自動的に呼び出します`UnlockBuffer`をデストラクターが呼び出されたときに、バッファーがロックされないことを確認します。 このメソッドの例は、次を参照してください。 [LockBuffer](#lockbuffer)します。  
  
##  <a name="a-namedtora--csimplestringtcsimplestringt"></a><a name="dtor"></a>CSimpleStringT:: ~ CSimpleStringT
`CSimpleStringT` オブジェクトを破棄します。  
  
### <a name="syntax"></a>構文  
  
```  
~CSimpleStringT() throw();
```  
### <a name="remarks"></a>コメント  
 破棄するには、このメソッドを呼び出して、`CSimpleStringT`オブジェクトです。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL と MFC クラスの共有](../../atl-mfc-shared/atl-mfc-shared-classes.md)
