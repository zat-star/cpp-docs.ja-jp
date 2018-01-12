---
title: "_putenv、_wputenv | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _putenv
- _wputenv
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tputenv
- _wputenv
- _putenv
- wputenv
- tputenv
dev_langs: C++
helpviewer_keywords:
- _putenv function
- environment variables, deleting
- putenv function
- tputenv function
- environment variables, creating
- wputenv function
- _wputenv function
- _tputenv function
- environment variables, modifying
ms.assetid: 9ba9b7fd-276e-45df-8420-d70c4204b8bd
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 509766f9f324c1dd9488488861e7c64200d44837
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="putenv-wputenv"></a>_putenv、_wputenv
環境変数を作成、変更、または削除します。 これらの関数にはセキュリティが強化されたバージョンがあります。「[_putenv_s、_wputenv_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md)」をご覧ください。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
int _putenv(  
   const char *envstring   
);  
int _wputenv(  
   const wchar_t *envstring   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `envstring`  
 環境文字列定義。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は 0 またはエラーの場合は-1 を返します。  
  
## <a name="remarks"></a>コメント  
 `_putenv` の関数は、新しい環境変数を追加したり、既存の環境変数の値を変更したりします。 環境変数は、プロセス (たとえば、プログラムにリンクされるライブラリの既定の検索パス) が実行される環境を定義します。 `_wputenv` 関数は、`_putenv` 関数のワイド文字バージョンです。`envstring` 関数の引数 `_wputenv` は、ワイド文字列です。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tputenv`|`_putenv`|`_putenv`|`_wputenv`|  
  
 `envstring` 引数は `varname=string` 形式の文字列へのポインターである必要があります。ここで、`varname` は、追加または変更される環境変数の名前であり、`string` は変数の値です。 `varname` が既に環境の一部である場合、値が `string` に置き換えられます。そうでない場合は、新しい `varname` 変数とその `string` の値が環境に追加されます。 空の `string` を指定して、つまり `varname=` だけを指定することで環境から変数を削除できます。  
  
 `_putenv` と `_wputenv` は、現在のプロセスに対してローカルである環境にのみ影響します。したがって、コマンド レベルの環境を変更するためには使用できません。 つまり、これらの関数は、ランタイム ライブラリからアクセスできるデータ構造体だけを対象とし、プロセス用にオペレーティング システムで作成された環境 "セグメント" は参照しません。 現在のプロセスが終了すると、環境は、呼び出し元プロセス (ほとんどの場合、オペレーティング システムのレベル) のレベルに戻ります。 ただし、変更された環境は `_spawn`、`_exec`、または `system` で作成された新しいプロセスに渡すことができ、これらの新しいプロセスは `_putenv` と `_wputenv` が追加した新しい項目を取得します。  
  
 環境のエントリを直接変更しないでください。代わりに、`_putenv`、または `_wputenv` を使用して変更します。 特に、`_environ[]` グローバル配列の要素を直接の解放すると、無効なメモリ アドレスを生成する可能性があります。  
  
 `getenv` と `_putenv` はグローバル変数 `_environ` を使用して環境のテーブルにアクセスします。`_wgetenv` と `_wputenv` は `_wenviron` を使用します。 `_putenv`および`_wputenv`の値を変更する可能性があります`_environ`と`_wenviron`、したがって無効化、`_envp`に渡す引数`main`と`_wenvp`に渡す引数`wmain`です。 つまり、環境情報へのアクセスに `_environ` または `_wenviron` を使用しても安全です。 `_putenv` および `_wputenv` とグローバル変数との関係の詳細については、「[_environ、_wenviron](../../c-runtime-library/environ-wenviron.md)」をご覧ください。  
  
> [!NOTE]
>  `_putenv` 系関数と `_getenv` 系関数はスレッド セーフではありません。 `_getenv` が文字列を変更している間に `_putenv` が文字列ポインターを返すことがあり、これはランダム エラーの原因になります。 これらの関数の呼び出しが同期されていることを確認する必要があります。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_putenv`|\<stdlib.h>|  
|`_wputenv`|\<stdlib.h> または \<wchar.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
 `_putenv` の使用例については、「[getenv、_wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)」をご覧ください。  
  
## <a name="see-also"></a>参照  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [getenv、_wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [_searchenv、_wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)