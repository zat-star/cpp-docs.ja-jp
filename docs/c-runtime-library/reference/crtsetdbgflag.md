---
title: _CrtSetDbgFlag | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CrtSetDbgFlag
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
- _CRTDBG_REPORT_FLAG
- _CRTDBG_CHECK_EVERY_16_DF
- _CRTDBG_CHECK_DEFAULT_DF
- CRTDBG_CHECK_DEFAULT_DF
- CRTDBG_CHECK_EVERY_128_DF
- CRTDBG_CHECK_EVERY_1024_DF
- _CRTDBG_CHECK_EVERY_128_DF
- CrtSetDbgFlag
- CRTDBG_CHECK_EVERY_16_DF
- _CRTDBG_CHECK_EVERY_1024_DF
- _CrtSetDbgFlag
- CRTDBG_REPORT_FLAG
dev_langs:
- C++
helpviewer_keywords:
- _CRTDBG_CHECK_EVERY_16_DF macro
- CRTDBG_CHECK_EVERY_16_DF macro
- _CRTDBG_CHECK_ALWAYS_DF macro
- _CRTDBG_CHECK_DEFAULT_DF macro
- CRTDBG_ALLOC_MEM_DF macro
- CRTDBG_CHECK_ALWAYS_DF macro
- _CRTDBG_ALLOC_MEM_DF macro
- _CRTDBG_REPORT_FLAG macro
- _CRTDBG_CHECK_EVERY_128_DF macro
- CRTDBG_REPORT_FLAG macro
- _CRTDBG_CHECK_EVERY_1024_DF macro
- CRTDBG_CHECK_DEFAULT_DF macro
- CRTDBG_CHECK_EVERY_1024_DF macro
- _CrtSetDbgFlag function
- CrtSetDbgFlag function
- _CRTDBG_DELAY_FREE_MEM_DF macro
- CRTDBG_CHECK_EVERY_128_DF macro
- CRTDBG_DELAY_FREE_MEM_DF macro
- CRTDBG_CHECK_CRT_DF macro
- _CRTDBG_CHECK_CRT_DF macro
ms.assetid: b5657ffb-6178-4cbf-9886-1af904ede94c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fb2af7756db37e3c5021894936d801d11705f0c6
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="crtsetdbgflag"></a>_CrtSetDbgFlag
**_crtDbgFlag** フラグの状態を取得または変更して、デバッグ ヒープ マネージャーの割り当て動作を制御します (デバッグ バージョンのみ)。  
  
## <a name="syntax"></a>構文  
  
