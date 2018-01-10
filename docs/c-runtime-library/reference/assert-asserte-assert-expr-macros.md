---
title: "_ASSERT、_ASSERTE、_ASSERT_EXPR マクロ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
- _ASSERTE
- ASSERTE
- _ASSERT
- _ASSERT_EXPR
dev_langs: C++
helpviewer_keywords:
- debugging [CRT], using macros
- _ASSERTE macro
- macros, debugging with
- debug reporting macros
- _ASSERT macro
- _ASSERT_EXPR macro
ms.assetid: e98fd2a6-7f5e-4aa8-8fe8-e93490deba36
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 07be60643ad77e1138c3c23a1dd358a1d4177f25
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="assert-asserte-assertexpr-macros"></a>_ASSERT、_ASSERTE、_ASSERT_EXPR マクロ
式を評価し、結果が `False` の場合に、デバッグ レポートを生成します (デバッグ バージョンのみ)。  
  
## <a name="syntax"></a>構文  
  
```  
_ASSERT_EXPR(  
   booleanExpression,  
   message  
);  
_ASSERT(   
   booleanExpression   
);  
_ASSERTE(   
   booleanExpression   
);  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `booleanExpression`  
 0 以外 (true) または 0 (false) に評価されるスカラー式 (ポインター式)。  
  
 `message`  
 レポートの一部として表示するワイド文字列。  
  
## <a name="remarks"></a>コメント  
 `_ASSERT_EXPR`マクロ、 `_ASSERT` マクロ、 `_ASSERTE` マクロは、デバッグ プロセス中に前提を検査するためのクリーンでシンプルなメカニズムを持つアプリケーションを提供します。 アプリケーションの製品版ビルドで呼び出されないようにするために `#ifdef` ステートメントで囲む必要がないため、これらのマクロには高い柔軟性があります。 この柔軟性は、 [_DEBUG](../../c-runtime-library/debug.md) マクロを使用することで実現されます。 `_ASSERT_EXPR`、 `_ASSERT` 、 `_ASSERTE` は、 `_DEBUG` がコンパイル時に定義される場合にのみ使用できます。 `_DEBUG` が定義されていない場合、これらのマクロの呼び出しは前処理で削除されます。  
  
 `_ASSERT_EXPR`、 `_ASSERT` 、 `_ASSERTE` はその `booleanExpression` 引数を評価し、結果が `false` (0) の際に、診断メッセージを出力し、 [_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) を呼び出してデバッグ レポートを生成します。 `_ASSERT` マクロは、単純な診断メッセージを出力します。  `_ASSERTE` には、メッセージ内の失敗した式の文字列表現が含まれます。 `_ASSERT_EXPR` には、診断メッセージの `message` 文字列が含まれます。 `booleanExpression` が 0 以外に評価されると、これらのマクロは何も行いません。  
  
 `_ASSERT_EXPR`、 `_ASSERT` 、 `_ASSERTE` は `_CrtDbgReportW`を呼び出します。これにより、すべての出力がワイド文字になります。 `_ASSERTE` プロパティは `booleanExpression` で Unicode 文字を正しく出力し、 `_ASSERT_EXPR` は `message`で Unicode 文字を出力します。  
  
 `_ASSERTE` マクロは失敗した式を指定し、 `_ASSERT_EXPR` は生成されたレポートにメッセージを指定できるようにするため、ユーザーはアプリケーションのソース コードを参照せずに問題を特定することができます。 ただし、欠点もあります。 `message` によって出力されるすべての `_ASSERT_EXPR` と、 `_ASSERTE` によって評価されるすべての式は文字列定数としてアプリケーションの出力 (デバッグ バージョン) ファイルに組み込まれます。 そのため、 `_ASSERT_EXPR` または `_ASSERTE`に対して多数の呼び出しが行われると、これらの式により、出力ファイルのサイズが大幅に増えます。  
  
 [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) や [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) 関数で明示的に指定しない限り、以下と等しい設定を持つメッセージがポップアップ ダイアログ ボックスに表示されます。  
  
