---
title: "exit、_Exit、_exit | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _exit
- exit
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
- Exit
- _exit
- process/exit
- process/_Exit
- stdlib/exit
- stdlib/_Exit
dev_langs:
- C++
helpviewer_keywords:
- exit function
- _exit function
- processes, terminating
- function calls, terminating
- process termination, calling
ms.assetid: b1501fa6-27c2-478c-9e93-cc4fd802a01f
caps.latest.revision: 17
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 8d6f75bb19c2cfd89d8714ed87ff91ddf340055e
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="exit-exit-exit"></a>終了、_Exit、_exit
呼び出しプロセスを終了します。 `exit` 関数はクリーンアップ後に呼び出しプロセスを終了させます。一方、 `_exit` と `_Exit` は直ちに終了させます。  
  
> [!NOTE]
>  テスト シナリオまたはデバッグ シナリオの場合を除き、この方法を使用してユニバーサル Windows プラットフォーム (UWP) アプリまたは [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリをシャットダウンしないでください。 プログラムによる方法で、あるいは UI による方法で [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリを閉じることは許可されていません。 Windows 8 および 8.1 アプリについて詳しくは、「 [アプリのライフサイクル](http://go.microsoft.com/fwlink/?LinkId=262853)」をご覧ください。 Windows 10 アプリについて詳しくは、「 [Windows 10 アプリの使用方法のガイド](http://go.microsoft.com/fwlink/p/?linkid=619133)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
void exit(   
   int const status   
);  
void _Exit(   
   int const status   
);  
void _exit(   
   int const status   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `status`  
 終了ステータス コード。  
  
## <a name="remarks"></a>コメント  
 `exit`関数、 `_Exit` 関数、 `_exit` 関数は呼び出しプロセスを終了します。 `exit` 関数はスレッド ローカル オブジェクトのデストラクターを呼び出してから、 `atexit` と `_onexit`によって登録された関数を、後入れ先出し (LIFO) の順序で呼び出し、プロセスが終了する前にすべてのファイル バッファーをフラッシュします。 `_Exit` 関数と `_exit` 関数は、スレッド ローカル オブジェクトの破棄も、 `atexit` や `_onexit` 関数の処理もせず、ストリーム バッファーのフラッシュもしないでプロセスを終了します。  
  
 `exit`、 `_Exit` 、 `_exit` 呼び出しは値を返しませんが、プロセスの終了後、 `status` の下位バイトは、ホスト環境または待機している呼び出しプロセスで使用できるようになります (存在する場合)。 通常、呼び出し元は、終了を示すために `status` 値を 0 に設定し、エラーを示す場合は他の値に設定します。 `status` 値は、オペレーティング システムのバッチ コマンド `ERRORLEVEL` で使用でき、0 の値を表す `EXIT_SUCCESS`、または 1 の値を表す `EXIT_FAILURE`の 2 種類の定数のうちのいずれかで表されます。  
  
 `exit`、 `_Exit`、 `_exit`、 `quick_exit`、 `_cexit`、 `_c_exit` 関数は次のように動作します。  
  
|関数|説明|  
|--------------|-----------------|  
|`exit`|完全な C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードをホスト環境に提供します。|  
|`_Exit`|最低限の C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードをホスト環境に提供します。|  
|`_exit`|最低限の C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードをホスト環境に提供します。|  
|`quick_exit`|高速な C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードをホスト環境に提供します。|  
|`_cexit`|完全な C ライブラリの終了処理を実行し、呼び出し元に戻ります。 プロセスを終了しません。|  
|`_c_exit`|最低限の C ライブラリの終了処理を実行し、呼び出し元に戻ります。 プロセスを終了しません。|  
  
 `exit`関数、  `_Exit` 関数、または `_exit` 関数を呼び出す場合、呼び出し時に存在する一時オブジェクトまたは自動オブジェクトのデストラクターは呼び出されません。 自動オブジェクトは、オブジェクトが静的として宣言されていない関数内で定義されます。 一時オブジェクトはコンパイラによって作成されたオブジェクトです。 `exit`、 `_Exit`、または `_exit`を呼び出す前に自動オブジェクトを破棄するには、次のように、明示的にオブジェクトのデストラクターを呼び出します。  
  
```  
myObject.myClass::~myClass();  
```  
  
 `DLL_PROCESS_ATTACH` から `exit` を呼び出すために `DllMain`を使用しないでください。 `DLLMain` の関数を終了するには、 `FALSE` から `DLL_PROCESS_ATTACH`を返します。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`exit`、`_Exit`、`_exit`|\<process.h> または \<stdlib.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_exit.c  
// This program returns an exit code of 1. The  
// error code could be tested in a batch file.  
  
#include <stdlib.h>  
  
int main( void )  
{  
   exit( 1 );  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [_cexit、_c_exit](../../c-runtime-library/reference/cexit-c-exit.md)   
 [_exec 関数、_wexec 関数](../../c-runtime-library/exec-wexec-functions.md)   
 [_onexit、_onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [quick_exit](../../c-runtime-library/reference/quick-exit1.md)   
 [_spawn関数、_wspawn 関数](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system、_wsystem](../../c-runtime-library/reference/system-wsystem.md)
