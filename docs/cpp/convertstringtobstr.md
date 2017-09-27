---
title: "ConvertStringToBSTR |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ConvertStringToBSTR
dev_langs:
- C++
helpviewer_keywords:
- ConvertStringToBSTR function
ms.assetid: 071f9b3b-9643-4e06-a1e5-de96ed15bab2
caps.latest.revision: 11
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
ms.openlocfilehash: 3778f84f152b9ce5dd1121d9cf01d7c1a4472a1e
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="convertstringtobstr"></a>ConvertStringToBSTR
**Microsoft 固有の仕様**  
  
 変換、 **char \* **値を`BSTR`です。  
  
## <a name="syntax"></a>構文  
  
```  
  
      BSTR __stdcall ConvertStringToBSTR(  
   const char* pSrc  
)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pSrc`  
 A **char \* **変数。  
  
## <a name="example"></a>例  
  
```  
// ConvertStringToBSTR.cpp  
#include <comutil.h>  
#include <stdio.h>  
  
#pragma comment(lib, "comsuppw.lib")  
#pragma comment(lib, "kernel32.lib")  
  
int main() {  
   char* lpszText = "Test";  
   printf_s("char * text: %s\n", lpszText);  
  
   BSTR bstrText = _com_util::ConvertStringToBSTR(lpszText);  
   wprintf_s(L"BSTR text: %s\n", bstrText);  
  
   SysFreeString(bstrText);  
}  
```  
  
```Output  
char * text: Test  
BSTR text: Test  
```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** comutil.h  
  
 **Lib:** comsuppw.lib または comsuppwd.lib (を参照してください[/Zc:wchar_t (wchar_t をネイティブ型)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)詳細)  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ COM のグローバル関数](../cpp/compiler-com-global-functions.md)
