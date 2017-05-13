---
title: _open_osfhandle | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _open_osfhandle
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _open_osfhandle
- open_osfhandle
dev_langs:
- C++
helpviewer_keywords:
- open_osfhandle function
- file handles [C++], associating
- _open_osfhandle function
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 0a201fa08f48198069df26c5c61944c99db73edf
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="openosfhandle"></a>_open_osfhandle
C ランタイム ファイル記述子を既存のオペレーティング システムのファイル ハンドルに関連付けます。  
  
## <a name="syntax"></a>構文  
  
```  
  
      int _open_osfhandle (  
   intptr_t osfhandle,  
   int flags   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `osfhandle`  
 オペレーティング システムのファイル ハンドル。  
  
 `flags`  
 許可される操作の種類。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合、`_open_osfhandle` は C ランタイム ファイル記述子を返します。 それ以外の場合、-1 を返します。  
  
## <a name="remarks"></a>コメント  
 `_open_osfhandle` 関数は、C ランタイム ファイル記述子を割り当て、`osfhandle` で指定したオペレーティング システムのファイル ハンドルに関連付けます。 `flags` 引数は、Fcntl.h で定義された 1 つ以上のマニフェスト定数で構成された整数式です。 `flags` 引数を構成するために複数のマニフェスト定数が使用される場合、定数はビットごとの OR 演算子を使用して組み合わされます ( **&#124;** )。  
  
 Fcntl.h では、次のマニフェスト定数が定義されています。  
  
 **_O_APPEND**  
 書き込み操作の前に、毎回、ファイル ポインターをファイルの末尾に位置指定します。  
  
 **_O_RDONLY**  
 読み取り専用でファイルを開きます。  
  
 **_O_TEXT**  
 ファイルをテキスト (変換) モードで開きます。  
  
 **_O_WTEXT**  
 Unicode (UTF-16 に変換) モードでファイルを開きます。  
  
 `_open_osfhandle` で開いたファイルを閉じるには、`_close` を呼び出します。 `_close` を呼び出すことによって元のハンドルも閉じるため、元のハンドルで Win32 関数 `CloseHandle` を呼び出す必要はありません。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_open_osfhandle`|\<io.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="see-also"></a>関連項目  
 [ファイル処理](../../c-runtime-library/file-handling.md)