`_CrtSetReportMode(CRT_ASSERT, _CRTDBG_MODE_WNDW);`  
  
 `_CrtDbgReportW` は、現在のレポート モード (複数可) と、 `_CRT_ASSERT` レポートの種類に定義されているファイルに基づいて、デバッグ レポートを生成し、その宛先 (複数可) を決定します。 既定では、アサーション エラーとエラーは、デバッグ メッセージ ウィンドウに送られます。 [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) 関数と [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) 関数は、各レポートの種類の宛先を定義するために使用されます。  
  
 宛先がデバッグ メッセージ ウィンドウであるときにユーザーが **[再試行]** ボタンをクリックすると、 `_CrtDbgReportW` は 1 を返します。これにより、 `_ASSERT_EXPR`マクロ、 `_ASSERT` マクロ、 `_ASSERTE` マクロはデバッガーを開始します (Just-In-Time (JIT) デバッグが有効な場合)。  
  
 レポート処理の詳細については、 [_CrtDbgReport、_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) 関数を参照してください。 アサーション失敗を解決し、これらのマクロをデバッグ エラーの処理機構として使用する方法の詳細については、「 [確認とレポートのためのマクロの使用](/visualstudio/debugger/macros-for-reporting)」を参照してください。  
  
 `_ASSERT` マクロの他に、プログラム ロジックの検証に [assert](../../c-runtime-library/reference/assert-macro-assert-wassert.md) マクロを使用できます。 このマクロは、ライブラリのデバッグ バージョンとリリース バージョンの両方で使用できます。 [_RPT、_RPTF](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) デバッグ マクロをデバッグ レポート生成のために使用することもできますが、式の評価は行いません。 `_RPT` マクロは単純なレポートを生成します。 `_RPTF` マクロは、ソース ファイルと、レポート マクロが呼び出された行番号を、生成されるレポートに組み込みます。 これらのマクロのワイド文字バージョンを使用できます (`_RPTWn`、 `_RPTFWn`)。 ワイド文字バージョンは、ワイド文字列がすべての文字列パラメーターと出力で使用できるという点を除き、ナロー文字バージョンと同一です。  
  
 `_ASSERT_EXPR`、`_ASSERT`、`_ASSERTE` はそれぞれマクロであり、\<crtdbg.h> を組み込むことによって使用可能になりますが、`_DEBUG` が定義されるときに、アプリケーションは、C ランタイム ライブラリのデバッグ バージョンとリンクする必要があります。これらのマクロは、他のランタイム関数を呼び出すからです。  
  
## <a name="requirements"></a>必要条件  
  
|マクロ|必須ヘッダー|  
|-----------|---------------------|  
|`_ASSERT_EXPR`,                  `_ASSERT`, `_ASSERTE`|\<crtdbg.h>|  
  
## <a name="example"></a>例  
 このプログラムでは、 `_ASSERT` マクロと `_ASSERTE` マクロが呼び出され、条件 `string1 == string2`がテストされます。 条件が失敗した場合、これらのマクロは診断メッセージを出力します。 `_RPTn` 関数の代わりにマクロの `_RPTFn` と `printf` グループをこのプログラムで実行することもできます。  
  
```C  
// crt_ASSERT_macro.c  
// compile with: /D_DEBUG /MTd /Od /Zi /link /verbose:lib /debug  
//  
// This program uses the _ASSERT and _ASSERTE debugging macros.  
//  
  
#include <stdio.h>  
#include <string.h>  
#include <malloc.h>  
#include <crtdbg.h>  
  
int main()  
{  
   char *p1, *p2;  
  
   // The Reporting Mode and File must be specified  
   // before generating a debug report via an assert  
   // or report macro.  
   // This program sends all report types to STDOUT.  
   _CrtSetReportMode(_CRT_WARN, _CRTDBG_MODE_FILE);  
   _CrtSetReportFile(_CRT_WARN, _CRTDBG_FILE_STDOUT);  
   _CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);  
   _CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDOUT);  
   _CrtSetReportMode(_CRT_ASSERT, _CRTDBG_MODE_FILE);  
   _CrtSetReportFile(_CRT_ASSERT, _CRTDBG_FILE_STDOUT);  
  
   // Allocate and assign the pointer variables.  
   p1 = (char *)malloc(10);  
   strcpy_s(p1, 10, "I am p1");  
   p2 = (char *)malloc(10);  
   strcpy_s(p2, 10, "I am p2");  
  
   // Use the report macros as a debugging  
   // warning mechanism, similar to printf.  
   // Use the assert macros to check if the   
   // p1 and p2 variables are equivalent.  
   // If the expression fails, _ASSERTE will  
   // include a string representation of the  
   // failed expression in the report.  
   // _ASSERT does not include the  
   // expression in the generated report.  
   _RPT0(_CRT_WARN,  
       "Use the assert macros to evaluate the expression p1 == p2.\n");  
   _RPTF2(_CRT_WARN, "\n Will _ASSERT find '%s' == '%s' ?\n", p1, p2);  
   _ASSERT(p1 == p2);  
  
   _RPTF2(_CRT_WARN, "\n\n Will _ASSERTE find '%s' == '%s' ?\n",  
          p1, p2);  
   _ASSERTE(p1 == p2);  
  
   _RPT2(_CRT_ERROR, "'%s' != '%s'\n", p1, p2);  
  
   free(p2);  
   free(p1);  
  
   return 0;  
}  
```  
  
```Output  
Use the assert macros to evaluate the expression p1 == p2.  
crt_ASSERT_macro.c(54) :   
 Will _ASSERT find 'I am p1' == 'I am p2' ?  
crt_ASSERT_macro.c(55) : Assertion failed!  
crt_ASSERT_macro.c(58) :   
  
 Will _ASSERTE find 'I am p1' == 'I am p2' ?  
crt_ASSERT_macro.c(59) : Assertion failed: p1 == p2  
'I am p1' != 'I am p2'  
```  
  
## <a name="see-also"></a>参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)   
 [assert マクロ、_assert、_wassert](../../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [_RPT、_RPTF、_RPTW、_RPTFW のマクロ](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)