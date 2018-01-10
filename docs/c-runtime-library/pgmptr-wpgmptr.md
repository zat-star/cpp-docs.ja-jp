---
title: "_pgmptr、_wpgmptr | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- pgmptr
- _pgmptr
- wpgmptr
- _wpgmptr
dev_langs: C++
helpviewer_keywords:
- wpgmptr function
- _wpgmptr function
- _pgmptr function
- pgmptr function
ms.assetid: 4d44b515-0eff-4136-8bc4-684195f218f5
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e8bf941f5e020a608817919b2819f2d6be023d89
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="pgmptr-wpgmptr"></a>_pgmptr、_wpgmptr
実行可能ファイルのパスです。 非推奨。[_get_pgmptr](../c-runtime-library/reference/get-pgmptr.md) と [_get_wpgmptr](../c-runtime-library/reference/get-wpgmptr.md) を使用してください。  
  
## <a name="syntax"></a>構文  
  
```  
extern char *_pgmptr;  
extern wchar_t *_wpgmptr;  
```  
  
## <a name="remarks"></a>コメント  
 コマンド インタープリター (Cmd.exe) からプログラムを実行すると、`_pgmptr` は実行可能ファイルの完全なパスに自動的に初期化されます。 たとえば、Hello.exe が C:\BIN にあり、C:\BIN がパス内にある場合は、次のように、実行時に `_pgmptr` が C:\BIN\Hello.exe に設定されます。  
  
```  
C> hello   
```  
  
 プログラムがコマンド ラインから実行されない場合は、`_pgmptr` はプログラム名 (ファイルの基本名。ファイル名拡張子を除く)、またはファイル名、相対パス、または完全なパスに初期化される可能性があります。  
  
 `_wpgmptr` は、ワイド文字版の `_pgmptr` で、`wmain` を使用するプログラムで使用されます。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|  
  
## <a name="requirements"></a>必要条件  
  
|変数|必須ヘッダー|  
|--------------|---------------------|  
|`_pgmptr`, `_wpgmptr`|\<stdlib.h>|  
  
## <a name="example"></a>例  
 次のプログラムで、`_pgmptr` の使用方法を示します。  
  
```  
// crt_pgmptr.c  
// compile with: /W3  
// The following program demonstrates the use of _pgmptr.  
//  
#include <stdio.h>  
#include <stdlib.h>  
int main( void )  
{  
   printf("The full path of the executing program is : %Fs\n",   
     _pgmptr); // C4996  
   // Note: _pgmptr is deprecated; use _get_pgmptr instead  
}  
```  
  
 `%Fs` を `%S`に、`main` を `wmain` に変更することで、`_wpgmptr` を使用できます。  
  
## <a name="see-also"></a>参照  
 [グローバル変数](../c-runtime-library/global-variables.md)