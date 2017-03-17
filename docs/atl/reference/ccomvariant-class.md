---
title: "CComVariant クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComVariant
- ATLCOMCLI/ATL::CComVariant
- ATLCOMCLI/ATL::CComVariant::CComVariant
- ATLCOMCLI/ATL::CComVariant::Attach
- ATLCOMCLI/ATL::CComVariant::ChangeType
- ATLCOMCLI/ATL::CComVariant::Clear
- ATLCOMCLI/ATL::CComVariant::Copy
- ATLCOMCLI/ATL::CComVariant::CopyTo
- ATLCOMCLI/ATL::CComVariant::Detach
- ATLCOMCLI/ATL::CComVariant::GetSize
- ATLCOMCLI/ATL::CComVariant::ReadFromStream
- ATLCOMCLI/ATL::CComVariant::SetByRef
- ATLCOMCLI/ATL::CComVariant::WriteToStream
dev_langs:
- C++
helpviewer_keywords:
- VARIANT macro
- CComVariant class
- VARIANT macro, ATL
ms.assetid: 4d31149c-d005-44b5-a509-10f84afa2b61
caps.latest.revision: 26
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
ms.openlocfilehash: 4b01ca9da3d216603ea7efad228735edd1becbd3
ms.lasthandoff: 02/24/2017

---
# <a name="ccomvariant-class"></a>CComVariant クラス
このクラスはラップ、`VARIANT`格納されているデータの種類を示すメンバーを提供する型。  
  
## <a name="syntax"></a>構文  
  
