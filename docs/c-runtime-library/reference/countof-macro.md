---
title: "_countof マクロ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_countof"
  - "countof"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_countof マクロ"
  - "countof マクロ"
ms.assetid: 86198767-f7e5-4beb-898d-3cbbf60350a3
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _countof マクロ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

静的に割り当てられた配列内の要素の数を計算します。  
  
## 構文  
  
```  
size_t _countof(   
   array  
);  
```  
  
#### パラメーター  
 `array`  
 配列の名前。  
  
## 戻り値  
 配列内の要素の数 \(`size_t` で表現\)。  
  
## 解説  
 `array` がポインターではなく、実際に配列であることを確認します。  C では、`array` がポインターである場合、`_countof` は間違った結果を生成します。  C\+\+ では、`array` がポインターである場合、`_countof` はコンパイルに失敗します。  
  
## 必要条件  
  
|マクロ|必須ヘッダー|  
|---------|------------|  
|`_countof`|\<stdlib.h\>|  
  
## 使用例  
  
```  
// crt_countof.cpp  
#define _UNICODE  
#include <stdio.h>  
#include <stdlib.h>  
#include <tchar.h>  
  
int main( void )  
{  
   _TCHAR arr[20], *p;  
   printf( "sizeof(arr) = %zu bytes\n", sizeof(arr) );  
   printf( "_countof(arr) = %zu elements\n", _countof(arr) );  
   // In C++, the following line would generate a compile-time error:  
   // printf( "%zu\n", _countof(p) ); // error C2784 (because p is a pointer)  
  
   _tcscpy_s( arr, _countof(arr), _T("a string") );  
   // unlike sizeof, _countof works here for both narrow- and wide-character strings  
}  
```  
  
  **sizeof\(arr\) \= 40 bytes**  
**\_countof\(arr\) \= 20 elements**   
## 参照  
 [sizeof 演算子](../../cpp/sizeof-operator.md)