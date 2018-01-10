---
title: "_alloca |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _alloca
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
apitype: DLLExport
f1_keywords:
- _alloca
- alloca
dev_langs: C++
helpviewer_keywords:
- memory allocation, stack
- alloca function
- _alloca function
ms.assetid: 74488eb1-b71f-4515-88e1-cdd03b6f8225
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a48b0ab3e9717416736acf4187a27df2c737089b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="alloca"></a>_alloca
スタックにメモリを割り当てます。 安全なバージョンがあるために、この関数は推奨されていません参照してください[_malloca](../../c-runtime-library/reference/malloca.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
void *_alloca(   
   size_t size   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `size`  
 スタックから割り当てられるバイト数。  
  
## <a name="return-value"></a>戻り値  
 `_alloca` ルーチンは割り当てられた領域への `void` ポインターを返します。この領域は、任意の種類のオブジェクトを格納できるよう適切に整列されていることが保証されています。 `size` が 0 の場合、`_alloca` 関数は長さが 0 の項目を割り当て、その項目への有効なポインターを返します。  
  
 領域の割り当てができない場合、スタック オーバーフロー例外が生成されます。 スタック オーバーフロー例外は C++ 例外ではなく、構造化例外です。 C++ 例外処理を使用する代わりに、[構造化例外処理](../../cpp/structured-exception-handling-c-cpp.md) (SEH) を使用する必要があります。  
  
## <a name="remarks"></a>コメント  
 `_alloca`割り当てる`size`はプログラム スタックからのバイト数。 割り当てられた領域はときではなく、割り当てがスコープ外に渡すだけ)、呼び出し元の関数が終了したときに自動的に解放されます。 そのため、によって返されるポインター値を渡していない`_alloca`への引数として[空き](../../c-runtime-library/reference/free.md)です。  
  
 例外ハンドラー (EH) で `_alloca` を明示的に呼び出す場合は制限があります。 x86 クラスのプロセッサで動作する EH ルーチンは、自身のメモリ フレーム内で処理されるため、外側の関数のスタック ポインターが示す現在位置を基にしたメモリ領域ではタスクを実行しません。 最も一般的な実装には、Windows NT 構造化例外処理 (SEH) や C++ catch 句の式などがあります。 このため、次のようなシナリオで `_alloca` を明示的に呼び出すと、呼び出した EH ルーチンへ戻る時点でプログラム エラーとなります。  
  
-   Windows NT SEH 例外フィルター式: `__except` (`_alloca ()` )  
  
-   Windows NT SEH 最終例外ハンドラー: `__finally` {`_alloca ()` }  
  
-   C++ EH catch 句の式  
  
 しかし、`_alloca` を EH ルーチン内から直接呼び出すことや、上にリストされた EH シナリオのいずれかで呼び出されるアプリケーション提供によるコールバックから呼び出すことはできます。  
  
> [!IMPORTANT]
>  Windows XP では、try/catch ブロック内で `_alloca` を呼び出した場合、その catch ブロック内で [_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md) を呼び出す必要があります。  
  
 使用する場合、上記の制限に加えて、[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)オプション、`_alloca`では使用できません`__except`ブロックします。 詳細については、「 [/clr Restrictions](../../build/reference/clr-restrictions.md)」を参照してください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_alloca`|\<malloc.h>|  
  
## <a name="example"></a>例  
  
```  
// crt_alloca.c  
// This program demonstrates the use of  
// _alloca and trapping any exceptions  
// that may occur.  
  
#include <windows.h>  
#include <stdio.h>  
#include <malloc.h>  
  
int main()  
{  
    int     size = 1000;  
    int     errcode = 0;  
    void    *pData = NULL;  
  
    // Note: Do not use try/catch for _alloca,  
    // use __try/__except, since _alloca throws  
    // Structured Exceptions, not C++ exceptions.  
  
    __try {  
        // An unbounded _alloca can easily result in a   
        // stack overflow.  
        // Checking for a size < 1024 bytes is recommended.  
        if (size > 0 && size < 1024)  
        {  
            pData = _alloca( size );  
            printf_s( "Allocated %d bytes of stack at 0x%p",  
                      size, pData);  
        }  
        else  
        {  
            printf_s("Tried to allocate too many bytes.\n");  
        }  
    }  
  
    // If an exception occured with the _alloca function  
    __except( GetExceptionCode() == STATUS_STACK_OVERFLOW )  
    {  
        printf_s("_alloca failed!\n");  
  
        // If the stack overflows, use this function to restore.  
        errcode = _resetstkoflw();  
        if (errcode)  
        {  
            printf_s("Could not reset the stack!\n");  
            _exit(1);  
        }  
    };  
}  
```  
  
```Output  
Allocated 1000 bytes of stack at 0x0012FB50  
```  
  
## <a name="see-also"></a>参照  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md)   
 [_malloca](../../c-runtime-library/reference/malloca.md)