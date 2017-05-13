---
title: _malloca | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _malloca
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
- malloca
- _malloca
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, stack
- malloca function
- _malloca function
ms.assetid: 293992df-cfca-4bc9-b313-0a733a6bb936
caps.latest.revision: 27
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 42c7a94bfd864f500892dbdee046a3684d295507
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="malloca"></a>_malloca
スタックにメモリを割り当てます。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_alloca](../../c-runtime-library/reference/alloca.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
void *_malloca(   
   size_t size   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `size`  
 スタックから割り当てられるバイト数。  
  
## <a name="return-value"></a>戻り値  
 `_malloca` ルーチンは割り当てられた領域への `void` ポインターを返します。この領域は、任意の種類のオブジェクトを格納できるよう適切に整列されていることが保証されています。 `size` が 0 の場合、`_malloca` 関数は長さが 0 の項目を割り当て、その項目への有効なポインターを返します。  
  
 領域の割り当てができない場合、スタック オーバーフロー例外が生成されます。 スタック オーバーフロー例外は C++ 例外ではなく、構造化例外です。 C++ 例外処理を使用する代わりに、[構造化例外処理](../../cpp/structured-exception-handling-c-cpp.md) (SEH) を使用する必要があります。  
  
## <a name="remarks"></a>コメント  
 `_malloca` は、要求が `_ALLOCA_S_THRESHOLD` で指定された特定のサイズ (バイト単位) を超えると、プログラム スタックまたはヒープから `size` バイトを割り当てます。 `_malloca` と `_alloca` の違いは、`_alloca` がサイズに関係なく常にスタックで割り当てることです。 `_alloca` で割り当てたメモリは `free` を呼び出して解放する必要がなく、そうすることも許可されていませんが、`_malloca` の場合はそれと異なり、[_freea](../../c-runtime-library/reference/freea.md) を使用してメモリを解放する必要があります。 デバッグ モードでは、`_malloca` は常にヒープからメモリを割り当てます。  
  
 例外ハンドラー (EH) で `_malloca` を明示的に呼び出す場合は制限があります。 x86 クラスのプロセッサで動作する EH ルーチンは、自身のメモリ フレーム内で処理されるため、外側の関数のスタック ポインターが示す現在位置を基にしたメモリ領域ではタスクを実行しません。 最も一般的な実装には、Windows NT 構造化例外処理 (SEH) や C++ catch 句の式などがあります。 このため、次のようなシナリオで `_malloca` を明示的に呼び出すと、呼び出した EH ルーチンへ戻る時点でプログラム エラーとなります。  
  
-   Windows NT SEH 例外フィルター式: `__except` (`_malloca ()` )  
  
-   Windows NT SEH 最終例外ハンドラー: `__finally` {`_malloca ()` }  
  
-   C++ EH catch 句の式  
  
 しかし、`_malloca` を EH ルーチン内から直接呼び出すことや、上にリストされた EH シナリオのいずれかで呼び出されるアプリケーション提供によるコールバックから呼び出すことはできます。  
  
> [!IMPORTANT]
>  Windows XP では、try/catch ブロック内で `_malloca` を呼び出した場合、その catch ブロック内で [_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md) を呼び出す必要があります。  
  
 上記の制限に加え、[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md) オプションを使用する場合は、`__except` ブロックで `_malloca` を使用できません。 詳細については、「[/clr の制約](../../build/reference/clr-restrictions.md)」を参照してください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_malloca`|\<malloc.h>|  
  
## <a name="example"></a>例  
  
```  
// crt_malloca_simple.c  
#include <stdio.h>  
#include <malloc.h>  
  
void Fn()  
{  
   char * buf = (char *)_malloca( 100 );  
   // do something with buf  
   _freea( buf );  
}  
  
int main()  
{  
   Fn();  
}  
```  
  
## <a name="example"></a>例  
  
```  
// crt_malloca_exception.c  
// This program demonstrates the use of  
// _malloca and trapping any exceptions  
// that may occur.  
  
#include <windows.h>  
#include <stdio.h>  
#include <malloc.h>  
  
int main()  
{  
    int     size;  
    int     numberRead = 0;  
    int     errcode = 0;  
    void    *p = NULL;  
    void    *pMarker = NULL;  
  
    while (numberRead == 0)  
    {  
        printf_s("Enter the number of bytes to allocate "  
                 "using _malloca: ");  
        numberRead = scanf_s("%d", &size);  
    }  
  
    // Do not use try/catch for _malloca,  
    // use __try/__except, since _malloca throws  
    // Structured Exceptions, not C++ exceptions.  
  
    __try  
    {  
        if (size > 0)  
        {  
            p =  _malloca( size );  
        }  
        else  
        {  
            printf_s("Size must be a positive number.");  
        }  
        _freea( p );  
    }  
  
    // Catch any exceptions that may occur.  
    __except( GetExceptionCode() == STATUS_STACK_OVERFLOW )  
    {  
        printf_s("_malloca failed!\n");  
  
        // If the stack overflows, use this function to restore.  
        errcode = _resetstkoflw();  
        if (errcode)  
        {  
            printf("Could not reset the stack!");  
            _exit(1);  
        }  
    };  
}  
```  
  
## <a name="input"></a>入力  
  
```  
1000  
```  
  
## <a name="sample-output"></a>出力例  
  
```  
Enter the number of bytes to allocate using _malloca: 1000  
```  
  
## <a name="see-also"></a>関連項目  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md)
