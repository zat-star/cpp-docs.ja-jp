---
title: _set_new_mode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_new_mode
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_new_mode
- _set_new_mode
dev_langs:
- C++
helpviewer_keywords:
- handler modes
- _set_new_mode function
- set_new_mode function
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
caps.latest.revision: 14
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 069a7dd22950e7ae9826ff2cf8c542025f14facd
ms.lasthandoff: 02/24/2017

---
# <a name="setnewmode"></a>_set_new_mode
`malloc` の新しいハンドラー モードを設定します。  
  
## <a name="syntax"></a>構文  
  
```  
int _set_new_mode(  
   int newhandlermode   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `newhandlermode`  
 `malloc` の新しいハンドラー モード。有効な値は 0 または 1 です。  
  
## <a name="return-value"></a>戻り値  
 `malloc` の以前のハンドラー モードのセットを返します。 戻り値 1 は、メモリの割り当てに失敗したときに、`malloc` が以前新しいハンドラー ルーチンを呼び出したことを示し、戻り値 0 は呼び出さなかったことを示します。 `newhandlermode` 引数が 0 または 1 と等しくない場合は、-1 を返します。  
  
## <a name="remarks"></a>コメント  
 C++ の `_set_new_mode` 関数は [malloc](../../c-runtime-library/reference/malloc.md) の新しいハンドラー モードを設定します。 新しいハンドラー モードは、エラーが発生したときに、`malloc` が [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md) によって設定された新しいハンドラー ルーチンを呼び出すかどうかを指定します。 既定では、`malloc` は、メモリの割り当てエラーの際に新しいハンドラー ルーチンを呼び出しません。 この既定の動作をオーバーライドすると、`malloc` がメモリの割り当てに失敗したときに、`malloc` 演算子が同じ理由で失敗したときと同じ方法で、`new` によって新しいハンドラー ルーチンを呼び出すことができます。 詳細については、*C++ 言語リファレンス*の「[new](../../cpp/new-operator-cpp.md) および [delete](../../cpp/delete-operator-cpp.md) 演算子」の説明をご覧ください。 既定の動作をオーバーライドするには、次の関数を呼び出します。  
  
```  
_set_new_mode(1)  
```  
  
 この呼び出しはプログラムの最初の方で指定するか、Newmode.obj にリンクします (「[リンク オプション](../../c-runtime-library/link-options.md)」を参照してください)。  
  
 この関数は、そのパラメーターを検証します。 `newhandlermode` が 0 または 1 以外の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、この関数によって無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、**_**`set_new_mode` は -1 を返し、`errno` を `EINVAL` に設定します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_set_new_mode`|\<new.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_query_new_handler](../../c-runtime-library/reference/query-new-handler.md)   
 [_query_new_mode](../../c-runtime-library/reference/query-new-mode.md)
