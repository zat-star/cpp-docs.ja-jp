---
title: _CrtSetAllocHook | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CrtSetAllocHook
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
- _CrtSetAllocHook
- CrtSetAllocHook
dev_langs:
- C++
helpviewer_keywords:
- _CrtSetAllocHook function
- CrtSetAllocHook function
ms.assetid: 405df37b-2fd1-42c8-83bc-90887f17f29d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f51d5ba216c387ea8f5871d68fcf026ea1749121
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="crtsetallochook"></a>_CrtSetAllocHook
C ランタイム デバッグ メモリ割り当てプロセスにフックして、クライアント定義割り当て関数をインストールします (デバッグ バージョンのみ)。  
  
## <a name="syntax"></a>構文  
  
```  
_CRT_ALLOC_HOOK _CrtSetAllocHook(  
   _CRT_ALLOC_HOOK allocHook   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `allocHook`  
 C ランタイム デバッグ メモリ割り当てプロセスにフックする新しいクライアント定義割り当て関数。  
  
## <a name="return-value"></a>戻り値  
 以前に定義された割り当てフック関数を返します。`NULL` が `allocHook` の場合は、`NULL` を返します。  
  
## <a name="remarks"></a>コメント  
 `_CrtSetAllocHook` は、C ランタイム デバッグ ライブラリのメモリ割り当てプロセスのためにアプリケーションが独自の割り当て関数をフックできるようにします。 そのため、メモリ ブロックの割り当て、再割り当て、または解放を行うためのデバッグ割り当て関数へのすべての呼び出しは、アプリケーションのフック関数への呼び出しをトリガーします。 `_CrtSetAllocHook` はアプリケーションにメモリ不足の状況への対処方法をテストするための簡単な手段、割り当てパターンを調べる機能、および後で分析するために割り当て情報を記録する機会を提供します。 [_DEBUG](../../c-runtime-library/debug.md) が定義されていない場合、`_CrtSetAllocHook` の呼び出しは前処理で削除されます。  
  
 `_CrtSetAllocHook` 関数は、`allocHook` で指定された新しいクライアント定義割り当て関数をインストールし、以前に定義されたフック関数を返します。 次の例は、クライアント定義割り当てフックをどのようにプロトタイプ宣言するかを示しています。  
  
```  
int YourAllocHook( int allocType, void *userData, size_t size, int   
blockType, long requestNumber, const unsigned char *filename, int   
lineNumber);  
```  
  
 `allocType` 引数は、割り当てのフック関数への呼び出しをトリガーする割り当て操作の種類 `(_HOOK_ALLOC`、`_HOOK_REALLOC`、および `_HOOK_FREE`) を指定します。 トリガーする割り当ての種類が `_HOOK_FREE` である場合、`userData` は解放されるメモリ ブロックのユーザー データ セクションへのポインターです。 一方、トリガーする割り当ての種類が `_HOOK_ALLOC` または `_HOOK_REALLOC` である場合は、メモリ ブロックがまだ割り当てられていないため、`userData` は `NULL` です。  
  
 `size` はメモリ ブロックのサイズをバイト数で指定します。`blockType` はメモリ ブロックの種類を示します。`requestNumber` はメモリ ブロックのオブジェクト割り当て順序番号です。また、`filename` と `lineNumber` を使用できる場合、これらはトリガーする割り当て操作が開始されたソース ファイル名と行番号を指定します。  
  
 フック関数は処理の完了後、続行方法を主要な C ランタイム割り当てプロセスに伝えるブール値を返す必要があります。 フック関数が呼び出されなかったかのように主要な割り当てプロセスが続行されるようにする場合、フック関数は `TRUE` を返す必要があります。 このようにすると、元のトリガーする割り当て操作が実行されます。 フック関数は、この実装を使用して、現在の割り当て操作またはデバッグ ヒープの状態に影響を与えずに、後で分析するための割り当て情報を収集および保存できます。  
  
 トリガーする割り当て操作が呼び出されて失敗したかのように主要な割り当てプロセスが続行されるようにする場合、フック関数は `FALSE` を返す必要があります。 フック関数は、この実装を使用して、さまざまなメモリの状況とデバッグ ヒープの状態をシミュレートし、各状況をアプリケーションがどのように処理するかをテストできます。  
  
 フック関数をクリアするには、`NULL` に `_CrtSetAllocHook` を渡します。  
  
 `_CrtSetAllocHook` を他のメモリ管理関数と共に使用する方法と、独自のクライアント定義フック関数を記述する方法の詳細については、「[デバッグ用フック関数の作成](/visualstudio/debugger/debug-hook-function-writing)」を参照してください。  
  
> [!NOTE]
>  `_CrtSetAllocHook` は、`/clr:pure` ではサポートされません。 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で使用されていません。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_CrtSetAllocHook`|\<crtdbg.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## <a name="example"></a>例  
 `_CrtSetAllocHook` の使用例については、「[crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)   
 [_CrtGetAllocHook](../../c-runtime-library/reference/crtgetallochook.md)