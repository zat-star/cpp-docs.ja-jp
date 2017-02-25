---
title: "_putenv_s、_wputenv_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wputenv_s"
  - "_putenv_s"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "putenv_s"
  - "wputenv_s"
  - "_wputenv_s"
  - "_putenv_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_putenv_s 関数"
  - "_wputenv_s 関数"
  - "環境変数, 作成"
  - "環境変数, 削除"
  - "環境変数, 変更"
  - "putenv_s 関数"
  - "wputenv_s 関数"
ms.assetid: fbf51225-a8da-4b9b-9d7c-0b84ef72df18
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# _putenv_s、_wputenv_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

環境変数を作成、変更、または削除します。  これらのバージョンの [\_putenv、\_wputenv](../../c-runtime-library/reference/putenv-wputenv.md) は、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」の説明にあるとおり、セキュリティーが強化されたバージョンです。  
  
> [!IMPORTANT]
>  この API は、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/en-us/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
errno_t _putenv_s(  
   const char *name,  
   const char *value   
);  
errno_t _wputenv_s(  
   const wchar_t *name,  
   const wchar_t *value  
);  
```  
  
#### パラメーター  
 `name`  
 環境変数名。  
  
 `value`  
 環境変数に設定する値。  
  
## 戻り値  
 正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。  
  
### エラー条件  
  
|`name`|`value`|戻り値|  
|------------|-------------|---------|  
|`NULL`|任意|`EINVAL`|  
|任意|`NULL`|`EINVAL`|  
  
 いずれかのエラー条件が発生すると、この関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、これらの関数は `EINVAL` を返し、`errno` を `EINVAL` に設定します。  
  
## 解説  
 `_putenv_s` の関数は、新しい環境変数を追加したり、既存の環境変数の値を変更したりします。  環境変数は、プロセス \(たとえば、プログラムにリンクされるライブラリの既定の検索パス\) が実行される環境を定義します。  `_wputenv_s` 関数は、`_putenv_s` 関数のワイド文字バージョンです。`envstring` 関数の引数 `_wputenv_s` は、ワイド文字列です。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tputenv_s`|`_putenv_s`|`_putenv_s`|`_wputenv_s`|  
  
 `name` は、追加または変更する環境変数の名前で、`value` はその変数の値です。  `name` が既に環境の一部である場合、値が `value` に置き換えられます。そうでない場合は、新しい `name` 変数とその `value` が環境に追加されます。  空の文字列 \(つまり ""\) を `value` に指定すると、環境から変数を削除できます。  
  
 `_putenv_s` と `_wputenv_s` は、現在のプロセスに対してローカルである環境にのみ影響します。したがって、コマンド レベルの環境を変更するためには使用できません。  これらの関数は、ランタイム ライブラリからアクセスできるデータ構造体でのみ動作し、プロセス用にオペレーティング システムが作成する環境 "セグメント" では動作しません。  現在のプロセスが終了すると、環境は、呼び出し元プロセスのレベルに戻ります。これはほとんどの場合、オペレーティング システムのレベルです。  ただし、変更された環境は `_spawn`、`_exec`、または `system` で作成された新しいプロセスに渡すことができ、これらの新しいプロセスは `_putenv_s` と `_wputenv_s` が追加した新しい項目を取得します。  
  
 環境のエントリを直接変更しないでください。代わりに、`_putenv_s`、または `_wputenv_s` を使用して変更します。  特に、`_environ[]` グローバル配列の要素を直接解放すると、無効なメモリ アドレスを生成する可能性があります。  
  
 `getenv` と `_putenv_s` はグローバル変数 `_environ` を使用して環境のテーブルにアクセスします。`_wgetenv` と `_wputenv_s` は `_wenviron` を使用します。  `_putenv_s` と `_wputenv_s` は `_environ` と `_wenviron` の値を変更して、`main` に対する `envp` 引数と `wmain` に対する `_wenvp` 引数を無効にする場合があります。  つまり、環境情報へのアクセスに `_environ` または `_wenviron` を使用しても安全です。  グローバル変数に対する `_putenv_s` と `_wputenv_s` の関係に関する詳細については、「[\_environ、\_wenviron](../../c-runtime-library/environ-wenviron.md)」を参照してください。  
  
> [!NOTE]
>  `_putenv_s` 系関数と `_getenv_s` 系関数はスレッド セーフではありません。  `_putenv_s` が文字列を変更している間に `_getenv_s` が文字列ポインターを返すことがあり、これはランダム エラーの原因になります。  これらの関数の呼び出しが同期されていることを確認する必要があります。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_putenv_s`|\<stdlib.h\>|  
|`_wputenv_s`|\<stdlib.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 `_putenv_s` の使用方法のサンプルについては、「[getenv\_s、\_wgetenv\_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 該当なし。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [getenv、\_wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [\_searchenv、\_wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)