---
title: _setmbcp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _setmbcp
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _setmbcp
- setmbcp
dev_langs:
- C++
helpviewer_keywords:
- setmbcp function
- _setmbcp function
- multibyte code pages
ms.assetid: cfde53b5-0b73-4684-81b1-a8d3aafc85de
caps.latest.revision: 13
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 4ae4dc9b57da5ee7d38f32066b8b4b204c50f065
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="setmbcp"></a>_setmbcp
新しいマルチバイト コード ページを設定します。  
  
## <a name="syntax"></a>構文  
  
```  
int _setmbcp(  
   int codepage   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `codepage`  
 ロケールに依存しないマルチバイトのルーチンのための新しいコード ページ設定。  
  
## <a name="return-value"></a>戻り値  
 コード ページが正常に設定されている場合は、0 を返します。 無効なコード ページの値が指定した場合`codepage`-1 とコード ページの設定は変更を返します。 メモリ割り当ての失敗が発生した場合には、`errno` を `EINVAL` に設定します。  
  
## <a name="remarks"></a>コメント  
 `_setmbcp` 関数は新しいマルチバイト コード ページを指定します。 既定では、ランタイム システムはマルチバイト コード ページを、システムの既定の ANSI コード ページに自動的に設定します。 マルチバイト コード ページの設定は、ロケールに依存していないすべてのマルチバイトのルーチンに影響します。 ただし、現在のロケールに対して定義されているコード ページを使用するように `_setmbcp` に指示することは可能です (次のマニフェスト定数とそれに関連する動作の結果の一覧を参照してください)。 マルチバイト コード ページではなく、ロケールのコード ページに依存しているマルチバイトのルーチンの一覧については、「[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)」を参照してください。  
  
 マルチバイト コード ページは、次のランタイム ライブラリ ルーチンによる、マルチバイト文字の処理にも影響します。  
  
||||  
|-|-|-|  
|[_exec 関数](../../c-runtime-library/exec-wexec-functions.md)|[_mktemp](../../c-runtime-library/reference/mktemp-wmktemp.md)|[_stat](../../c-runtime-library/reference/stat-functions.md)|  
|[_fullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)|[_spawn 関数](../../c-runtime-library/spawn-wspawn-functions.md)|[_tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
|[_makepath](../../c-runtime-library/reference/makepath-wmakepath.md)|[_splitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)|[tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
  
 さらに、マルチバイト文字の `argv` または `envp` プログラム引数をパラメーターとして受け取るすべてのランタイム ライブラリ ルーチン (`_exec` および `_spawn` ファミリなど) は、これらの文字列をマルチバイト コード ページに従って処理します。 そのため、これらのルーチンは、マルチバイト コード ページを変更する `_setmbcp` の呼び出しからも影響を受けます。  
  
 `codepage` 引数は、次の値のいずれかに設定できます。  
  
-   `_MB_CP_ANSI` プログラムの起動時にオペレーティング システムから取得した ANSI コード ページを使用します。  
  
-   `_MB_CP_LOCALE` [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) の前回の呼び出しから取得した現在のロケールのコード ページを使用します。  
  
-   `_MB_CP_OEM` プログラムの起動時にオペレーティング システムから取得した OEM コード ページを使用します。  
  
-   `_MB_CP_SBCS` 1 バイト コード ページを使用します。 コード ページを `_MB_CP_SBCS` に設定すると、[_ismbblead](../../c-runtime-library/reference/ismbblead-ismbblead-l.md) などのルーチンは常に false を返します。  
  
-   他の任意の有効なコード ページ値。値は、ANSI、OEM、またはその他のオペレーティング システムがサポートするコード ページであるかに関係ありません。ただし、サポートされていない UTF-7 と UTF-8 は除きます。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_setmbcp`|\<mbctype.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [setlocale、_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)
