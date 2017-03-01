---
title: "CComBSTR クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CComBSTR
- CComBSTR
- ATL.CComBSTR
dev_langs:
- C++
helpviewer_keywords:
- BSTRs, wrapper
- CComBSTR class
- CComBSTR
ms.assetid: 8fea1879-a05e-47a5-a803-8dec60eaa534
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
ms.sourcegitcommit: 8cdedc5cfac9d49df812ae6fcfcc548201b1edb5
ms.openlocfilehash: e7b61a5826836e7d26a0d470631d7230f7b7be56
ms.lasthandoff: 02/24/2017

---
# <a name="ccombstr-class"></a>CComBSTR クラス
このクラスのラッパーは、`BSTR`秒です。  
  
## <a name="syntax"></a>構文  
  
```
class CComBSTR
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComBSTR::CComBSTR](#ccombstr)|コンストラクターです。|  
|[CComBSTR:: ~ CComBSTR](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComBSTR::Append](#append)|文字列を付加`m_str`します。|  
|[CComBSTR::AppendBSTR](#appendbstr)|追加、`BSTR`に`m_str`します。|  
|[CComBSTR::AppendBytes](#appendbytes)|指定したバイト数を追加`m_str`します。|  
|[CComBSTR::ArrayToBSTR](#arraytobstr)|作成、 `BSTR` safearray の各要素の最初の文字からに接続し、`CComBSTR`オブジェクトです。|  
|[CComBSTR::AssignBSTR](#assignbstr)|代入、`BSTR`に`m_str`します。|  
|[CComBSTR::Attach](#attach)|アタッチ、`BSTR`に、`CComBSTR`オブジェクトです。|  
|[CComBSTR::BSTRToArray](#bstrtoarray)|文字を配列の各要素がここでは&0; から始まる&1; 次元の safearray を作成、`CComBSTR`オブジェクトです。|  
|[CComBSTR::ByteLength](#bytelength)|長さを返す`m_str`(バイト単位)。|  
|[CComBSTR::Copy](#copy)|コピーを返します`m_str`します。|  
|[CComBSTR::CopyTo](#copyto)|コピーを返します`m_str`を使用して、 **[out]**パラメーター|  
|[CComBSTR::Detach](#detach)|デタッチ`m_str`から、`CComBSTR`オブジェクトです。|  
|[CComBSTR::Empty](#empty)|解放`m_str`します。|  
|[CComBSTR::Length](#length)|長さを返す`m_str`します。|  
|[CComBSTR::LoadString](#loadstring)|文字列リソースを読み込みます。|  
|[CComBSTR::ReadFromStream](#readfromstream)|読み込み、`BSTR`オブジェクトをストリームからです。|  
|[CComBSTR::ToLower](#tolower)|文字列を小文字に変換します。|  
|[CComBSTR::ToUpper](#toupper)|文字列を大文字に変換します。|  
|[CComBSTR::WriteToStream](#writetostream)|保存`m_str`をストリームにします。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CComBSTR::operator BSTR](#operator_bstr)|キャスト、`CComBSTR`オブジェクトを`BSTR`です。|  
|[CComBSTR::operator!](#operator_not)|返します。`true`または`false`かどうかに応じて、`m_str`は`NULL`です。|  
|[CComBSTR::operator! =](#operator_neq)|比較、`CComBSTR`文字列を使用します。|  
|[CComBSTR::operator >/documents/report1.rdl」の](#operator_amp)|アドレスを返す`m_str`します。|  
|[CComBSTR::operator + = 演算子](#operator_add_eq)|追加、`CComBSTR`オブジェクトにします。|  
|[CComBSTR::operator](#operator_lt)|比較、`CComBSTR`文字列を使用します。|  
|[CComBSTR::operator =](#operator_eq)|値を代入`m_str`します。|  
|[CComBSTR::operator = =](#operator_eq_eq)|比較、`CComBSTR`文字列を使用します。|  
|[CComBSTR::operator >](#operator_gt)|比較、`CComBSTR`文字列を使用します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComBSTR::m_str](#m_str)|含む、`BSTR`に関連付けられている、`CComBSTR`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 `CComBSTR`クラスのラッパーは、`BSTR`で、これは固定長の文字列です。 長さは、整数、文字列内のデータの前にメモリ位置として格納されます。  
  
 A [BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228)が null で終わる、最後の文字をカウントが、文字列に埋め込まれた null 文字を含めることもできます。 文字列の長さは、最初の null 文字ではない、文字数によって決まります。  
  
> [!NOTE]
>  `CComBSTR`クラスには、ANSI または Unicode のいずれかの文字列を引数としてを取得するメンバー (コンス トラクター、代入演算子、および比較演算子) の数が用意されています。 一時的な Unicode 文字列が内部で作成された多くの場合するためには、これらの関数の ANSI バージョンは、Unicode 対応するよりも効率が低下します。 効率性のためには、可能であれば Unicode バージョンを使用します。  
  
> [!NOTE]
>  Visual Studio .NET に実装されている強化された検索の動作によりコードなど`bstr = L"String2" + bstr;`、以前のリリースでコンパイルする代わりに実装すべきとして`bstr = CStringW(L"String2") + bstr`します。  
  
 使用する場合の注意事項の一覧については`CComBSTR`を参照してください[CComBSTR を使用したプログラミング](../../atl/programming-with-ccombstr-atl.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="a-nameappenda--ccombstrappend"></a><a name="append"></a>CComBSTR::Append  
 いずれかの追加`lpsz`または`BSTR`のメンバー`bstrSrc`に[m_str](#m_str)します。  
  
```
HRESULT Append(const CComBSTR& bstrSrc) throw();
HRESULT Append(wchar_t ch) throw();
HRESULT Append(char ch) throw();
HRESULT Append(LPCOLESTR lpsz) throw();
HRESULT Append(LPCSTR lpsz) throw();
HRESULT Append(LPCOLESTR lpsz, int nLen) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `bstrSrc`  
 [in]A`CComBSTR`追加するオブジェクト。  
  
 *ch*  
 [in]追加する文字。  
  
 `lpsz`  
 [in]追加する文字の&0; で終わる文字列。 使用して Unicode 文字列を渡すことができます、 **LPCOLESTR**過負荷または ANSI 文字列を使用して、`LPCSTR`バージョンです。  
  
 `nLen`  
 [in]文字数`lpsz`を追加します。  
  
