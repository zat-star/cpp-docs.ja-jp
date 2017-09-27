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
- _variant_t._variant_t
dev_langs:
- C++
helpviewer_keywords:
- _variant_t class, constructor
- _variant_t method
ms.assetid: a50e5b33-d4c6-4a26-8e7e-a0a25fd9895b
caps.latest.revision: 7
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 6bd29401970d3beffcac6d29247138aa65d6a338
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

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
  
 *fltSrc、dblSrc*  
 新しい `_variant_t` オブジェクトにコピーされる数値。  
  
 `cySrc`  
 A **CY**新しいにコピーされるオブジェクト`_variant_t`オブジェクト。  
  
 `bstrSrc`  
 新しい `_bstr_t` オブジェクトにコピーされる `_variant_t` オブジェクト。  
  
 *strSrc、wstrSrc*  
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
  
-   **_variant_t (VARIANT &***varSrc***)**構築、`_variant_t`オブジェクトのコピーから、**バリアント**オブジェクト。     バリアント型は保持されます。  
  
-   **_variant_t (VARIANT\****pVarSrc***)**構築、`_variant_t`オブジェクトのコピーから、**バリアント**オブジェクト。     バリアント型は保持されます。  
  
-   **_variant_t (_variant_t &***var_t_Src***)**構築、`_variant_t`から別のオブジェクト`_variant_t`オブジェクト。     バリアント型は保持されます。  
  
-   **_variant_t (VARIANT &***varSrc* **、bool**`fCopy`**)**構築、 `_variant_t` 、既存のオブジェクト**VARIANT**オブジェクト。       場合`fCopy`は**false**、**バリアント**オブジェクトは、コピーを作成せず、新しいオブジェクトにアタッチされています。  
  
-   **_variant_t (短い***sSrc* **、VARTYPE**`vtSrc`**= VT_I2)**構築、`_variant_t`型のオブジェクト`VT_I2`または`VT_BOOL`から、**短い**整数値。       その他の**VARTYPE**結果、`E_INVALIDARG`エラーです。  
  
-   **_variant_t (長い**`lSrc` **、VARTYPE**`vtSrc`**= VT_I4)**構築、`_variant_t`型のオブジェクト`VT_I4`、 `VT_BOOL`、または`VT_ERROR`から、**長い**整数値。       その他の**VARTYPE**結果、`E_INVALIDARG`エラーです。  
  
-   **_variant_t (float**`fltSrc`**)**構築、`_variant_t`型のオブジェクト`VT_R4`から、 **float**数値を指定します。      
  
-   **_variant_t (二重**`dblSrc` **、VARTYPE**`vtSrc`**= VT_R8)**構築、`_variant_t`型のオブジェクト`VT_R8`または`VT_DATE`から**二重**数値を指定します。       その他の**VARTYPE**結果、`E_INVALIDARG`エラーです。  
  
-   **_variant_t (CY (& a)**`cySrc`**)**構築、`_variant_t`型のオブジェクト`VT_CY`から、 **CY**オブジェクト。      
  
-   **_variant_t (_bstr_t &**`bstrSrc`**)**構築、`_variant_t`型のオブジェクト`VT_BSTR`から、`_bstr_t`オブジェクト。     新しい `BSTR` を割り当てます。  
  
-   **_variant_t (wchar_t \* ** *wstrSrc***)**構築、`_variant_t`型のオブジェクト`VT_BSTR`Unicode 文字列。   新しい `BSTR` を割り当てます。  
  
-   **_variant_t (char\***`strSrc`**)**構築、`_variant_t`型のオブジェクト`VT_BSTR`文字列からです。     新しい `BSTR` を割り当てます。  
  
-   **_variant_t (bool**`bSrc`**)**構築、`_variant_t`型のオブジェクト`VT_BOOL`から、`bool`値。      
  
-   **_variant_t (IUnknown\* ** `pIUknownSrc` **、bool**`fAddRef`**= true)**構築、`_variant_t`型のオブジェクト**VT_UNKNOWN** COM インターフェイス ポインターから。       場合`fAddRef`は**true**、し、`AddRef`への呼び出しの一致するように指定されたインターフェイス ポインターで呼び出されると**リリース**が発生するときに、`_variant_t`オブジェクトは破棄されます。 呼び出すかどうかは**リリース**で指定されたインターフェイス ポインター。 場合`fAddRef`は**false**、指定されたインターフェイス ポインターの所有権をこのコンス トラクター以外の場合は呼び出さないでください**リリース**で指定されたインターフェイス ポインター。  
  
-   **_variant_t (IDispatch\* ** `pDispSrc` **、bool**`fAddRef`**= true)**構築、`_variant_t`型のオブジェクト**VT_DISPATCH** COM インターフェイス ポインターから。       場合`fAddRef`は**true**、し、`AddRef`への呼び出しの一致するように指定されたインターフェイス ポインターで呼び出されると**リリース**が発生するときに、`_variant_t`オブジェクトは破棄されます。 呼び出すかどうかは**リリース**で指定されたインターフェイス ポインター。 場合**fAddRef**が false の場合、このコンス トラクターの所有権を指定されたインターフェイス ポインター以外の場合は呼び出さないでください**リリース**で指定されたインターフェイス ポインター。  
  
-   **_variant_t (10 進数 (& a)**`decSrc`**)**構築、`_variant_t`型のオブジェクト**VT_DECIMAL**から、 **DECIMAL**値。      
  
-   **_variant_t (バイト**`bSrc`**)**構築、`_variant_t`型のオブジェクト`VT_UI1`から、**バイト**値。      
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_variant_t クラス](../cpp/variant-t-class.md)
