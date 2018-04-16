---
title: "_variant_t::_variant_t |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::_variant_t
dev_langs:
- C++
helpviewer_keywords:
- _variant_t class [C++], constructor
- _variant_t method [C++]
ms.assetid: a50e5b33-d4c6-4a26-8e7e-a0a25fd9895b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cd85a54e9f73352894f6575051fe1ea8be0698fb
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2018
---
# <a name="varianttvariantt"></a>_variant_t::_variant_t
**Microsoft 固有の仕様**  
  
 `_variant_t` オブジェクトを構築します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      _variant_t( ) throw( );  
  
_variant_t(  
   const VARIANT& varSrc   
);  
  
_variant_t(  
   const VARIANT* pVarSrc   
);  
  
_variant_t(  
   const _variant_t& var_t_Src   
);  
  
_variant_t(  
   VARIANT& varSrc,  
   bool fCopy   
);  
  
_variant_t(  
   short sSrc,  
   VARTYPE vtSrc = VT_I2   
);  
  
_variant_t(  
   long lSrc,  
   VARTYPE vtSrc = VT_I4   
);  
  
_variant_t(  
   float fltSrc   
) throw( );  
  
_variant_t(  
   double dblSrc,  
   VARTYPE vtSrc = VT_R8   
);  
  
_variant_t(  
   const CY& cySrc   
) throw( );  
  
_variant_t(  
   const _bstr_t& bstrSrc   
);  
  
_variant_t(  
   const wchar_t *wstrSrc   
);  
  
_variant_t(  
   const char* strSrc   
);  
  
_variant_t(  
   IDispatch* pDispSrc,  
   bool fAddRef = true   
) throw( );  
  
_variant_t(  
   bool bSrc   
) throw( );  
  
_variant_t(  
   IUnknown* pIUknownSrc,  
   bool fAddRef = true   
) throw( );  
  
_variant_t(  
   const DECIMAL& decSrc   
) throw( );  
  
_variant_t(  
   BYTE bSrc   
) throw( );  
  
variant_t(  
   char cSrc  
) throw();  
  
_variant_t(  
   unsigned short usSrc  
) throw();  
  
_variant_t(  
   unsigned long ulSrc  
) throw();  
  
_variant_t(  
   int iSrc  
) throw();  
  
_variant_t(  
   unsigned int uiSrc  
) throw();  
  
_variant_t(  
   __int64 i8Src  
) throw();  
  
_variant_t(  
   unsigned __int64 ui8Src  
) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 *varSrc*  
 A**バリアント**新しいにコピーされるオブジェクト`_variant_t`オブジェクト。  
  
 *pVarSrc*  
 ポインター、**バリアント**新しいにコピーされるオブジェクト`_variant_t`オブジェクト。  
  
 *var_t_Src*  
 新しい `_variant_t` オブジェクトにコピーされる `_variant_t` オブジェクト。  
  
 `fCopy`  
 False の場合、指定された**バリアント**を新しいオブジェクトがアタッチされる`_variant_t`によって新しいコピーを作成せずオブジェクト**VariantCopy**です。  
  
 *ISrc、sSrc*  
 新しい `_variant_t` オブジェクトにコピーされる整数値。  
  
 `vtSrc`  
 **VARTYPE**新しい`_variant_t`オブジェクト。  
  
 *fltSrc, dblSrc*  
 新しい `_variant_t` オブジェクトにコピーされる数値。  
  
 `cySrc`  
 A **CY**新しいにコピーされるオブジェクト`_variant_t`オブジェクト。  
  
 `bstrSrc`  
 新しい `_bstr_t` オブジェクトにコピーされる `_variant_t` オブジェクト。  
  
 *strSrc, wstrSrc*  
 新しい `_variant_t` オブジェクトにコピーされる文字列。  
  
 `bSrc`  
 新しい `bool` オブジェクトにコピーされる `_variant_t` 値。  
  
 `pIUknownSrc`  
 COM インターフェイス ポインター、 **VT_UNKNOWN**新しいにカプセル化されるオブジェクト`_variant_t`オブジェクト。  
  
 `pDispSrc`  
 COM インターフェイス ポインター、 **VT_DISPATCH**新しいにカプセル化されるオブジェクト`_variant_t`オブジェクト。  
  
 `decSrc`  
 A **DECIMAL**新しいにコピーされる値`_variant_t`オブジェクト。  
  
 `bSrc`  
 A**バイト**新しいにコピーされる値`_variant_t`オブジェクト。  
  
 `cSrc`  
 新しい `char` オブジェクトにコピーされる `_variant_t` 値。  
  
 *usSrc*  
 A **unsigned short**新しいにコピーされる値`_variant_t`オブジェクト。  
  
 *ulSrc*  
 新しい `unsigned long` オブジェクトにコピーされる `_variant_t` 値。  
  
 `iSrc`  
 新しい `int` オブジェクトにコピーされる `_variant_t` 値。  
  
 *uiSrc*  
 新しい `unsigned int` オブジェクトにコピーされる `_variant_t` 値。  
  
 *i8Src*  
 _ _**Int64**新しいにコピーされる値`_variant_t`オブジェクト。  
  
 *ui8Src*  
 **符号なし _ _int64**新しいにコピーされる値`_variant_t`オブジェクト。  
  