```  
  
      int _CrtSetDbgFlag(   
   int newFlag   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `newFlag`  
 **_crtDbgFlag** の新しい状態。  
  
## <a name="return-value"></a>戻り値  
 **_crtDbgFlag** の以前の状態を返します。  
  
## <a name="remarks"></a>コメント  
 `_CrtSetDbgFlag` 関数を使用すると、アプリケーションは **_crtDbgFlag** フラグのビット フィールドを変更することによって、デバッグ ヒープ マネージャーがメモリ割り当てを追跡する方法を制御できます。 ビットを設定する (オンにする) ことによって、アプリケーションはデバッグ ヒープ マネージャーに特別なデバッグ操作の実行を指示できます。たとえば、アプリケーション終了時にメモリ リークを確認し、リークを発見した場合に報告したり、解放されたメモリ ブロックをヒープのリンク リストに残すように指定してメモリ不足状況をシミュレーションしたり、すべての割り当て要求時に各メモリ ブロックを検査してヒープの整合性を検証したりすることができます。 [_DEBUG](../../c-runtime-library/debug.md) が定義されていない場合、`_CrtSetDbgFlag` の呼び出しは前処理で削除されます。  
  
 次の表は、**_crtDbgFlag** のビット フィールドと、その動作の説明の一覧です。 ビットを設定すると、診断出力が増加し、プログラムの実行速度が低下するため、これらのビットは既定では設定されていません (オフになっています)。 これらのビット フィールドの詳細については、「[ヒープの状態をレポートする関数](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。  
  
|ビット フィールド|既定値|説明|  
|---------------|-------------|-----------------|  
|**_CRTDBG_ALLOC_MEM_DF**|ON|オン: デバッグ ヒープ割り当てと、`_CLIENT_BLOCK` などのメモリ ブロック型識別子の使用を有効にします。 オフ: ヒープのリンク リストに新しい割り当てを追加しますが、ブロックの型を **_IGNORE_BLOCK** に設定します。<br /><br /> ヒープ頻度チェック マクロのいずれかと組み合わせることもできます。|  
|**_CRTDBG_CHECK_ALWAYS_DF**|OFF|オン: 割り当て要求および解放要求のたびに [_CrtCheckMemory](../../c-runtime-library/reference/crtcheckmemory.md) を呼び出します。 オフ: `_CrtCheckMemory` を明示的に呼び出す必要があります。<br /><br /> このフラグが設定されている場合、ヒープ頻度チェック マクロは効果がありません。|  
|`_CRTDBG_CHECK_CRT_DF`|OFF|オン: リーク検出およびメモリ状態比較の操作に `_CRT_BLOCK` 型を含めます。 オフ: ランタイム ライブラリによって内部的に使用されるメモリは、これらの操作では無視されます。<br /><br /> ヒープ頻度チェック マクロのいずれかと組み合わせることもできます。|  
|**_CRTDBG_DELAY_FREE_MEM_DF**|OFF|オン: 解放されたメモリ ブロックをヒープのリンク リストに保持し、それらに **_FREE_BLOCK** 型を割り当てて、バイト値 0xDD を設定します。 オフ: 解放されたブロックをヒープのリンク リストに保持しません。<br /><br /> ヒープ頻度チェック マクロのいずれかと組み合わせることもできます。|  
|`_CRTDBG_LEAK_CHECK_DF`|OFF|オン: [_CrtDumpMemoryLeaks](../../c-runtime-library/reference/crtdumpmemoryleaks.md) を呼び出すことによってプログラムの終了時に自動リーク チェックを実行し、アプリケーションが割り当てたすべてのメモリを解放できなかった場合はエラー レポートを生成します。 オフ: プログラムの終了時に自動的なリーク チェックを行いません。<br /><br /> ヒープ頻度チェック マクロのいずれかと組み合わせることもできます。|  
  
 **ヒープ頻度チェック マクロ**  
  
 C ランタイム ライブラリがデバッグ ヒープ (`_CrtCheckMemory`) の検証を実行する頻度を、`malloc`、`realloc`、**free**、および `_msize` の呼び出しの数に基づいて指定できます。  
  
 `_CrtSetDbgFlag` は、`newFlag` パラメーターの上位 16 ビットで値を調べます。 指定された値は、`_CrtCheckMemory` の呼び出し間の `malloc`、`realloc`、**free**、および `_msize` の呼び出し数です。 この目的のために、4 つの定義済みマクロが用意されています。  
  
|マクロ|_CrtCheckMemory の呼び出し間の malloc、realloc、free、および _msize の呼び出し数|  
|-----------|------------------------------------------------------------------------------------------|  
|_CRTDBG_CHECK_EVERY_16_DF|16|  
|_CRTDBG_CHECK_EVERY_128_DF|128|  
|_CRTDBG_CHECK_EVERY_1024_DF|1024|  
|_CRTDBG_CHECK_DEFAULT_DF|0 (既定では、ヒープ チェックなし)|  
  
 既定では、`malloc`、`realloc`、**free**、および `_msize` を 1,024 回呼び出すごとに、`_CrtCheckMemory` が 1 回呼び出されます。  
  
 たとえば、次のコードでは、16 個の `malloc`、`realloc`、**free**、および `_msize` 操作ごとのヒープ チェックを指定できます。  
  
```  
#include <crtdbg.h>  
int main( )  
{  
int tmp;  
  
// Get the current bits  
tmp = _CrtSetDbgFlag(_CRTDBG_REPORT_FLAG);  
  
// Clear the upper 16 bits and OR in the desired freqency  
tmp = (tmp & 0x0000FFFF) | _CRTDBG_CHECK_EVERY_16_DF;  
  
// Set the new bits  
_CrtSetDbgFlag(tmp);  
}  
```  
  
 `newFlag` パラメーターの上位 16 ビットは、_CRTDBG_CHECK_ALWAYS_DF が指定されている場合は無視されます。 この場合、`malloc`、`realloc`、**free**、および `_msize` を呼び出すたびに `_CrtCheckMemory` が呼び出されます。  
  
 `newFlag` は **_crtDbgFlag** に適用する新しい状態であり、各ビット フィールドの値の組み合わせです。  
  
### <a name="to-change-one-or-more-of-these-bit-fields-and-create-a-new-state-for-the-flag"></a>これらのビット フィールドを変更して、フラグの新しい状態を作成するには  
  
1.  `_CrtSetDbgFlag` を `newFlag` と同じにして `_CRTDBG_REPORT_FLAG` を呼び出して現在の **_crtDbgFlag** の状態を取得し、返された値を一時変数に格納します。  
  
2.  この一時変数と、対応するビットマスクとの `OR` 演算を行い、ビットをオンにします。ビットマスクは、アプリケーション コードの中ではマニフェスト定数で表されています。  
  
3.  一時変数と、適切なビットマスクのビットごとの **NOT** との **AND** 演算を行い、他のビットをオフにします。  
  
4.  `newFlag` を一時変数に格納されている値と同じにして `_CrtSetDbgFlag` を呼び出すことによって、**_crtDbgFlag** の新しい状態を設定します。  
  
 次のコードは、解放されたメモリ ブロックをヒープのリンク リストに保持することでメモリ不足の状態をシミュレートし、割り当て要求のたびに `_CrtCheckMemory` が呼び出されないようにする方法を示しています。  
  
```  
// Get the current state of the flag  
// and store it in a temporary variable  
int tmpFlag = _CrtSetDbgFlag( _CRTDBG_REPORT_FLAG );  
  
