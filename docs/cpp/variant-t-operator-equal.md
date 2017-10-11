---
title: "_variant_t::operator = |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= [C++], variant
- operator = [C++], variant
- = operator [C++], with specific Visual C++ objects
ms.assetid: 77622723-6e49-4dec-9e0f-fa74028f1a3c
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 850562235442ef8fed4f7b130948a5e92b15a1fb
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="varianttoperator-"></a>_variant_t::operator =
**Microsoft 固有の仕様**  
  
## <a name="syntax"></a>構文  
  
```  
  
      _variant_t& operator=(  
   const VARIANT& varSrc   
);  
  
_variant_t& operator=(  
   const VARIANT* pVarSrc   
);  
  
_variant_t& operator=(  
   const _variant_t& var_t_Src   
);  
  
_variant_t& operator=(  
   short sSrc   
);  
  
_variant_t& operator=(  
   long lSrc   
);  
  
_variant_t& operator=(  
   float fltSrc   
);  
  
_variant_t& operator=(  
   double dblSrc   
);  
  
_variant_t& operator=(  
   const CY& cySrc   
);  
  
_variant_t& operator=(  
   const _bstr_t& bstrSrc   
);  
  
_variant_t& operator=(  
   const wchar_t* wstrSrc   
);  
  
_variant_t& operator=(  
   const char* strSrc   
);  
  
_variant_t& operator=(  
   IDispatch* pDispSrc   
);  
  
_variant_t& operator=(  
   bool bSrc   
);  
  
_variant_t& operator=(  
   IUnknown* pSrc   
);  
  
_variant_t& operator=(  
   const DECIMAL& decSrc   
);  
  
_variant_t& operator=(  
   BYTE bSrc   
);  
  
_variant_t& operator=(  
   char cSrc  
);  
  
_variant_t& operator=(  
   unsigned short usSrc  
);  
  
_variant_t& operator=(  
   unsigned long ulSrc  
);  
  
_variant_t& operator=(  
   int iSrc  
);  
  
_variant_t& operator=(  
   unsigned int uiSrc  
);  
  
_variant_t& operator=(  
   __int64 i8Src  
);  
  
_variant_t& operator=(  
   unsigned __int64 ui8Src  
);  
```  
  
## <a name="remarks"></a>コメント  
 この演算子は、`_variant_t` オブジェクトに新しい値を代入します。  
  
-   **演算子 = = (***varSrc***)**既存を割り当てます**バリアント**を`_variant_t`オブジェクト。      
  
-   **演算子 = = (***pVarSrc***)**既存を割り当てます**バリアント**を`_variant_t`オブジェクト。      
  
-   **演算子 = = (***var_t_Src***)**既存割り当てます`_variant_t`オブジェクトを`_variant_t`オブジェクト。      
  
-   **演算子 = = (***sSrc***)**割り当てます、**短い**整数値を`_variant_t`オブジェクト。      
  
-   **演算子 = (**`lSrc`**)**割り当てます、**長い**整数値を`_variant_t`オブジェクト。      
  
-   **演算子 = = (***fltSrc***)**割り当てます、 **float**する数値を指定、`_variant_t`オブジェクト。      
  
-   **演算子 = = (***dblSrc***)**割り当てます、**二重**する数値を指定、`_variant_t`オブジェクト。      
  
-   **演算子 = = (***cySrc***)**割り当てます、 **CY**オブジェクトを`_variant_t`オブジェクト。      
  
-   **演算子 = = (***bstrSrc***)**割り当てます、`BSTR`オブジェクトを`_variant_t`オブジェクト。      
  
-   **演算子 = = (***wstrSrc***)**に Unicode 文字列を割り当てます、`_variant_t`オブジェクト。      
  
-   **演算子 = = (**`strSrc`**)**にマルチバイト文字列を割り当てます、`_variant_t`オブジェクト。      
  
-   **演算子 = = (** `bSrc` **)**割り当てます、`bool`値を`_variant_t`オブジェクト。    
  
-   **演算子 = = (***pDispSrc***)**割り当てます、 **VT_DISPATCH**オブジェクトを`_variant_t`オブジェクト。      
  
-   **演算子 = = (***pIUnknownSrc***)**割り当てます、 **VT_UNKNOWN**オブジェクトを`_variant_t`オブジェクト。      
  
-   **演算子 = = (***decSrc***)**割り当てます、 **10 進**値を`_variant_t`オブジェクト。      
  
-   **演算子 = = (** `bSrc` **)**割り当てます、**バイト**値を`_variant_t`オブジェクト。    
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_variant_t クラス](../cpp/variant-t-class.md)
