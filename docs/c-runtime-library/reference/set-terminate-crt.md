---
title: set_terminate (CRT) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: set_terminate
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
f1_keywords: set_terminate
dev_langs: C++
helpviewer_keywords:
- set_terminate function
- terminate function
- exception handling, termination
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f2e2ac7ad7b103b5c1da790b61f560c758d9d124
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="setterminate-crt"></a>set_terminate (CRT)
`terminate` によって呼び出される独自の終了ルーチンをインストールします。  
  
## <a name="syntax"></a>構文  
  
```  
terminate_function set_terminate(  
   terminate_function termFunction  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `termFunction`  
 作成する終了関数へのポインター。  
  
## <a name="return-value"></a>戻り値  
 `set_terminate` によって登録された前の関数へのポインターを返し、前の関数を後で復元できるようにします。 前の関数が設定されていない場合には、戻り値を使用して既定の動作を復元することができます。この値は NULL になります。  
  
## <a name="remarks"></a>コメント  
 `set_terminate` 関数は `terminate` によって呼び出される関数として `termFunction` をインストールします。 `set_terminate` は C++ 例外処理で使用され、例外がスローされる前に、プログラムのどの時点でも呼び出すことができます。 `terminate` は既定では `abort` を呼び出します。 この既定の設定を変更するには、独自の終了関数を作成し、その関数の名前を引数として `set_terminate` を呼び出します。 `terminate` は、`set_terminate` への引数として渡された最後の関数を呼び出します。 必要なクリーンアップ タスクを実行した後で、`termFunction` はプログラムを終了する必要があります。 終了せずに呼び出し元に戻った場合は、`abort` が呼び出されます。  
  
 マルチ スレッド環境では、終了関数はスレッドごとに別々に管理されます。 新しいスレッドは各々、それぞれの終了関数をインストールする必要があります。 したがって、各スレッドがそれぞれの終了処理を担当します。  
  
 `terminate_function` 型は EH.H に、ユーザー定義の終了関数、つまり `void` を返す `termFunction` へのポインターとして定義されます。 ユーザー定義関数 `termFunction` は引数を受け取ることはできず、呼び出し元に戻ってはいけません。 戻った場合、`abort` が呼び出されます。 `termFunction` 内から例外がスローされることはありません。  
  
```  
typedef void ( *terminate_function )( );  
```  
  
> [!NOTE]
>  `set_terminate` 関数はデバッガーの外部でのみ機能します。  
  
 動的にリンクされるすべての DLL または EXE ファイルに対して、`set_terminate` ハンドラーは単一です。自分で `set_terminate` を呼び出しても別のハンドラーに置き換えられます。あるいはハンドラーを別の DLL または EXE ファイルに自分で置き換えることもできます。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`set_terminate`|\<eh.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
 [terminate](../../c-runtime-library/reference/terminate-crt.md) の例をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [例外処理ルーチン](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [_get_terminate](../../c-runtime-library/reference/get-terminate.md)   
 [set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)