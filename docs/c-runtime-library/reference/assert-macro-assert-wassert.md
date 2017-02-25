---
title: "assert マクロ、_assert、_wassert | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "assert"
  - "_assert"
  - "_wassert"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "assert"
  - "_assert"
  - "_wassert"
  - "assert/_wassert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "中止 (プログラムを)"
  - "assert 関数"
  - "ASSERT マクロ"
ms.assetid: a9ca031a-648b-47a6-bdf1-65fc7399dd40
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# assert マクロ、_assert、_wassert
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

式を評価し、結果が `false` の場合、診断メッセージを出力し、プログラムを中止します。  
  
## 構文  
  
```  
assert(   
   expression   
);  
void _assert(  
   char const* message,  
   char const* filename,  
   unsigned line  
);  
void _wassert(  
   wchar_t const* message,  
   wchar_t const* filename,  
   unsigned line  
);  
```  
  
#### パラメーター  
 `expression`  
 0 以外 \(`true`\) または 0 \(`false`\) に評価されるスカラー式 \(ポインター式\)。  
  
 `message`  
 表示するメッセージ。  
  
 `filename`  
 アサーションが失敗したソース ファイルの名前。  
  
 `line`  
 失敗したアサーションのソース ファイルの行番号。  
  
## 解説  
 `assert` マクロは通常、プログラム開発中の論理エラーを識別するために使用されます。 正しく動作しないときにのみ `false` に評価される `expression` 引数を実装することにより、予期しない条件が発生したときにプログラムの実行を停止するために使用します。 マクロ `NDEBUG` を定義することにより、コンパイル時にアサーション チェックをオフにすることができます。 オフにすることができます、 `assert` マクロを使用して、ソース ファイルを変更することがなく、 **\/DNDEBUG** コマンド ライン オプションです。 \<assert.h\> が組み込まれる前に `#define NDEBUG` ディレクティブを使用することにより、ソース コードの `assert` マクロをオフにすることができます。  
  
 `expression` を `false` \(0\) に評価し、[abort](../../c-runtime-library/reference/abort.md) を呼び出してプログラム実行を終了する際、`assert` マクロは診断メッセージを出力します。`expression` が `true` \(0 以外\) の場合、アクションは取られません。 診断メッセージには、失敗した式、ソース ファイルの名前、アサーションが失敗した行番号が含まれます。  
  
 診断メッセージはワイド文字で出力されます。 したがって、式に Unicode 文字がある場合でも、予期していたとおりに機能します。  
  
 ルーチンを呼び出したアプリケーションの種類に基づいて診断メッセージの出力先が決まります。 コンソール アプリケーションは、常に `stderr` を使用してメッセージを受け取ります。 Windows ベースのアプリケーションで、`assert` は、Windows [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) 関数を呼び出し、メッセージ ボックスを作成して、メッセージと **\[OK\]** ボタンを表示します。 ユーザーが **\[OK\]** をクリックすると、プログラムはすぐに中止されます。  
  
 アプリケーションがランタイム ライブラリのデバッグ バージョンとリンクされている場合、`assert` は、**\[中止\]**、**\[再試行\]** と **\[無視\]** の 3 個のボタンのあるメッセージ ボックスを作成します。 ユーザーが **\[中止\]** をクリックすると、プログラムはすぐに中止されます。 ユーザーが **\[再試行\]** をクリックすると、Just\-In\-Time \(JIT\) デバッグが有効になっている場合、デバッガーが呼び出され、ユーザーはプログラムをデバッグできます。 ユーザーが **\[無視\]** をクリックすると、`assert` は、通常の実行である、**\[OK\]** のボタンのあるメッセージ ボックスの作成を続けます。 なお、エラー状況が存在するときに **\[無視\]** をクリックすると、"未定義の動作" という結果になることがあります。  
  
 CRT デバッグの詳細については、「[CRT のデバッグ技術](../Topic/CRT%20Debugging%20Techniques.md)」を参照してください。  
  
 `_assert` 関数と `_wassert` 関数は、内部 CRT 関数です。 これらは、アサーションをサポートするためのオブジェクト ファイルに必要なコードを最小限に抑えるうえで役立ちます。 これらの関数を直接呼び出すことはお勧めしません。  
  
 `NDEBUG` が定義されていない場合、`assert` マクロは、C ランタイム ライブラリのリリース バージョンとデバッグ バージョンの両方で有効になります。`NDEBUG` が定義されている場合、マクロは使用可能になりますが、その引数を評価せず、影響を与えません。 マクロが有効な場合、`assert` マクロは実装のために `_wassert` を呼び出します。 その他のアサーション マクロの [\_ASSERT](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md)、[\_ASSERTE](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md)、[\_ASSERT\_EXPR](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md) も使用できますが、これらは、[\_DEBUG](../Topic/_DEBUG.md) マクロが定義されており、かつ C ランタイム ライブラリのデバッグ バージョンとリンクされたコードにある場合にのみ、渡される式を評価します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`assert`, `_wassert`|\<assert.h\>|  
  
 `_assert` 関数の署名は、ヘッダー ファイルでは使用できません。`_wassert` 関数の署名は、`NDEBUG` マクロが定義されていない場合にのみ使用できます。  
  
## 使用例  
 このプログラムでは、`analyze_string` 関数は、`assert` マクロを使用して、文字列と長さに関連するいくつかの条件をテストします。 条件のいずれかが失敗した場合、プログラムは失敗の原因を示すメッセージを出力します。  
  
```  
// crt_assert.c  
// compile by using: cl /W4 crt_assert.c  
#include <stdio.h>  
#include <assert.h>  
#include <string.h>  
  
void analyze_string( char *string );   // Prototype  
  
int main( void )  
{  
   char  test1[] = "abc", *test2 = NULL, test3[] = "";  
  
   printf ( "Analyzing string '%s'\n", test1 ); fflush( stdout );  
   analyze_string( test1 );  
   printf ( "Analyzing string '%s'\n", test2 ); fflush( stdout );  
   analyze_string( test2 );  
   printf ( "Analyzing string '%s'\n", test3 ); fflush( stdout );  
   analyze_string( test3 );  
}  
  
// Tests a string to see if it is NULL,   
// empty, or longer than 0 characters.  
void analyze_string( char * string )  
{  
   assert( string != NULL );        // Cannot be NULL  
   assert( *string != '\0' );       // Cannot be empty  
   assert( strlen( string ) > 2 );  // Length must exceed 2  
}  
```  
  
 プログラムは次の出力を生成します。  
  
```Output  
Analyzing string 'abc' Analyzing string '(null)' Assertion failed: string != NULL, file crt_assert.c, line 25  
```  
  
 アサーションが失敗した後、オペレーティング システムとランタイム ライブラリのバージョンに応じて、以下のような内容のメッセージ ボックスが表示される可能性があります。  
  
```Output  
問題が原因で、プログラムの正常な動作が停止しました。 Windows はプログラムを閉じ、解決策が使用可能かどうかを知らせます。  
```  
  
 デバッガーがインストールされている場合は **\[デバッグ\]** ボタンを選択してデバッガーを開始するか、**\[プログラムの終了\]** をクリックして終了します。  
  
## 同等の .NET Framework 関数  
 [System::Diagnostics::Debug::Assert](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)  
  
## 参照  
 [エラー処理](../../c-runtime-library/error-handling-crt.md)   
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [raise](../../c-runtime-library/reference/raise.md)   
 [signal](../../c-runtime-library/reference/signal.md)   
 [\_ASSERT、\_ASSERTE、\_ASSERT\_EXPR マクロ](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md)   
 [\_DEBUG](../Topic/_DEBUG.md)