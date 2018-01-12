---
title: _CrtCheckMemory | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtCheckMemory
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
- CrtCheckMemory
- _CrtCheckMemory
dev_langs: C++
helpviewer_keywords:
- _CrtCheckMemory function
- CrtCheckMemory function
ms.assetid: 457cc72e-60fd-4177-ab5c-6ae26a420765
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 60909079a4d7c30b3a3e6c00257d882d76467585
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="crtcheckmemory"></a>_CrtCheckMemory
デバッグ ヒープで割り当てられたメモリ ブロックの整合性を確認します (デバッグ バージョンのみ)。  
  
## <a name="syntax"></a>構文  
  
```  
  
int _CrtCheckMemory( void );  
```  
  
## <a name="return-value"></a>戻り値  
 成功すると、`_CrtCheckMemory` は TRUE を返します。それ以外の場合は FALSE を返します。  
  
## <a name="remarks"></a>コメント  
 `_CrtCheckMemory` 関数は、基になるベース ヒープを確認し、各メモリ ブロックを調べることにより、デバッグ ヒープ マネージャーによって割り当てられたメモリを検証します。 基になるベース ヒープ、デバッグ ヘッダー情報、または上書きバッファーでエラーやメモリの不整合が検出された場合、`_CrtCheckMemory` はエラー状況を説明する情報を含むデバッグ レポートを生成します。 [_DEBUG](../../c-runtime-library/debug.md) が定義されていない場合、`_CrtCheckMemory` の呼び出しは前処理で削除されます。  
  
 `_CrtCheckMemory` の動作は、[_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) 関数を使用して [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) フラグのビット フィールドを設定することによって制御できます。 **_CRTDBG_CHECK_ALWAYS_DF** ビット フィールドをオンに切り替えると、メモリ割り当て操作が要求されるたびに `_CrtCheckMemory` が呼び出されるようになります。 この方法は実行速度を低下させますが、エラーをすばやく見つけるために役立ちます。 **_CRTDBG_ALLOC_MEM_DF** ビット フィールドをオフに切り替えると、`_CrtCheckMemory` がヒープを確認せずに直ちに **TRUE** を返すようになります。  
  
 この関数は **TRUE** または **FALSE** を返すため、[_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 系マクロに渡すことによって、デバッグ用の単純なエラー処理機構を作成できます。 次の例は、ヒープの破損が検出された場合に、アサーション エラーを発生させます。  
  
```  
_ASSERTE( _CrtCheckMemory( ) );  
```  
  
 `_CrtCheckMemory` を他のデバッグ関数と共に使用する方法の詳細については、「[ヒープの状態をレポートする関数](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。 メモリ管理とデバッグ ヒープの概要については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_CrtCheckMemory`|\<crtdbg.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## <a name="example"></a>例  
 `_CrtCheckMemory` の使用例については、「[crt_dbg1](http://msdn.microsoft.com/en-us/17b4b20c-e849-48f5-8eb5-dca6509cbaf9)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)   
 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)   
 [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)