---
title: _CrtIsValidPointer | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CrtIsValidPointer
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
- CrtlsValidPointer
- _CrtIsValidPointer
dev_langs:
- C++
helpviewer_keywords:
- CrtIsValidPointer function
- _CrtIsValidPointer function
ms.assetid: 91c35590-ea5e-450f-a15d-ad8d62ade1fa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e81cd074c9bd69386b300d307525a76515e02522
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="crtisvalidpointer"></a>_CrtIsValidPointer
ポインターが null でないことを確認します。 Visual Studio 2010 より前のバージョンの C ランタイム ライブラリでは、指定したメモリ範囲で読み取りおよび書き込みが可能であることを確認します (デバッグ バージョンのみ)。  
  
## <a name="syntax"></a>構文  
  
```  
int _CrtIsValidPointer(   
   const void *address,  
   unsigned int size,  
   int access   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 アドレス  
 確認のためにテストするメモリ範囲の先頭を指します。  
  
 `size`  
 指定されたメモリ範囲のサイズ (バイト単位)。  
  
 access  
 メモリ範囲に対して確認する読み取り/書き込みアクセシビリティ。  
  
## <a name="return-value"></a>戻り値  
 指定したポインターが null でない場合、`_CrtIsValidPointer` は TRUE を返します。 Visual Studio 2010 より前のバージョンの CRT ライブラリでは、メモリ範囲で指定された操作が有効である場合に、TRUE を返します。 それ以外の場合、関数は FALSE を返します。  
  
## <a name="remarks"></a>コメント  
 Visual Studio 2010 以降の CRT ライブラリでは、size および access パラメーターは無視されます。`_CrtIsValidPointer` は、指定されたアドレスが null でないことを確認するだけです。 このテストは自分で簡単に実行できるので、この関数を使用することはお勧めしません。 Visual Studio 2010 より前のバージョンでは、この関数は、`address` から始まる `size` バイトのメモリ範囲で、指定されたアクセシビリティ操作が有効であることを確認します。 `access` が TRUE に設定されると、メモリ範囲で読み取りと書き込みの両方が確認されます。 `access` が FALSE の場合は、メモリ範囲での読み取りだけが確認されます。 [_DEBUG](../../c-runtime-library/debug.md) が定義されていない場合、`_CrtIsValidPointer` の呼び出しは前処理で削除されます。  
  
 この関数は TRUE または FALSE を返すため、[_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 系マクロに渡すことによって、デバッグ用の単純なエラー処理機構を作成できます。 次の例では、メモリ範囲で読み取りと書き込みの両方が無効だった場合、アサーション エラーが発生します。  
  
```  
_ASSERTE( _CrtIsValidPointer( address, size, TRUE ) );  
```  
  
 `_CrtIsValidPointer` を他のデバッグ関数およびマクロと共に使用する方法の詳細については、「[レポート用マクロ](/visualstudio/debugger/macros-for-reporting)」を参照してください。 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_CrtIsValidPointer`|\<crtdbg.h>|  
  
 `_CrtIsValidPointer` は Microsoft 拡張機能です。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## <a name="example"></a>例  
 「[_CrtIsValidHeapPointer](../../c-runtime-library/reference/crtisvalidheappointer.md)」のトピックの例を参照してください。  
  
## <a name="see-also"></a>参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)