### <a name="return-value"></a>戻り値  
 `S_OK`成功した場合、または任意の標準に`HRESULT`エラー値。  
  
### <a name="remarks"></a>コメント  
 追加する前に、ANSI 文字列を Unicode に変換されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities&#32;](../../atl/codesnippet/cpp/ccombstr-class_1.cpp)]  
  
##  <a name="a-nameappendbstra--ccombstrappendbstr"></a><a name="appendbstr"></a>CComBSTR::AppendBSTR  
 指定した追加`BSTR`に[m_str](#m_str)します。  
  
```
HRESULT AppendBSTR(BSTR p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 [in]A`BSTR`を追加します。  
  
### <a name="return-value"></a>戻り値  
 `S_OK`成功した場合、または任意の標準に`HRESULT`エラー値。  
  
### <a name="remarks"></a>コメント  
 このメソッドに通常のワイド文字の文字列を渡さないでください。 コンパイラは、エラーをキャッチし、実行時エラーが発生することはできません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&33;](../../atl/codesnippet/cpp/ccombstr-class_2.cpp)]  
  
##  <a name="a-nameappendbytesa--ccombstrappendbytes"></a><a name="appendbytes"></a>CComBSTR::AppendBytes  
 指定したバイト数の追加[m_str](#m_str)変換なし。  
  
```
HRESULT AppendBytes(const char* lpsz, int nLen) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpsz`  
 [in]追加するバイトの配列へのポインター。  
  
 `p`  
 [in]追加するバイト数。  
  
### <a name="return-value"></a>戻り値  
 `S_OK`成功した場合、または任意の標準に`HRESULT`エラー値。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&34;](../../atl/codesnippet/cpp/ccombstr-class_3.cpp)]  
  
##  <a name="a-namearraytobstra--ccombstrarraytobstr"></a><a name="arraytobstr"></a>CComBSTR::ArrayToBSTR  
 保持されている既存の文字列を解放、`CComBSTR`オブジェクトを作成し、 `BSTR` safearray の各要素の最初の文字からに接続し、`CComBSTR`オブジェクトです。  
  
```
HRESULT ArrayToBSTR(const SAFEARRAY* pSrc) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pSrc`  
 [in]文字列を作成するために使用する要素を格納する safearray。  
  
### <a name="return-value"></a>戻り値  
 `S_OK`成功した場合、または任意の標準に`HRESULT`エラー値。  
  
##  <a name="a-nameassignbstra--ccombstrassignbstr"></a><a name="assignbstr"></a>CComBSTR::AssignBSTR  
 代入、`BSTR`に[m_str](#m_str)します。  
  
```
HRESULT AssignBSTR(const BSTR bstrSrc) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `bstrSrc`  
 [in]A`BSTR`現在に割り当てる`CComBSTR`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 `S_OK`成功した場合、または任意の標準に`HRESULT`エラー値。  
  
##  <a name="a-nameattacha--ccombstrattach"></a><a name="attach"></a>CComBSTR::Attach  
 アタッチ、`BSTR`に、`CComBSTR`オブジェクトを設定して、 [m_str](#m_str)メンバー *src*します。  
  
```
void Attach(BSTR src) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *src*  
 [in]`BSTR`オブジェクトにアタッチします。  
  
### <a name="remarks"></a>コメント  
 このメソッドに通常のワイド文字の文字列を渡さないでください。 コンパイラは、エラーをキャッチし、実行時エラーが発生することはできません。  
  
> [!NOTE]
>  このメソッドはアサート場合`m_str`以外は、 **NULL**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities&#35;](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]  
  
##  <a name="a-namebstrtoarraya--ccombstrbstrtoarray"></a><a name="bstrtoarray"></a>CComBSTR::BSTRToArray  
 文字を配列の各要素がここでは&0; から始まる&1; 次元の safearray を作成、`CComBSTR`オブジェクトです。  
  
```
HRESULT BSTRToArray(LPSAFEARRAY* ppArray) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `ppArray`  
 [out]関数の結果を保持するために使用する safearray へのポインター。  
  
### <a name="return-value"></a>戻り値  
 `S_OK`成功した場合、または任意の標準に`HRESULT`エラー値。  
  
##  <a name="a-namebytelengtha--ccombstrbytelength"></a><a name="bytelength"></a>CComBSTR::ByteLength  
 内のバイト数を返します`m_str`、終端の null 文字を除外します。  
  
```
unsigned int ByteLength() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 長さ、 [m_str](#m_str)メンバー (バイト単位)。  
  
### <a name="remarks"></a>コメント  
 0 を返します`m_str`は**NULL**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities&#36;](../../atl/codesnippet/cpp/ccombstr-class_5.cpp)]  
  
##  <a name="a-nameccombstra--ccombstrccombstr"></a><a name="ccombstr"></a>CComBSTR::CComBSTR  
 コンストラクターです。 既定のコンス トラクターは、設定、 [m_str](#m_str)メンバー **NULL**します。  
  
```
CComBSTR() throw();
CComBSTR(const CComBSTR& src);  
CComBSTR(REFGUID  guid);  
CComBSTR(int nSize);  
CComBSTR(int nSize, LPCOLESTR sz);  
CComBSTR(int nSize, LPCSTR sz);  
CComBSTR(LPCOLESTR pSrc);  
CComBSTR(LPCSTR pSrc);  
CComBSTR(CComBSTR&& src) throw(); // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>パラメーター  
 `nSize`  
 [入力] `sz` からコピーする文字数、または `CComBSTR` の文字数の初期サイズ。  
  
 `sz`  
 [入力] コピーする文字列。 Unicode のバージョンを指定、 **LPCOLESTR**; ANSI バージョンの指定、`LPCSTR`です。  
  
 `pSrc`  
 [入力] コピーする文字列。 Unicode のバージョンを指定、 **LPCOLESTR**; ANSI バージョンの指定、`LPCSTR`です。  
  
 *src*  
 [入力] `CComBSTR` オブジェクト。  
  
 `guid`  
 [in]参照、 **GUID**構造体。  
  
### <a name="remarks"></a>コメント  
 コピー コンス トラクター セット`m_str`のコピーを`BSTR`のメンバー *src*します。 **REFGUID**コンス トラクターに変換、 **GUID**を使用して文字列に**StringFromGUID2**し結果を格納します。  
  
 その他のコンストラクターは、`m_str` を指定された文字列のコピーに設定します。 `nSize` の値を渡した場合は、`nSize` 分の文字だけがコピーされ、終端の null 文字が付加されます。  
  
 `CComBSTR` は移動セマンティクスをサポートします。 移動コンス トラクターを使用することができます (右辺値参照を受け取るコンス トラクター ( `&&`)、古いオブジェクトのオブジェクトのコピーのオーバーヘッドの増加を引数として渡すと、同じ基になるデータを使用する新しいオブジェクトを作成します。  
  
 デストラクターは、`m_str` が指す文字列を解放します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&37;](../../atl/codesnippet/cpp/ccombstr-class_6.cpp)]  
  
##  <a name="a-namedtora--ccombstrccombstr"></a><a name="dtor"></a>CComBSTR:: ~ CComBSTR  
 デストラクターです。  
  
```
~CComBSTR();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターは、`m_str` が指す文字列を解放します。  
  
##  <a name="a-namecopya--ccombstrcopy"></a><a name="copy"></a>CComBSTR::Copy  
 割り当てのコピーを返します`m_str`します。  
  
```
BSTR Copy() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 コピー、 [m_str](#m_str)メンバーです。 If `m_str` is **NULL**, returns **NULL**.  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&38;](../../atl/codesnippet/cpp/ccombstr-class_7.cpp)]  
  
##  <a name="a-namecopytoa--ccombstrcopyto"></a><a name="copyto"></a>CComBSTR::CopyTo  
 割り当てのコピーを返します[m_str](#m_str)パラメーターを使用しています。  
  
```
HRESULT CopyTo(BSTR* pbstr) throw();

HRESULT CopyTo(VARIANT* pvarDest) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *pbstr*  
 [out]アドレス、`BSTR`すると、このメソッドによって割り当てられた文字列が返されます。  
  
 `pvarDest`  
 [out]アドレス、 **VARIANT**すると、このメソッドによって割り当てられた文字列が返されます。  
  
### <a name="return-value"></a>戻り値  
 標準的な`HRESULT`コピーの成否を示す値。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出した後、 **VARIANT**指す`pvarDest`型である`VT_BSTR`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities&#39;](../../atl/codesnippet/cpp/ccombstr-class_8.cpp)]  
  
##  <a name="a-namedetacha--ccombstrdetach"></a><a name="detach"></a>CComBSTR::Detach  
 デタッチ[m_str](#m_str)から、`CComBSTR`オブジェクトとセット`m_str`に**NULL**します。  
  
```
BSTR Detach() throw();
```  
  
### <a name="return-value"></a>戻り値  
 `BSTR`に関連付けられている、`CComBSTR`オブジェクトです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&40;](../../atl/codesnippet/cpp/ccombstr-class_9.cpp)]  
  
##  <a name="a-nameemptya--ccombstrempty"></a><a name="empty"></a>CComBSTR::Empty  
 解放、 [m_str](#m_str)メンバーです。  
  
```
void Empty() throw();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&41;](../../atl/codesnippet/cpp/ccombstr-class_10.cpp)]  
  
##  <a name="a-namelengtha--ccombstrlength"></a><a name="length"></a>CComBSTR::Length  
 内の文字数を返します`m_str`、終端の null 文字を除外します。  
  
```
unsigned int Length() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 長さ、 [m_str](#m_str)メンバーです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&42;](../../atl/codesnippet/cpp/ccombstr-class_11.cpp)]  
  
##  <a name="a-nameloadstringa--ccombstrloadstring"></a><a name="loadstring"></a>CComBSTR::LoadString  
 指定された文字列リソースを読み込みます`nID`し、このオブジェクトに格納します。  
  
```
bool LoadString(HINSTANCE hInst, UINT nID) throw();
bool LoadString(UINT nID) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 参照してください[LoadString](http://msdn.microsoft.com/library/windows/desktop/ms647486)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 返します**true**文字列が正常に読み込まれた、それ以外の場合は、返す**false**します。  
  
### <a name="remarks"></a>コメント  
 1 つ目の関数を使用してユーザーが特定されたモジュールから、リソースを読み込みます、`hInst`パラメーター。 2 番目の関数に関連付けられているリソース モジュールから、リソースを読み込みます、 [CComModule](../../atl/reference/ccommodule-class.md)-このプロジェクトで使用されるオブジェクトを派生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&43;](../../atl/codesnippet/cpp/ccombstr-class_12.cpp)]  
  