```  
cpp
class CComVariant : public tagVARIANT  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComVariant::CComVariant](#ccomvariant)|コンストラクターです。|  
|[CComVariant:: ~ CComVariant](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComVariant::Attach](#attach)|アタッチ、 **VARIANT**に、`CComVariant`オブジェクトです。|  
|[CComVariant::ChangeType](#changetype)|変換、`CComVariant`オブジェクトを新しい型にします。|  
|[CComVariant::Clear](#clear)|消去、`CComVariant`オブジェクトです。|  
|[CComVariant::Copy](#copy)|コピー、 **VARIANT**に、`CComVariant`オブジェクトです。|  
|[CComVariant::CopyTo](#copyto)|内容をコピー、`CComVariant`オブジェクトです。|  
|[CComVariant::Detach](#detach)|基になるデタッチ**VARIANT**から、`CComVariant`オブジェクトです。|  
|[CComVariant::GetSize](#getsize)|サイズの内容のバイト数で返します、`CComVariant`オブジェクトです。|  
|[CComVariant::ReadFromStream](#readfromstream)|読み込み、 **VARIANT**ストリームからです。|  
|[CComVariant::SetByRef](#setbyref)|初期化、`CComVariant`オブジェクトと設定、 **vt**メンバー **VT_BYREF**します。|  
|[な](#writetostream)|基になる保存**VARIANT**をストリームにします。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|||  
|-|-|  
|[CComVariant::operator](#operator_lt)|示すかどうか、`CComVariant`オブジェクトは、指定よりも小さい値**VARIANT**します。|  
|[CComVariant::operator >](#operator_gt)|示すかどうか、`CComVariant`オブジェクトが、指定よりも大きい**VARIANT**します。|  
|[operator! =](#operator_neq)|示すかどうか、`CComVariant`オブジェクトが、指定したと等しくない**VARIANT**します。|  
|[演算子 =](#operator_eq)|値を代入、`CComVariant`オブジェクトです。|  
|[演算子 = =](#operator_eq_eq)|示すかどうか、`CComVariant`オブジェクトが、指定した**VARIANT**します。|  
  
## <a name="remarks"></a>コメント  
 `CComVariant`ラップ、`VARIANT and VARIANTARG`は共用体と共用体に格納されたデータの種類を示すメンバーの型。 **VARIANT**s は、Automation で通常使用します。  
  
 `CComVariant`派生した、 **VARIANT**入力できるように任意の場所を使用、 **VARIANT**使用できます。 たとえば、使用することができます、 **V_VT**の種類を抽出するマクロ、`CComVariant`またはアクセスすることができます、 **vt**メンバーの場合と直接だけ、 **VARIANT**します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `tagVARIANT`  
  
 `CComVariant`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcomcli.h  
  
##  <a name="attach"></a>CComVariant::Attach  
 現在の内容を消去しても問題ありません、`CComVariant`の内容をコピー オブジェクトを`pSrc`にこのオブジェクトのバリアント型を設定し、`pSrc`に`VT_EMPTY`します。  
  
```
HRESULT Attach(VARIANT* pSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSrc`  
 [in]指す、 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)オブジェクトにアタッチされています。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 保持しているデータの所有権`pSrc`に転送される、`CComVariant`オブジェクトです。  
  
##  <a name="ccomvariant"></a>CComVariant::CComVariant  
 各コンス トラクターがの安全な初期化を処理、`CComVariant`オブジェクトを呼び出して、 `VariantInit` Win32 関数か、オブジェクトの値と種類を渡されるパラメーターに応じてを設定します。  
  
```
CComVariant() throw();
CComVariant(const CComVariant& varSrc);
CComVariant(const VARIANT& varSrc);
CComVariant(LPCOLESTR lpszSrc);
CComVariant(LPCSTR lpszSrc);
CComVariant(bool bSrc);
CComVariant(BYTE nSrc) throw();
CComVariant(int nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned int  nSrc, VARTYPE vtSrc = VT_UI4) throw();
CComVariant(shor  nSrc) throw();
CComVariant(unsigned short nSrc) throw();
CComVariant(long  nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned long  nSrc) throw();
CComVariant(LONGLONG  nSrc) throw();
CComVariant(ULONGLONG  nSrc) throw();
CComVariant(float  fltSrc) throw();
CComVariant(double  dblSrc, VARTYPE vtSrc = VT_R8) throw();
CComVariant(CY  cySrc) throw();
CComVariant(IDispatch* pSrc) throw();
CComVariant(IUnknown* pSrc) throw();
CComVariant(const SAFEARRAY* pSrc);
CComVariant(char  cSrc) throw();
CComVariant(const CComBSTR& bstrSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 *varSrc*  
 [in]`CComVariant`または`VARIANT`初期化に使用される、`CComVariant`オブジェクトです。 コピー元のバリアントの内容は、変換せずに先にコピーされます。  
  
 `lpszSrc`  
 [in]初期化に使用される文字の文字列、`CComVariant`オブジェクトです。 0 で終了ワイド (Unicode) 文字列を渡すことができます、 **LPCOLESTR**バージョンのコンス トラクターまたは ANSI 文字列を`LPCSTR`バージョンです。 いずれの場合、文字列は、Unicode に変換`BSTR`を使用して割り当て**SysAllocString**します。 種類、`CComVariant`オブジェクトなります`VT_BSTR`します。  
  
 `bSrc`  
 [in]`bool`初期化に使用される、`CComVariant`オブジェクトです。 `bool`に変換される、 **VARIANT_BOOL**保存される前にします。 種類、`CComVariant`オブジェクトなります`VT_BOOL`します。  
  
 `nSrc`  
 [in]`int`、**バイト**、**短い**、**長い**、 **LONGLONG**、**使い**、 **unsigned short 型**、 `unsigned long`、または`unsigned int`初期化に使用される、`CComVariant`オブジェクトです。 The type of the `CComVariant` object will be `VT_I4`, `VT_UI1`, `VT_I2`, `VT_I4`, **VT_I8**, **VT_UI8**, **VT_UI2**, **VT_UI4**, or **VT_UI4**, respectively.  
  
 `vtSrc`  
 [in]バリアントの型。 最初のパラメーターの場合は`int`、有効な種類は`VT_I4`と**VT_INT**します。 最初のパラメーターの場合は**長い**、有効な種類は`VT_I4`と`VT_ERROR`です。 最初のパラメーターの場合は**二重**、有効な種類は`VT_R8`と`VT_DATE`です。 最初のパラメーターの場合は`unsigned int`、有効な種類は**VT_UI4**と**VT_UINT**します。  
  
 `fltSrc`  
 [in]**Float**初期化に使用される、`CComVariant`オブジェクトです。 種類、`CComVariant`オブジェクトなります`VT_R4`します。  
  
 `dblSrc`  
 [in]**二重**初期化に使用される、`CComVariant`オブジェクトです。 種類、`CComVariant`オブジェクトなります`VT_R8`します。  
  
 `cySrc`  
 [in]**CY**初期化に使用される、`CComVariant`オブジェクトです。 種類、`CComVariant`オブジェクトなります`VT_CY`します。  
  
 `pSrc`  
 [in]`IDispatch`または**IUnknown**ポインターの初期化に使用される、`CComVariant`オブジェクトです。 `AddRef`インターフェイス ポインターで呼び出されます。 種類、`CComVariant`オブジェクトなります**VT_DISPATCH**または**VT_UNKNOWN**、それぞれします。  
  
 または、 **SAFERRAY**ポインターの初期化に使用される、`CComVariant`オブジェクトです。 コピー、 **SAFEARRAY**に格納されて、`CComVariant`オブジェクトです。 種類、`CComVariant`オブジェクトの元の型の組み合わせになります、 **SAFEARRAY**と**VT_ARRAY**します。  
  
 `cSrc`  
 [in]`char`初期化に使用される、`CComVariant`オブジェクトです。 種類、`CComVariant`オブジェクトなります**VT_I1**します。  
  
 `bstrSrc`  
 [in]初期化に使用される、BSTR、`CComVariant`オブジェクトです。 種類、`CComVariant`オブジェクトなります`VT_BSTR`します。  
  
### <a name="remarks"></a>コメント  
 デストラクターを呼び出して[CComVariant::Clear](#clear)します。  
  
##  <a name="dtor"></a>CComVariant:: ~ CComVariant  
 デストラクターです。  
  
```
~CComVariant() throw();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出してクリーンアップを管理する[CComVariant::Clear](#clear)します。  
  
##  <a name="changetype"></a>CComVariant::ChangeType  
 変換、`CComVariant`オブジェクトを新しい型にします。  
  
```
HRESULT ChangeType(VARTYPE vtNew, const VARIANT* pSrc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `vtNew`  
 [in]新しい型、`CComVariant`オブジェクトです。  
  
 `pSrc`  
 [in]ポインター、`VARIANT`の値は、新しい型に変換されます。 既定値は**NULL**つまり、`CComVariant`オブジェクトはインプレース変換されます。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 値を渡す場合`pSrc`、`ChangeType`がこれを使う**VARIANT**変換のソースとして。 それ以外の場合、`CComVariant`オブジェクトで、ソースになります。  
  
##  <a name="clear"></a>CComVariant::Clear  
 消去、`CComVariant`を呼び出してオブジェクト、 `VariantClear` Win32 関数です。  
  
```
HRESULT Clear();
```  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 デストラクターが自動的に呼び出します**クリア**します。  
  
##  <a name="copy"></a>CComVariant::Copy  
 解放、`CComVariant`オブジェクトし、指定したコピーを割り当てます**VARIANT**します。  
  
```
HRESULT Copy(const VARIANT* pSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSrc`  
 [in]ポインター、 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)をコピーします。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="copyto"></a>CComVariant::CopyTo  
 内容をコピー、`CComVariant`オブジェクトです。  
  
```
HRESULT CopyTo(BSTR* pstrDest);
```  
  
### <a name="parameters"></a>パラメーター  
 *pstrDest*  
 指す、`BSTR`の内容のコピーを受信する、`CComVariant`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 **CComVariant**オブジェクト型でなければなりません`VT_BSTR`します。  
  
##  <a name="detach"></a>CComVariant::Detach  
 基になるデタッチ**VARIANT**から、`CComVariant`オブジェクトおよびオブジェクトの種類を設定`VT_EMPTY`します。  
  
```
HRESULT Detach(VARIANT* pDest);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDest`  
 [out]基になる返します`VARIANT`オブジェクトの値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 内容、`VARIANT`によって参照される`pDest`値と、呼び出し元の型に割り当てられる前に自動的にクリアされます**CComVariant**オブジェクトです。  
  
##  <a name="getsize"></a>CComVariant::GetSize  
 単純な固定サイズの`VARIANT`秒、このメソッドが戻る、`sizeof`基のデータ型が正符号`sizeof(VARTYPE)`します。  
  
```
ULONG GetSize() const;
```  
  
### <a name="return-value"></a>戻り値  
 現在の内容のバイト単位のサイズ、`CComVariant`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 場合、`VARIANT`インターフェイス ポインターを含む`GetSize`クエリ`IPersistStream`または`IPersistStreamInit`です。 成功すると、戻り値がによって返される値の下位 32 ビット`GetSizeMax`加えた`sizeof`、`CLSID`と`sizeof(VARTYPE)`です。 インターフェイス ポインターがある場合`NULL`、`GetSize`返します、 `sizeof` 、 `CLSID` plus`sizeof(VARTYPE)`します。 合計サイズがより大きい場合`ULONG_MAX`、`GetSize`返します`sizeof(VARTYPE)`エラーを示します。  
  
 その他の場合、一時的な`VARIANT`型の`VT_BSTR`は現在の強制変換`VARIANT`します。 この長さ`BSTR`文字列の長さと文字列自体の長さのサイズの正符号の null 文字のサイズの合計として計算されます`sizeof(VARTYPE)`します。 場合、`VARIANT`を強制的に変換できない、`VARIANT`型の`VT_BSTR`、`GetSize`返します`sizeof(VARTYPE)`します。  
  
 このメソッドによって返されるサイズで使用するバイト数に一致する[な](#writetostream)成功の条件下でします。  
  
##  <a name="operator_eq"></a>CComVariant::operator =  
 値と対応する型を割り当て、`CComVariant`オブジェクトです。  
  
```
CComVariant& operator=(const CComVariant& varSrc);
CComVariant& operator=(const VARIANT& varSrc);
CComVariant& operator=(const CComBSTR& bstrSrc);
CComVariant& operator=(LPCOLESTR lpszSrc);
CComVariant& operator=(LPCSTR lpszSrc);
CComVariant& operator=(bool bSrc);
CComVariant& operator=(BYTE nSrc) throw();
CComVariant& operator=int nSrc) throw();
CComVariant& operator=(unsigned int nSrc) throw();
CComVariant& operator=(short nSrc) throw();
CComVariant& operator=(unsigned short nSrc) throw();
CComVariant& operator=(long nSrc) throw();
CComVariant& operator=(unsigned long nSrc) throw();
CComVariant& operator=(LONGLONG nSrc) throw();
CComVariant& operator=(ULONGLONG nSrc) throw();
CComVariant& operator=(float fltSrc) throw();
CComVariant& operator=(double dblSrc) throw();
CComVariant& operator=(CY cySrc) throw();
CComVariant& operator=(IDispatch* pSrc) throw();
CComVariant& operator=(IUnknown* pSrc) throw();
CComVariant& operator=(const SAFEARRAY* pSrc);
CComVariant& operator=(char cSrc) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *varSrc*  
 [in]`CComVariant`または[VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)に割り当てられる、`CComVariant`オブジェクトです。 コピー元のバリアントの内容は、変換せずに先にコピーされます。  
  
 `bstrSrc`  
 [in]BSTR に割り当てられる、`CComVariant`オブジェクトです。 種類、`CComVariant`オブジェクトなります`VT_BSTR`します。  
  
 `lpszSrc`  
 [in]文字の文字列に割り当てられる、`CComVariant`オブジェクトです。 0 で終了ワイド (Unicode) 文字列を渡すことができます、 **LPCOLESTR**演算子または ANSI 文字列のバージョン、`LPCSTR`バージョンです。 いずれの場合、文字列は、Unicode に変換`BSTR`を使用して割り当て**SysAllocString**します。 種類、`CComVariant`オブジェクトなります`VT_BSTR`します。  
  
 `bSrc`  
 [in]`bool`に割り当てられる、`CComVariant`オブジェクトです。 `bool`に変換される、 **VARIANT_BOOL**保存される前にします。 種類、`CComVariant`オブジェクトなります`VT_BOOL`します。  
  
 `nSrc`  
 [in]The `int`, **BYTE**, **short**, **long**, **LONGLONG**, **ULONGLONG**, **unsigned short**, `unsigned long`, or `unsigned int` to be assigned to the `CComVariant` object. The type of the `CComVariant` object will be `VT_I4`, `VT_UI1`, `VT_I2`, `VT_I4`, **VT_I8**, **VT_UI8**, **VT_UI2**, **VT_UI4**, or **VT_UI4**, respectively.  
  
 `fltSrc`  
 [in]**Float**に割り当てられる、`CComVariant`オブジェクトです。 種類、`CComVariant`オブジェクトなります`VT_R4`します。  
  
 `dblSrc`  
 [in]**二重**に割り当てられる、`CComVariant`オブジェクトです。 種類、`CComVariant`オブジェクトなります`VT_R8`します。  
  
 `cySrc`  
 [in]**CY**に割り当てられる、`CComVariant`オブジェクトです。 種類、`CComVariant`オブジェクトなります`VT_CY`します。  
  
 `pSrc`  
 [in]`IDispatch`または**IUnknown**に割り当てられるへのポインター、`CComVariant`オブジェクトです。 `AddRef`インターフェイス ポインターで呼び出されます。 種類、`CComVariant`オブジェクトなります**VT_DISPATCH**または**VT_UNKNOWN**、それぞれします。  
  
 または、 **SAFEARRAY**に割り当てられるへのポインター、`CComVariant`オブジェクトです。 コピー、 **SAFEARRAY**に格納されて、`CComVariant`オブジェクトです。 種類、`CComVariant`オブジェクトの元の型の組み合わせになります、 **SAFEARRAY**と**VT_ARRAY**します。  
  
 `cSrc`  
 [in]割り当てられる char、`CComVariant`オブジェクトです。 種類、`CComVariant`オブジェクトなります**VT_I1**します。  
  
##  <a name="operator_eq_eq"></a>CComVariant::operator = =  
 示すかどうか、`CComVariant`オブジェクトが、指定した**VARIANT**します。  
  
```
bool operator==(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>コメント  
 返します。 **true**場合値と型の*varSrc*値と型に等しく、それぞれの、`CComVariant`オブジェクトです。 それ以外の場合、 **false**します。 演算子では、ユーザーの既定のロケールを使用して、比較を行います。  
  
 演算子は、バリアント型の値のみを比較します。 これは、文字列、整数、および浮動小数点ですがない配列またはレコードを比較します。  
  
##  <a name="operator_neq"></a>CComVariant::operator! =  
 示すかどうか、`CComVariant`オブジェクトが、指定したと等しくない**VARIANT**します。  
  
```
bool operator!=(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>コメント  
 返します。 **true**場合、値または型の*varSrc*が値の型、またはと等しくない、それぞれの、`CComVariant`オブジェクトです。 それ以外の場合、 **false**します。 演算子では、ユーザーの既定のロケールを使用して、比較を行います。  
  
 演算子は、バリアント型の値のみを比較します。 これは、文字列、整数、および浮動小数点ですがない配列またはレコードを比較します。  
  
##  <a name="operator_lt"></a>CComVariant::operator&lt;  
 示すかどうか、`CComVariant`オブジェクトは、指定よりも小さい値**VARIANT**します。  
  
```
bool operator<(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>コメント  
 返します。 **true**場合の値、`CComVariant`オブジェクトがの値より小さい*varSrc*します。 それ以外の場合、 **false**します。 演算子では、ユーザーの既定のロケールを使用して、比較を行います。  
  
##  <a name="operator_gt"></a>CComVariant::operator&gt;  
 示すかどうか、`CComVariant`オブジェクトが、指定よりも大きい**VARIANT**します。  
  
```
bool operator>(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>コメント  
 返します。 **true**場合の値、`CComVariant`オブジェクトがの値より大きい*varSrc*します。 それ以外の場合、 **false**します。 演算子では、ユーザーの既定のロケールを使用して、比較を行います。  
  
##  <a name="readfromstream"></a>CComVariant::ReadFromStream  
 基に**VARIANT**に、 **VARIANT**指定したストリームに含まれています。  
  
```
HRESULT ReadFromStream(IStream* pStream);
```  
  
### <a name="parameters"></a>パラメーター  
 `pStream`  
 [in]ポインター、 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)データを格納しているストリームのインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 **ReadToStream**に対する以前の呼び出しを必要と[WriteToStream](#writetostream)します。  
  
##  <a name="setbyref"></a>CComVariant::SetByRef  
 初期化、`CComVariant`オブジェクトと設定、 **vt**メンバー **VT_BYREF**します。  
  
```
template < typename T >
void SetByRef(T* pT) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 型**VARIANT**など、 `BSTR`、 `int`、または`char`です。  
  
 *pT*  
 ポインターの初期化に使用される、`CComVariant`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 `SetByRef`初期化する関数テンプレートは、`CComVariant`オブジェクトをポインター *pT*し、設定、 **vt**メンバー **VT_BYREF**します。 例:  
  
 [!code-cpp[NVC_ATL_Utilities #&76;](../../atl/codesnippet/cpp/ccomvariant-class_1.cpp)]  
  
##  <a name="writetostream"></a>な  
 基になる保存**VARIANT**をストリームにします。  
  
```
HRESULT WriteToStream(IStream* pStream);
```  
  
### <a name="parameters"></a>パラメーター  
 `pStream`  
 [in]ポインター、 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)ストリーム上のインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
