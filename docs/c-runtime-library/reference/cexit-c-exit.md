---
title: "_cexit、_c_exit | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _c_exit
- _cexit
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _cexit
- c_exit
- _c_exit
- cexit
dev_langs:
- C++
helpviewer_keywords:
- cleanup operations during processes
- cexit function
- _c_exit function
- _cexit function
- c_exit function
ms.assetid: f3072045-9924-4b1a-9fef-b0dcd6d12663
caps.latest.revision: 12
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
ms.openlocfilehash: a68b803ee7dc444439d7a62f43cf7157e7fbf505
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="cexit-cexit"></a>_cexit、_c_exit
クリーンアップ操作を実行し、プロセスを終了せずに処理を戻します。  
  
## <a name="syntax"></a>構文  
  
```  
void _cexit( void );  
void _c_exit( void );  
```  
  
## <a name="remarks"></a>コメント  
 `_cexit` 関数は、`atexit` と `_onexit`によって登録された関数を後入れ先出し (LIFO) 順に呼び出します。 次に `_cexit` はすべての I/O バッファーをフラッシュし、開いているすべてのストリームを閉じてから戻ります。 `_c_exit` の動作は、`atexit` や `_onexit` を処理またはストリーム バッファーをフラッシュすることなく、呼び出し元プロセスに戻る点を除いて、`_exit` と同じです。 `exit`、`_exit`、`_cexit`、`_c_exit` の動作を次の表に示します。  
  
|関数|動作|  
|--------------|--------------|  
|`exit`|完全な C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードで終了します。|  
|`_exit`|高速な C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードで終了します。|  
|`_cexit`|完全な C ライブラリの終了処理を実行し、呼び出し元に戻りますが、プロセスを終了しません。|  
|`_c_exit`|高速な C ライブラリの終了処理を実行し、呼び出し元に戻りますが、プロセスを終了しません。|  
  
 `_cexit` 関数または `_c_exit` 関数を呼び出す場合、呼び出し時に存在する一時オブジェクトまたは自動オブジェクトのデストラクターは呼び出されません。 自動オブジェクトとは、オブジェクトが静的と宣言されていない関数内で定義されるオブジェクトです。 一時オブジェクトはコンパイラによって作成されるオブジェクトです。 `_cexit` または `_c_exit` を呼び出す前に自動オブジェクトを破棄するには、次のように、明示的にオブジェクトのデストラクターを呼び出します。  
  
```  
myObject.myClass::~myClass( );  
```  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_cexit`|\<process.h>|  
|`_c_exit`|\<process.h>|  
  
 互換性について詳しくは、「はじめに」の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [_exec 系関数と _wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)   
 [exit、_Exit、_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit、_onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_spawn関数、_wspawn 関数](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system、_wsystem](../../c-runtime-library/reference/system-wsystem.md)
