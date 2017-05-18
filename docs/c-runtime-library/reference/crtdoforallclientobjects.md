---
title: _CrtDoForAllClientObjects | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtDoForAllClientObjects
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
- _CrtDoForAllClientObjects
- CrtDoForAllClientObjects
- crtdbg/_CrdDoForAllClientObjects
dev_langs:
- C++
helpviewer_keywords:
- _CrtDoForAllClientObjects function
- CrtDoForAllClientObjects function
ms.assetid: d0fdb835-3cdc-45f1-9a21-54208e8df248
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: df96a24b04473099daaca29472f90c9770181e82
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="crtdoforallclientobjects"></a>_CrtDoForAllClientObjects
ヒープ内のすべての `_CLIENT_BLOCK` 型に対して、アプリケーションによって提供される関数を呼び出します (デバッグ バージョンのみ)。  
  
## <a name="syntax"></a>構文  
  
```  
void _CrtDoForAllClientObjects(   
   void ( * pfn )( void *, void * ),  
   void *context  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pfn`  
 アプリケーションによって提供された関数コールバック関数へのポインター。 この関数の最初のパラメーターは、データを指します。 2 番目のパラメーターは、 `_CrtDoForAllClientObjects`の呼び出しに渡されるコンテキスト ポインターです。  
  
 `context`  
 アプリケーションによって提供される関数に渡す、アプリケーションによって提供されるコンテキストへのポインター。  
  
## <a name="remarks"></a>コメント  
 `_CrtDoForAllClientObjects` 関数は、ヒープのリンク リストで `_CLIENT_BLOCK` 型のメモリ ブロックを検索し、この型のブロックがある場合は、アプリケーションによって提供される関数を呼び出します。 見つかったブロックと `context` パラメーターは、アプリケーションによって提供される関数に引数として渡されます。 デバッグ中に、アプリケーションはメモリを割り当てるためのデバッグ ヒープ関数を明示的に呼び出し、ブロックに `_CLIENT_BLOCK` ブロック型を割り当てるように指定することによって、割り当ての特定のグループを追跡できます。 これらのブロックは個別に追跡し、リーク検出やメモリ状態のレポート時に異なる方法で報告できます。  
  
 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) フラグの `_CRTDBG_ALLOC_MEM_DF` ビット フィールドがオンでない場合、`_CrtDoForAllClientObjects` はすぐに制御を返します。 [_DEBUG](../../c-runtime-library/debug.md) が定義されていない場合、`_CrtDoForAllClientObjects` の呼び出しは前処理で削除されます。  
  
 `_CLIENT_BLOCK` 型と、それが他のデバッグ関数によってどのように使用されるかの詳細については、「[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。  
  
 `pfn` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は [errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) を `EINVAL` に設定して処理を戻します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_CrtDoForAllClientObjects`|\<crtdbg.h>、\<errno.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
 **ライブラリ:** ユニバーサル C ランタイム ライブラリのデバッグ バージョンのみ。  
  
## <a name="see-also"></a>関連項目  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)   
 [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)   
 [ヒープ状態レポート関数](/visualstudio/debugger/crt-debug-heap-details)   
 [_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md)
