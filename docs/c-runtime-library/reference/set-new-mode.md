---
title: "_set_new_mode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_new_mode"
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
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "set_new_mode"
  - "_set_new_mode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_new_mode 関数"
  - "ハンドラー モード"
  - "set_new_mode 関数"
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _set_new_mode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`malloc`の new ハンドラー モードを設定します。  
  
## 構文  
  
```  
int _set_new_mode(  
   int newhandlermode   
);  
```  
  
#### パラメーター  
 `newhandlermode`  
 `malloc`の New ハンドラー モード; 有効な値は 0 または 1.です。  
  
## 戻り値  
 `malloc`に設定される前のハンドラーのモードを返します。  戻り値 1 は、メモリの割り当てに失敗 `malloc` が前に new ハンドラー ルーチンを呼び出すことを示します; 戻り値 0 はことを示します。  `newhandlermode` の引数が 0 または 1 と等しい場合、–1 を返します。  
  
## 解説  
 C\+\+ `_set_new_mode` 関数のセット [malloc](../../c-runtime-library/reference/malloc.md)の new ハンドラー モード。  新しいハンドラー モードは、エラーが発生したときに、`malloc` が [\_set\_new\_handler](../Topic/_set_new_handler.md) によって設定された新しいハンドラー ルーチンを呼び出すかどうかを指定します。  既定では、`malloc` は、メモリの割り当てエラーの際に新しいハンドラー ルーチンを呼び出しません。  この既定の動作をオーバーライドすると、`malloc` がメモリの割り当てに失敗したときに、`new` 演算子が同じ理由で失敗したときと同じ方法で、`malloc` によって新しいハンドラー ルーチンを呼び出すことができます。  詳細については、" *C\+\+ Language Reference*" [new](../../cpp/new-operator-cpp.md) と [削除](../../cpp/delete-operator-cpp.md) の演算子"を参照してください。  既定の名前をオーバーライドするには、ODBC API 関数:  
  
```  
_set_new_mode(1)  
```  
  
 高速 Newmode.obj のプログラムまたはリンク \([リンク オプション](../Topic/Link%20Options.md)を参照してください。  
  
 この関数は、そのパラメーターを検証します。  `newhandlermode` が 0 または 1 以外の場合、関数は [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、無効なパラメーター ハンドラーを呼び出します。  実行の継続 \#\#\#\_`set_new_mode` は \-1 を返し、`EINVAL`に `errno` を設定します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_set_new_mode`|\<new.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_query\_new\_handler](../../c-runtime-library/reference/query-new-handler.md)   
 [\_query\_new\_mode](../../c-runtime-library/reference/query-new-mode.md)