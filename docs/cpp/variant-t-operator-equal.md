---
title: "_variant_t::operator = | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_variant_t.operator="
  - "_variant_t::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "= 演算子, Visual C++ 固有のオブジェクトを使用する"
  - "演算子 =, バリアント"
  - "演算子 =, バリアント"
ms.assetid: 77622723-6e49-4dec-9e0f-fa74028f1a3c
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _variant_t::operator =
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
## 構文  
  
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
  
## 解説  
 この演算子は、`_variant_t` オブジェクトに新しい値を代入します。  
  
-   **operator\=\(**  *varSrc*  **\)** `_variant_t` オブジェクトに既存の **VARIANT** を代入します。  
  
-   **operator\=\(**  *pVarSrc*  **\)** `_variant_t` オブジェクトに既存の **VARIANT** を代入します。  
  
-   **operator\=\(**  *var\_t\_Src*  **\)** `_variant_t` オブジェクトに既存の `_variant_t` オブジェクトを代入します。  
  
-   **operator\=\(**  *sSrc*  **\)** `_variant_t` オブジェクトに **short** 統合値を代入します。  
  
-   **operator\=\(**  `lSrc`  **\)** `_variant_t` オブジェクトに **long** 整数値を代入します。  
  
-   **operator\=\(**  *fltSrc*  **\)** `_variant_t` オブジェクトに **float** 数値を代入します。  
  
-   **operator\=\(**  *dblSrc*  **\)** `_variant_t` オブジェクトに **double** 数値を代入します。  
  
-   **operator\=\(**  *cySrc*  **\)** `_variant_t` オブジェクトに **CY** オブジェクトを代入します。  
  
-   **operator\=\(**  *bstrSrc*  **\)** `_variant_t` オブジェクトに `BSTR` オブジェクトを代入します。  
  
-   **operator\=\(**  *wstrSrc*  **\)** `_variant_t` オブジェクトに Unicode 文字列を代入します。  
  
-   **operator\=\(**  `strSrc`  **\)** `_variant_t` オブジェクトにマルチバイト文字列を代入します。  
  
-   **operator\=\(**  `bSrc` **\)** `_variant_t` オブジェクトに `bool` 値を代入します。  
  
-   **operator\=\(**  *pDispSrc*  **\)** `_variant_t` オブジェクトに **VT\_DISPATCH** オブジェクトを代入します。  
  
-   **operator\=\(**  *pIUnknownSrc*  **\)** `_variant_t` オブジェクトに **VT\_UNKNOWN** オブジェクトを代入します。  
  
-   **operator\=\(**  *decSrc*  **\)** `_variant_t` オブジェクトに **DECIMAL** 値を代入します。  
  
-   **operator\=\(**  `bSrc` **\)** `_variant_t` オブジェクトに **BYTE** 値を代入します。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_variant\_t クラス](../cpp/variant-t-class.md)