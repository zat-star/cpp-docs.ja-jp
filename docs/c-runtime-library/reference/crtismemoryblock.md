---
title: _CrtIsMemoryBlock | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtIsMemoryBlock
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
- CrtlsMemoryBlock
- _CrtIsMemoryBlock
dev_langs: C++
helpviewer_keywords:
- _CrtIsMemoryBlock function
- CrtIsMemoryBlock function
ms.assetid: f7cbbc60-3690-4da0-a07b-68fd7f250273
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ec6bea115ba509c7275a2d220cf4b10c6faecae9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="crtismemoryblock"></a>_CrtIsMemoryBlock
指定されたメモリ ブロックがローカル ヒープ内にあり、有効なデバッグ ヒープ ブロック型識別子が設定されていることを検査します (デバッグ バージョンだけ)。  
  
## <a name="syntax"></a>構文  
  
```  
int _CrtIsMemoryBlock(   
   const void *userData,  
   unsigned int size,  
   long *requestNumber,  
   char **filename,  
   int *linenumber   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `userData`  
 検査するメモリ ブロックの先頭へのポインター。  
  
 [入力] `size`  
 指定されたブロックのサイズ (バイト)。  
  
 [出力] `requestNumber`  
 ブロックの割り当て番号へのポインター、または `NULL`。  
  
 [出力] `filename`  
 ブロックを要求したソース ファイル名へのポインター、または `NULL`。  
  
 [出力] `linenumber`  
 ソース ファイル内の行番号へのポインター、または `NULL`。  
  
## <a name="return-value"></a>戻り値  
 `_CrtIsMemoryBlock` は、指定されたメモリ ブロックがローカル ヒープにあり、有効なデバッグ ヒープ ブロック型識別子が設定されていれば、`TRUE` を返します。それ以外の場合は、`FALSE` を返します。  
  
## <a name="remarks"></a>コメント  
 `_CrtIsMemoryBlock` 関数は、指定されたメモリ ブロックがアプリケーションのローカル ヒープ内にあり、有効なブロック型識別子が設定されていることを検査します。 また、この関数を使用すると、オブジェクト割り当て順序番号と、メモリ ブロックの割り当て要求を行ったソース ファイル名および行番号を取得できます。 `requestNumber`、`filename`、`linenumber` の各パラメーターとして NULL 以外の値を渡すと、`_CrtIsMemoryBlock` は、ローカル ヒープ内にメモリ ブロックが見つかった場合、これらのパラメーターにそのメモリ ブロックのデバッグ ヘッダーの値を設定します。 [_DEBUG](../../c-runtime-library/debug.md) が定義されていない場合、`_CrtIsMemoryBlock` の呼び出しは前処理で削除されます。  
  
 `_CrtIsMemoryBlock` は、失敗すると `FALSE` を返し、出力パラメーターを既定値に初期化します。この場合、`requestNumber` および `lineNumber` は 0 に設定され、`filename` は `NULL` に設定されます。  
  
 この関数は `TRUE` または `FALSE` を返すため、[_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 系マクロに渡すことによって、デバッグ用の単純なエラー処理機構を作成できます。 指定されたアドレスがローカル ヒープ内にない場合に、アサーションの失敗を発生させるには、次のように記述します。  
  
```  
_ASSERTE( _CrtIsMemoryBlock( userData, size, &requestNumber,   
&filename, &linenumber ) );  
```  
  
 `_CrtIsMemoryBlock` を他のデバッグ関数およびマクロと共に使用する方法の詳細については、「[レポート用マクロ](/visualstudio/debugger/macros-for-reporting)」を参照してください。 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_CrtIsMemoryBlock`|\<crtdbg.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## <a name="example"></a>例  
 「[_CrtIsValidHeapPointer](../../c-runtime-library/reference/crtisvalidheappointer.md)」のトピックの例を参照してください。  
  
## <a name="see-also"></a>参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)