// Turn On (OR) - Keep freed memory blocks in the  
// heap's linked list and mark them as freed  
tmpFlag |= _CRTDBG_DELAY_FREE_MEM_DF;  
  
// Turn Off (AND) - prevent _CrtCheckMemory from  
// being called at every allocation request  
tmpFlag &= ~_CRTDBG_CHECK_ALWAYS_DF;  
  
// Set the new state for the flag  
_CrtSetDbgFlag( tmpFlag );  
```  
  
 メモリ管理とデバッグ ヒープの概要については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。  
  
 `_CrtSetDbgFlag` 関数でフラグを無効にするには、変数と、ビットマスクのビットごとの **NOT** を **AND** 演算する必要があります。  
  
 `newFlag` が有効な値ではない場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、この関数によって無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、`_crtDbgFlag` の以前の状態を返します。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_CrtSetDbgFlag`|\<crtdbg.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## <a name="example"></a>例  
  
```  
// crt_crtsetdflag.c  
// compile with: /c -D_DEBUG /MTd -Od -Zi -W3 /link -verbose:lib /debug  
/*  
 * This program concentrates on allocating and freeing memory  
 * blocks to test the functionality of the _crtDbgFlag flag..  
 */  
  
#include <string.h>  
#include <malloc.h>  
#include <crtdbg.h>  
  
int main( )  
{  
        char *p1, *p2;  
        int tmpDbgFlag;  
  
        _CrtSetReportMode( _CRT_ERROR, _CRTDBG_MODE_FILE );  
        _CrtSetReportFile( _CRT_ERROR, _CRTDBG_FILE_STDERR );  
        /*  
         * Set the debug-heap flag to keep freed blocks in the  
         * heap's linked list - This will allow us to catch any  
         * inadvertent use of freed memory  
         */  
        tmpDbgFlag = _CrtSetDbgFlag(_CRTDBG_REPORT_FLAG);  
        tmpDbgFlag |= _CRTDBG_DELAY_FREE_MEM_DF;  
        tmpDbgFlag |= _CRTDBG_LEAK_CHECK_DF;  
        _CrtSetDbgFlag(tmpDbgFlag);  
  
        /*  
         * Allocate 2 memory blocks and store a string in each  
         */  
        p1 = malloc( 34 );  
        p2 = malloc( 38 );  
        strcpy_s( p1, 34, "p1 points to a Normal allocation block" );  
        strcpy_s( p2, 38, "p2 points to a Client allocation block" );  
  
        /*  
         * Free both memory blocks  
         */  
        free( p2 );  
        free( p1 );  
  
        /*  
         * Set the debug-heap flag to no longer keep freed blocks in the  
         * heap's linked list and turn on Debug type allocations (CLIENT)  
         */  
        tmpDbgFlag = _CrtSetDbgFlag(_CRTDBG_REPORT_FLAG);  
        tmpDbgFlag |= _CRTDBG_ALLOC_MEM_DF;  
        tmpDbgFlag &= ~_CRTDBG_DELAY_FREE_MEM_DF;  
        _CrtSetDbgFlag(tmpDbgFlag);  
  
        /*  
         * Explicitly call _malloc_dbg to obtain the filename and   
         * line number of our allocation request and also so we can   
         * allocate CLIENT type blocks specifically for tracking  
         */  
        p1 = _malloc_dbg( 40, _NORMAL_BLOCK, __FILE__, __LINE__ );  
        p2 = _malloc_dbg( 40, _CLIENT_BLOCK, __FILE__, __LINE__ );  
        strcpy_s( p1, 40, "p1 points to a Normal allocation block" );  
        strcpy_s( p2, 40, "p2 points to a Client allocation block" );  
  
        /*  
         * _free_dbg must be called to free the CLIENT block  
         */  
        _free_dbg( p2, _CLIENT_BLOCK );  
        free( p1 );  
  
        /*  
         * Allocate p1 again and then exit - this will leave unfreed  
         * memory on the heap  
         */  
        p1 = malloc( 10 );  
}  
```  
  
## <a name="see-also"></a>参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)   
 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)   
 [_CrtCheckMemory](../../c-runtime-library/reference/crtcheckmemory.md)