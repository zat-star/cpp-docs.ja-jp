---
title: "_bstr_t::operator + =、+ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::operator+
- _bstr_t::operator+=
dev_langs: C++
helpviewer_keywords:
- += operator [C++], appending strings
- + operator [C++], _bstr_t objects
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1ceeec1461b05b25d4bb0b42321cb9b3988ce4b0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="bstrtoperator--"></a>_bstr_t::operator +=、+
**Microsoft 固有の仕様**  
  
 `_bstr_t` オブジェクトの末尾に文字を追加するか、2 つの文字列を連結します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      _bstr_t& operator+=(  
   const _bstr_t& s1   
);  
_bstr_t operator+(  
   const _bstr_t& s1   
);  
friend _bstr_t operator+(  
   const char* s2,  
   const _bstr_t& s1   
);  
friend _bstr_t operator+(  
   const wchar_t* s3,  
   const _bstr_t& s1   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *s1*  
 `_bstr_t` オブジェクト。  
  
 *s2*  
 マルチバイト文字列。  
  
 `s3`  
 Unicode 文字列。  
  
## <a name="remarks"></a>コメント  
 これらの演算子は文字列連結を実行します。  
  
-   **演算子 + = (***s1***)**でカプセル化された文字を追加`BSTR`の*s1*このオブジェクトのカプセル化されたの末尾に`BSTR`.  
  
-   **operator + (***s1***)**新しいを返します`_bstr_t`は、このオブジェクトを連結して形成される`BSTR`の*s1*です。  
  
-   **operator + (***s2***&#124;***s1***)**新しいを返します`_bstr_t`マルチバイト文字列の連結によって形成される*s2*を Unicode に変換された、使用、 `BSTR`内のカプセル化された*s1*です。  
  
-   **operator + (** `s3` **、***s1***)**新しいを返します`_bstr_t`Unicode 文字列を連結して形成する`s3``BSTR`にカプセル化された*s1*です。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [_bstr_t クラス](../cpp/bstr-t-class.md)