##  <a name="a-namemstra--ccombstrmstr"></a><a name="m_str"></a>CComBSTR::m_str  
 含む、`BSTR`に関連付けられている、`CComBSTR`オブジェクトです。  
  
```
BSTR m_str;
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities 番号&49;](../../atl/codesnippet/cpp/ccombstr-class_13.cpp)]  
  
##  <a name="a-nameoperatorbstra--ccombstroperator-bstr"></a><a name="operator_bstr"></a>CComBSTR::operator BSTR  
 キャスト、`CComBSTR`オブジェクトを`BSTR`です。  
  
```  
operator BSTR() const throw();
```  
  
### <a name="remarks"></a>コメント  
 渡す`CComBSTR`を持つ関数オブジェクト**[in] BSTR**パラメーター。  
  
### <a name="example"></a>例  
 例を参照してください[CComBSTR::m_str](#m_str)します。  
  
##  <a name="a-nameoperatornota--ccombstroperator-"></a><a name="operator_not"></a>CComBSTR::operator!  
 チェックするかどうか`BSTR`文字列が NULL です。  
  
```
bool operator!() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**場合、 [m_str](#m_str)メンバーは**NULL**。 そうしないと、 **false**します。  
  
### <a name="remarks"></a>コメント  
 この演算子は、空の文字列ではなく、NULL 値のだけを確認します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities&#35;](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]  
  
##  <a name="a-nameoperatorneqa--ccombstroperator-"></a><a name="operator_neq"></a>CComBSTR::operator! =  
 論理的に反対の返します[演算子 = =](#operator_eq_eq)です。  
  
```
bool operator!= (const CComBSTR& bstrSrc) const throw();
bool operator!= (LPCOLESTR pszSrc) const;
bool operator!= (LPCSTR pszSrc) const;
bool operator!= (int nNull) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `bstrSrc`  
 [入力] `CComBSTR` オブジェクト。  
  
 `pszSrc`  
 [in]0 で終わる文字列。  
  
 `nNull`  
 [in]必要があります**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 返します**true**比較対象のアイテムと等しくない場合、`CComBSTR`オブジェクト。 それ以外の場合、返されます**false**します。  
  
### <a name="remarks"></a>コメント  
 `CComBSTR`ユーザーの既定のロケールのコンテキストでは、s がテキストで比較されます。 最後の比較演算子には、格納されている文字列だけを比較して**NULL**します。  
  
##  <a name="a-nameoperatorampa--ccombstroperator-amp"></a><a name="operator_amp"></a>CComBSTR::operator&amp;  
 アドレスを返す、`BSTR`に格納されている、 [m_str](#m_str)メンバーです。  
  
```
BSTR* operator&() throw();
```  
  
### <a name="remarks"></a>コメント  
 `CComBstr operator &`特殊なアサーションに関連付けられている、メモリ リークを識別しやすくします。 プログラムをアサートときに、`m_str`メンバーを初期化します。 このアサーションは、プログラマが使用状況を識別するために作成された、`& operator`に新しい値を代入する`m_str`の最初の割り当てを解放せずメンバー`m_str`します。 場合`m_str`"NULL"と等しい、プログラムでは、m_str まだ割り当てられていないと想定しています。 この場合、プログラムはアサートされません。  
  
 このアサーションは、既定では無効です。 定義`ATL_CCOMBSTR_ADDRESS_OF_ASSERT`このアサーションが有効にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities&#46;](../../atl/codesnippet/cpp/ccombstr-class_14.cpp)]  
  
 [!code-cpp[NVC_ATL_Utilities #&47;](../../atl/codesnippet/cpp/ccombstr-class_15.cpp)]  
  
##  <a name="a-nameoperatoraddeqa--ccombstroperator-"></a><a name="operator_add_eq"></a>CComBSTR::operator + = 演算子  
 文字列を追加、`CComBSTR`オブジェクトです。  
  
```
CComBSTR& operator+= (const CComBSTR& bstrSrc);  
CComBSTR& operator+= (const LPCOLESTR pszSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 `bstrSrc`  
 [in]A`CComBSTR`追加するオブジェクト。  
  
 `pszSrc`  
 [in]追加する&0; で終わる文字列。  
  
### <a name="remarks"></a>コメント  
 `CComBSTR`ユーザーの既定のロケールのコンテキストでは、s がテキストで比較されます。 **LPCOLESTR**比較が行われを使用して`memcmp`各文字列の生データにします。 `LPCSTR`比較が実行される同じ方法での一時的な Unicode のコピーと`pszSrc`が用意されています。 最後の比較演算子には、格納されている文字列だけを比較して**NULL**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&48;](../../atl/codesnippet/cpp/ccombstr-class_16.cpp)]  
  
##  <a name="a-nameoperatorlta--ccombstroperator-lt"></a><a name="operator_lt"></a>CComBSTR::operator&lt;  
 比較、`CComBSTR`文字列を使用します。  
  
```
bool operator<(const CComBSTR& bstrSrc) const throw();
bool operator<(LPCOLESTR pszSrc) const throw();
bool operator<(LPCSTR pszSrc) const throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します**true**比較対象のアイテムの場合よりも低い`CComBSTR`オブジェクト。 それ以外の場合、返されます**false**します。  
  
### <a name="remarks"></a>コメント  
 ユーザーの既定のロケールを使用して比較を実行します。  
  
##  <a name="a-nameoperatoreqa--ccombstroperator-"></a><a name="operator_eq"></a>CComBSTR::operator =  
 セット、 [m_str](#m_str)メンバーのコピーを`pSrc`またはのコピーを`BSTR`のメンバー *src*します。 移動代入演算子を移動`src`コピーせずします。   
  
```
CComBSTR& operator= (const CComBSTR& src);  
CComBSTR& operator= (LPCOLESTR pSrc);  
CComBSTR& operator= (LPCSTR pSrc);
CComBSTR& operator= (CComBSTR&& src) throw(); // (Visual Studio 2017)
```  
  
### <a name="remarks"></a>コメント  
 `pSrc`パラメーターを指定するか、 **LPCOLESTR**の Unicode バージョンまたは`LPCSTR`ANSI バージョンのです。  
  
### <a name="example"></a>例  
 例を参照してください[CComBSTR::Copy](#copy)します。  
  
##  <a name="a-nameoperatoreqeqa--ccombstroperator-"></a><a name="operator_eq_eq"></a>CComBSTR::operator = =  
 比較、`CComBSTR`文字列を使用します。 `CComBSTR`ユーザーの既定のロケールのコンテキストでは、s がテキストで比較されます。  
  
```
bool operator== (const CComBSTR& bstrSrc) const throw();
bool operator== (LPCOLESTR pszSrc) const;
bool operator== (LPCSTR pszSrc) const;
bool operator== (int nNull) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `bstrSrc`  
 [入力] `CComBSTR` オブジェクト。  
  
 `pszSrc`  
 [in]0 で終わる文字列。  
  
 `nNull`  
 [in]必要があります**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 返します**true**比較対象のアイテムに等しい場合、`CComBSTR`オブジェクト。 それ以外の場合、返す**false**します。  
  
### <a name="remarks"></a>コメント  
 最後の比較演算子には、格納されている文字列だけを比較して**NULL**します。  
  
##  <a name="a-nameoperatorgta--ccombstroperator-gt"></a><a name="operator_gt"></a>CComBSTR::operator&gt;  
 比較、`CComBSTR`文字列を使用します。  
  
```
bool operator>(const CComBSTR& bstrSrc) const throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します**true**比較対象のアイテムがより大きい場合、`CComBSTR`オブジェクト。 それ以外の場合、返す**false**します。  
  
### <a name="remarks"></a>コメント  
 ユーザーの既定のロケールを使用して比較を実行します。  
  
##  <a name="a-namereadfromstreama--ccombstrreadfromstream"></a><a name="readfromstream"></a>CComBSTR::ReadFromStream  
 セット、 [m_str](#m_str)メンバーを`BSTR`指定したストリームに格納します。  
  
```
HRESULT ReadFromStream(IStream* pStream) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pStream`  
 [in]ポインター、 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)データを格納しているストリームのインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 **ReadToStream**への呼び出しで書き出さデータ形式と互換性がある現在の位置にあるストリームの内容を必要と[WriteToStream](#writetostream)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&44;](../../atl/codesnippet/cpp/ccombstr-class_17.cpp)]  
  
##  <a name="a-nametolowera--ccombstrtolower"></a><a name="tolower"></a>CComBSTR::ToLower  
 格納されている文字列を小文字に変換します。  
  
```
HRESULT ToLower() throw();
```  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 参照してください**CharLowerBuff**変換を実行する方法の詳細についてです。  
  
##  <a name="a-nametouppera--ccombstrtoupper"></a><a name="toupper"></a>CComBSTR::ToUpper  
 格納されている文字列を大文字に変換します。  
  
```
HRESULT ToUpper() throw();
```  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 参照してください**CharUpperBuff**変換を実行する方法の詳細についてです。  
  
##  <a name="a-namewritetostreama--ccombstrwritetostream"></a><a name="writetostream"></a>CComBSTR::WriteToStream  
 保存、 [m_str](#m_str)ストリームへのメンバーです。  
  
```
HRESULT WriteToStream(IStream* pStream) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pStream`  
 [in]ポインター、 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)ストリーム上のインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 使用してストリームの内容から BSTR を再作成することができます、 [ReadFromStream](#readfromstream)関数です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&45;](../../atl/codesnippet/cpp/ccombstr-class_18.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [ATL と MFC 文字列変換マクロ](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863)

