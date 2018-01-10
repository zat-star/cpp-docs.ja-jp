---
title: _CrtSetDumpClient | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtSetDumpClient
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
- _CrtSetDumpClient
- CrtSetDumpClient
dev_langs: C++
helpviewer_keywords:
- _CrtSetDumpClient function
- CrtSetDumpClient function
ms.assetid: f3dd06d0-c331-4a12-b68d-25378d112033
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bf64ca280998ac25adbb380ff8245a0b8eecf797
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="crtsetdumpclient"></a>_CrtSetDumpClient
`_CLIENT_BLOCK` 型のメモリ ブロックをダンプするアプリケーション定義関数をインストールします (デバッグ バージョンのみ)。  
  
## <a name="syntax"></a>構文  
  
```  
  
      _CRT_DUMP_CLIENT _CrtSetDumpClient(   
   _CRT_DUMP_CLIENT dumpClient   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dumpClient`  
 C ランタイム デバッグ メモリ ダンプ プロセスにフックする新しいクライアント定義メモリ ダンプ関数。  
  
## <a name="return-value"></a>戻り値  
 以前に定義されていたクライアント ブロック ダンプ関数を返します。  
  
## <a name="remarks"></a>コメント  
 `_CrtSetDumpClient` 関数を使用すると、アプリケーションは独自の関数をフックして、`_CLIENT_BLOCK` メモリ ブロックに格納されているオブジェクトを C ランタイム デバッグのメモリ ダンプ プロセスにダンプすることができます。 その結果、[_CrtMemDumpAllObjectsSince](../../c-runtime-library/reference/crtmemdumpallobjectssince.md) や [_CrtDumpMemoryLeaks](../../c-runtime-library/reference/crtdumpmemoryleaks.md) などのデバッグ ダンプ関数が `_CLIENT_BLOCK` メモリ ブロックをダンプするたびに、アプリケーションのダンプ関数も呼び出されます。 `_CrtSetDumpClient` を使用すると、アプリケーションは簡単にメモリ リークを検出したり、`_CLIENT_BLOCK` ブロックに格納されているデータの内容の検証やレポートを行うことができます。 [_DEBUG](../../c-runtime-library/debug.md) が定義されていない場合、`_CrtSetDumpClient` の呼び出しは前処理で削除されます。  
  
 `_CrtSetDumpClient` 関数は、`dumpClient` で指定された新しいアプリケーション定義ダンプ関数をインストールし、以前に定義されたダンプ関数を返します。 クライアント ブロック ダンプ関数の例は、次のとおりです。  
  
```  
void DumpClientFunction( void *userPortion, size_t blockSize );  
```  
  
 `userPortion` 引数はメモリ ブロックのユーザー データ部分の先頭へのポインターであり、`blockSize` は割り当てられたメモリ ブロックのサイズをバイト単位で指定します。 クライアント ブロック ダンプ関数は、`void` を返す必要があります。 `_CrtSetDumpClient` に渡されるクライアント ダンプ関数へのポインターは、Crtdbg.h で次のように定義されているように、`_CRT_DUMP_CLIENT` 型です。  
  
```  
typedef void (__cdecl *_CRT_DUMP_CLIENT)( void *, size_t );  
```  
  
 `_CLIENT_BLOCK` 型のメモリ ブロックを操作する関数の詳細については、「[Client ブロック用のフック関数](/visualstudio/debugger/client-block-hook-functions)」を参照してください。 ブロックの型やその細分化された型に関する情報を返すには、[_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md) 関数を使用できます。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_CrtSetDumpClient`|\<crtdbg.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## <a name="see-also"></a>参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)   
 [_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md)   
 [_CrtGetDumpClient](../../c-runtime-library/reference/crtgetdumpclient.md)