---
title: __security_init_cookie | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: __security_init_cookie
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
- security_init_cookie
- __security_init_cookie
dev_langs: C++
helpviewer_keywords:
- security cookie [C++]
- __security_init_cookie function
- security_init_cookie function
- global security cookie
ms.assetid: 32119905-0897-4a1c-84ca-bffd16c9b2af
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ee0657393ec8322889b527c21a36c13b9e032325
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="securityinitcookie"></a>__security_init_cookie
グローバル セキュリティ クッキーを初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
void __security_init_cookie(void);  
```  
  
## <a name="remarks"></a>コメント  
 グローバル セキュリティ クッキーは、[/GS (バッファーのセキュリティ チェック)](../../build/reference/gs-buffer-security-check.md) を指定してコンパイルされたコードおよび例外処理を使用するコードでバッファー オーバーランから保護するために使用されます。 オーバーランから保護されている関数を開始するときにクッキーはスタックに配置され、関数が終了するときにスタックの値がグローバルなクッキーと比較されます。 違いがある場合はバッファー オーバーランが発生したことを意味し、プログラムは直ちに終了します。  
  
 通常は、CRT の初期化時に、CRT によって `__security_init_cookie` が呼び出されます。 CRT の初期化をバイパスする場合 (たとえば、[/ENTRY](../../build/reference/entry-entry-point-symbol.md) を使用してエントリ ポイントを指定する場合) は、ユーザー自身で `__security_init_cookie` を呼び出す必要があります。 `__security_init_cookie` を呼び出さないと、グローバル セキュリティ クッキーが既定値に設定され、バッファー オーバーランの保護が損なわれます。 攻撃者がこの既定のクッキー値を悪用してバッファー オーバーランのチェックをすり抜けることがあるため、独自のエントリ ポイントを定義するときには、常に `__security_init_cookie` を呼び出すことをお勧めします。  
  
 `__security_init_cookie` の呼び出しは、オーバーランから保護されている関数に入る前に行う必要があります。そうしないと、実際には発生していないバッファー オーバーランが検出されます。 詳細については、「[C Runtime Error R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md)」(C ランタイム エラー R6035) をご覧ください。  
  
## <a name="example"></a>例  
 「[C Runtime Error R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md)」(C ランタイム エラー R6035) の例をご覧ください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`__security_init_cookie`|\<process.h>|  
  
 `__security_init_cookie` は、標準の C ランタイム ライブラリの Microsoft 拡張機能です。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [コンパイラ セキュリティの徹底調査](http://go.microsoft.com/fwlink/p/?linkid=7260)