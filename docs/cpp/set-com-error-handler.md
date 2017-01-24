---
title: "_set_com_error_handler | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_com_error_handler 関数"
ms.assetid: 49fe4fca-5e37-4d83-abaf-15be5ce37f94
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _set_com_error_handler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 COM のエラー処理に使用する既定の関数を置き換えます。  
  
## 構文  
  
```  
void __stdcall _set_com_error_handler(  
   void (__stdcall *pHandler)(  
      HRESULT hr,   
      IErrorInfo* perrinfo  
   )  
);  
```  
  
#### パラメーター  
 `pHandler`  
 置換する関数へのポインター。  
  
 `hr`  
 `HRESULT` 情報。  
  
 `perrinfo`  
 `IErrorInfo` オブジェクト。  
  
## 解説  
 既定では、[\_com\_raise\_error](../cpp/com-raise-error.md) は、すべての COM エラーを処理します。  この動作は、`_set_com_error_handler` で独自のエラー処理関数を呼び出すことで変更できます。  
  
 置換関数には `_com_raise_error` のシグネチャと等価のシグニチャが必要です。  
  
## 使用例  
  
```  
// _set_com_error_handler.cpp  
// compile with /EHsc  
#include <stdio.h>  
#include <comdef.h>  
#include <comutil.h>  
  
// Importing ado dll to attempt to establish an ado connection.  
// Not related to _set_com_error_handler   
#import "C:\Program Files\Common Files\System\ado\msado15.dll" no_namespace rename("EOF", "adoEOF")  
  
void __stdcall _My_com_raise_error(HRESULT hr, IErrorInfo* perrinfo)  
{  
   throw "Unable to establish the connection!";  
}  
  
int main()  
{  
   _set_com_error_handler(_My_com_raise_error);  
   _bstr_t bstrEmpty(L"");  
   _ConnectionPtr Connection = NULL;  
   try  
   {  
      Connection.CreateInstance(__uuidof(Connection));  
      Connection->Open(bstrEmpty, bstrEmpty, bstrEmpty, 0);   
   }  
   catch(char* errorMessage)  
   {  
      printf("Exception raised: %s\n", errorMessage);  
   }  
  
   return 0;  
}  
```  
  
  **Exception raised: Unable to establish the connection\!**   
## 必要条件  
 **ヘッダー:** comdef.h  
  
 **Lib:** "wchar\_t をネイティブ型として認識" のコンパイラ オプションが有効な場合は、comsuppw.lib または comsuppwd.lib を使用します。  "wchar\_t をネイティブ型として認識" の設定が無効になっている場合は、comsupp.lib を使用します。  詳細については、「[\/Zc:wchar\_t \(wchar\_t をネイティブ型として認識\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)」を参照してください。  
  
## 参照  
 [コンパイラ COM のグローバル関数](../cpp/compiler-com-global-functions.md)