## <a name="remarks"></a>コメント  
  
-   **_variant_t ()** 、空の構築`_variant_t`オブジェクト、`VT_EMPTY`です。  
  
-   **_variant_t( VARIANT&**  *varSrc*  **)** Constructs a `_variant_t` object from a copy of the **VARIANT** object. バリアント型は保持されます。  
  
-   **_variant_t( VARIANT\***  *pVarSrc*  **)** Constructs a `_variant_t` object from a copy of the **VARIANT** object. バリアント型は保持されます。  
  
-   **_variant_t( _variant_t&**  *var_t_Src*  **)** Constructs a `_variant_t` object from another `_variant_t` object. バリアント型は保持されます。  
  
-   **_variant_t( VARIANT&**  *varSrc* **, bool**  `fCopy`  **)** Constructs a `_variant_t` object from an existing **VARIANT** object. 場合`fCopy`は**false**、**バリアント**オブジェクトは、コピーを作成せず、新しいオブジェクトにアタッチされています。  
  
-   **_variant_t( short**  *sSrc* **, VARTYPE**  `vtSrc`  **= VT_I2 )** Constructs a `_variant_t` object of type `VT_I2` or `VT_BOOL` from a **short** integer value. その他の**VARTYPE**結果、`E_INVALIDARG`エラーです。  
  
-   **_variant_t( long**  `lSrc` **, VARTYPE**  `vtSrc`  **= VT_I4 )** Constructs a `_variant_t` object of type `VT_I4`, `VT_BOOL`, or `VT_ERROR` from a **long** integer value. その他の**VARTYPE**結果、`E_INVALIDARG`エラーです。  
  
-   **_variant_t (float**`fltSrc`**)**構築、`_variant_t`型のオブジェクト`VT_R4`から、 **float**数値を指定します。      
  
-   **_variant_t( double**  `dblSrc` **, VARTYPE**  `vtSrc`  **= VT_R8 )** Constructs a `_variant_t` object of type `VT_R8` or `VT_DATE` from a **double** numerical value. その他の**VARTYPE**結果、`E_INVALIDARG`エラーです。  
  
-   **_variant_t( CY&**  `cySrc`  **)** Constructs a `_variant_t` object of type `VT_CY` from a **CY** object.  
  
-   **_variant_t( _bstr_t&**  `bstrSrc`  **)** Constructs a `_variant_t` object of type `VT_BSTR` from a `_bstr_t` object. 新しい `BSTR` を割り当てます。  
  
-   **_variant_t( wchar_t \*** *wstrSrc*  **)** Constructs a `_variant_t` object of type `VT_BSTR` from a Unicode string. 新しい `BSTR` を割り当てます。  
  
-   **_variant_t( char\***  `strSrc`  **)** Constructs a `_variant_t` object of type `VT_BSTR` from a string. 新しい `BSTR` を割り当てます。  
  
-   **_variant_t( bool**  `bSrc`  **)** Constructs a `_variant_t` object of type `VT_BOOL` from a `bool` value.  
  
-   **_variant_t( IUnknown\***  `pIUknownSrc` **, bool**  `fAddRef`  **= true )** Constructs a `_variant_t` object of type **VT_UNKNOWN** from a COM interface pointer. 場合`fAddRef`は**true**、し、`AddRef`への呼び出しの一致するように指定されたインターフェイス ポインターで呼び出されると**リリース**が発生するときに、`_variant_t`オブジェクトは破棄されます。 呼び出すかどうかは**リリース**で指定されたインターフェイス ポインター。 場合`fAddRef`は**false**、指定されたインターフェイス ポインターの所有権をこのコンス トラクター以外の場合は呼び出さないでください**リリース**で指定されたインターフェイス ポインター。  
  
-   **_variant_t( IDispatch\***  `pDispSrc` **, bool**  `fAddRef`  **= true )** Constructs a `_variant_t` object of type **VT_DISPATCH** from a COM interface pointer. 場合`fAddRef`は**true**、し、`AddRef`への呼び出しの一致するように指定されたインターフェイス ポインターで呼び出されると**リリース**が発生するときに、`_variant_t`オブジェクトは破棄されます。 呼び出すかどうかは**リリース**で指定されたインターフェイス ポインター。 場合**fAddRef**が false の場合、このコンス トラクターの所有権を指定されたインターフェイス ポインター以外の場合は呼び出さないでください**リリース**で指定されたインターフェイス ポインター。  
  
-   **_variant_t( DECIMAL&**  `decSrc`  **)** Constructs a `_variant_t` object of type **VT_DECIMAL** from a **DECIMAL** value.  
  
-   **_variant_t( BYTE**  `bSrc`  **)** Constructs a `_variant_t` object of type `VT_UI1` from a **BYTE** value.  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_variant_t クラス](../cpp/variant-t-class.md)