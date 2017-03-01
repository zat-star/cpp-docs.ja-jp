---
title: _CrtDumpMemoryLeaks | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtDumpMemoryLeaks
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
- CRTDBG_LEAK_CHECK_DF
- CRTDBG_CHECK_CRT_DF
- _CRTDBG_LEAK_CHECK_DF
- CrtDumpMemoryLeaks
- _CrtDumpMemoryLeaks
- _CRTDBG_CHECK_CRT_DF
dev_langs:
- C++
helpviewer_keywords:
- CrtDumpMemoryLeaks function
- CRTDBG_LEAK_CHECK_DF macro
- _CRTDBG_LEAK_CHECK_DF macro
- _CrtDumpMemoryLeaks function
- CRTDBG_CHECK_CRT_DF macro
- _CRTDBG_CHECK_CRT_DF macro
ms.assetid: 71b2eab4-7f55-44e8-a55a-bfea4f32d34c
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 3fca6935525d9654c7f78f81e879497fc3e0e5af
ms.lasthandoff: 02/24/2017

---
# <a name="crtdumpmemoryleaks"></a>_CrtDumpMemoryLeaks
メモリ リークが発生したときに、デバッグ ヒープ内のすべてのメモリ ブロックをダンプします (デバッグ バージョンのみ)。  
  
## <a name="syntax"></a>構文  
  
```  
  
int _CrtDumpMemoryLeaks( void );  
```  
  
## <a name="return-value"></a>戻り値  
 `_CrtDumpMemoryLeaks` は、メモリ リークが見つかった場合は TRUE を返します。 それ以外の場合、関数は FALSE を返します。  
  
## <a name="remarks"></a>コメント  
 `_CrtDumpMemoryLeaks` 関数は、プログラムの実行開始以降にメモリ リークが発生したかどうかを判定します。 メモリ リークが見つかると、ヒープ内のすべてのオブジェクトのデバッグ ヘッダー情報が、ユーザーが判読できる形式でダンプされます。 [_DEBUG](../../c-runtime-library/debug.md) が定義されていない場合、`_CrtDumpMemoryLeaks` の呼び出しは前処理で削除されます。  
  
 `_CrtDumpMemoryLeaks` は、アプリケーションによって割り当てられたすべてのメモリが解放されたことを確認するために、プログラムの実行終了時に頻繁に呼び出されます。 プログラムの終了時にこの関数が自動的に呼び出されるようにするには、[_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) 関数を使用して、[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) フラグの `_CRTDBG_LEAK_CHECK_DF` ビット フィールドをオンにします。  
  
 `_CrtDumpMemoryLeaks` は [_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) を呼び出してヒープの現在の状態を取得し、解放されていないブロックの状態をスキャンします。 解放されていないブロックが見つかると、`_CrtDumpMemoryLeaks` は [_CrtMemDumpAllObjectsSince](../../c-runtime-library/reference/crtmemdumpallobjectssince.md) を呼び出して、プログラムの実行開始以降にヒープに割り当てられたすべてのオブジェクトについての情報をダンプします。  
  
 既定では、内部 C ランタイム ブロック (`_CRT_BLOCK`) は、メモリ ダンプ操作に含まれません。 これらのブロックをリーク検出プロセスに含めるには、[_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) 関数を使用して、`_crtDbgFlag` の `_CRTDBG_CHECK_CRT_DF` ビットをオンにします。  
  
 ヒープ状態関数と `_CrtMemState` 構造体の詳細については、「[ヒープの状態をレポートする関数](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。 デバッグ バージョンのベース ヒープでのメモリ ブロックの割り当て、初期化、管理の方法について詳しくは、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_CrtDumpMemoryLeaks`|\<crtdbg.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## <a name="example"></a>例  
 `_CrtDumpMemoryLeaks` の使用例については、「[crt_dbg1](http://msdn.microsoft.com/en-us/17b4b20c-e849-48f5-8eb5-dca6509cbaf9)」を参照してください。  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)
