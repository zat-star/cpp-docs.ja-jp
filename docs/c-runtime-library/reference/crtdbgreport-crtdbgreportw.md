---
title: "_CrtDbgReport、_CrtDbgReportW | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CrtDbgReport
- _CrtDbgReportW
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
- CrtDbgReport
- CrtDbgReportW
- _CrtDbgReportW
- _CrtDbgReport
dev_langs:
- C++
helpviewer_keywords:
- debug reporting
- _CrtDbgReport function
- CrtDbgReport function
- CrtDbgReportW function
- _CrtDbgReportW function
ms.assetid: 6e581fb6-f7fb-4716-9432-f0145d639ecc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 45cd908519fbacb42e017676a245451a5966891e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="crtdbgreport-crtdbgreportw"></a>_CrtDbgReport、_CrtDbgReportW
デバッグ メッセージのあるレポートを生成し、3 つの宛先 (デバッグ バージョンのみ) にレポートを送信します。  
  
## <a name="syntax"></a>構文  
  
```  
int _CrtDbgReport(   
   int reportType,  
   const char *filename,  
   int linenumber,  
   const char *moduleName,  
   const char *format [,  
   argument] ...   
);  
int _CrtDbgReportW(   
   int reportType,  
   const wchar_t *filename,  
   int linenumber,  
   const wchar_t *moduleName,  
   const wchar_t *format [,  
   argument] ...   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `reportType`  
 レポートの種類: `_CRT_WARN`、`_CRT_ERROR`、および `_CRT_ASSERT`。  
  
 `filename`  
 アサート/レポートが発生したソース ファイル名へのポインターまたは `NULL`。  
  
 `linenumber`  
 アサート/レポートが発生したソース ファイル名の行番号または `NULL`。  
  
 `moduleName`  
 アサートまたはレポートが発生したモジュール (.exe または .dll) 名へのポインター。  
  
 `format`  
 ユーザー メッセージの作成に使用される書式指定文字列へのポインター。  
  
 `argument`  
 `format` で使用される省略可能な代用引数。  
  
## <a name="return-value"></a>戻り値  
 すべてのレポート送信先`_CrtDbgReport`と`_CrtDbgReportW`エラーが発生しなかった場合、エラーが発生した場合は-1、0 を返します。 ただし、レポートの宛先がデバッグ メッセージ ウィンドウで、ユーザーが **[再試行]** をクリックすると、これらの関数は 1 を返します。 ユーザーがデバッグ メッセージ ウィンドウの **[中止]** をクリックすると、関数はすぐに中止され、値は返されません。  
  
 [_RPT、_RPTF](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) デバッグ マクロは `_CrtDbgReport` を呼び出して、デバッグ レポートを生成します。 これらのマクロのワイド文字バージョンは、[_ASSERT&#91;E&#93;](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)、`_RPTW n`、および `_RPTFW n` と共に、`_CrtDbgReportW` を使用してデバッグ レポートを生成します。 `_CrtDbgReport` または `_CrtDbgReportW` が 1 を返す場合は、Just-In-Time (JIT) デバッグが有効であれば、これらのマクロ デバッガーが開始しています。  
  
## <a name="remarks"></a>コメント  
 `_CrtDbgReport` および `_CrtDbgReportW` は、3 種類の宛先へデバッグ レポートを送信できます。デバッグ レポート ファイル、デバッグ モニター ([!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] デバッガー)、またはデバッグ メッセージ ウィンドウです。 2 つの構成関数 [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) および [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) は、各レポートの種類の出力先を指定するために使用されます。 これらの関数では、各レポートの種類に対するレポートの宛先を個別に管理できます。 たとえば、`reportType` の `_CRT_WARN` をデバッグ モニターのみに送信したり、`reportType` の `_CRT_ASSERT` をデバッグ メッセージ ウィンドウとユーザー定義のレポート ファイルに送信するよう指定できます。  
  
 `_CrtDbgReportW` 関数は、`_CrtDbgReport` 関数のワイド文字バージョンです。 すべての出力および文字列のパラメーターは、ワイド文字列内にあり、それ以外の場合は 1 バイト文字バージョンと同じです。  
  
 `_CrtDbgReport` および `_CrtDbgReportW` は、`argument` または `n` 関数により定義されている同じ規則を使用して、`format`[`printf`] 引数を `wprintf` 文字列に置き換えることでデバッグ レポートのユーザー メッセージを作成します。 次にこれらの関数は、`reportType` に定義されている現在のレポート モードおよびファイルに基づいて、デバッグ レポートを生成し、宛先を決定します。 レポートがデバッグ メッセージ ウィンドウに送信される場合、ウィンドウに表示される情報には `filename`、`lineNumber`、および `moduleName` が含まれます。  
  
 次の表に、`_CrtDbgReport` および `_CrtDbgReportW` のレポート モードとファイルで使用できるオプションおよび結果の動作を示します。 これらのオプションは、\<crtdbg.h> でビット フラグとして定義されています。  
  
|レポート モード|レポート ファイル|`_CrtDbgReport` および `_CrtDbgReportW` の動作|  
|-----------------|-----------------|------------------------------------------------|  
|`_CRTDBG_MODE_DEBUG`|利用不可|Windows [OutputDebugString](http://msdn.microsoft.com/library/windows/desktop/aa363362.aspx) API にメッセージを書き込みます。|  
|`_CRTDBG_MODE_WNDW`|利用不可|Windows [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) API を呼び出して、メッセージおよび **[中止]**、**[再試行]**、**[無視]** の各ボタンを表示するメッセージ ボックスを作成します。 ユーザーが **[中止]** をクリックすると、`_CrtDbgReport` または `_CrtDbgReport` はすぐに中止されます。 ユーザーが **[再試行]** をクリックすると、1 を返します。 ユーザーが **[無視]** をクリックすると、実行は継続され、`_CrtDbgReport` および `_CrtDbgReportW` は 0 を返します。 エラー状況が存在するときに **[無視]** をクリックすると、"未定義の動作" という結果になることがよくあります。|  
|`_CRTDBG_MODE_FILE`|`__HFILE`|Windows [WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747.aspx) API を使用して、ユーザーが指定した `HANDLE` にメッセージを書き込みますが、ハンドルの有効性は検証しません。アプリケーションは、レポート ファイルを開き、有効なファイル ハンドルを渡す役割を果たします。|  
|`_CRTDBG_MODE_FILE`|`_CRTDBG_FILE_STDERR`|`stderr` にメッセージを書き込みます。|  
|`_CRTDBG_MODE_FILE`|`_CRTDBG_FILE_STDOUT`|`stdout` にメッセージを書き込みます。|  
  
 レポートは 1 つ、2 つ、または 3 つの宛先に送信できます。またどの宛先にも送信しないこともできます。 レポート モードおよびレポート ファイルを指定する方法の詳細については、「[_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md)」および「[_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md)」関数を参照してください。 デバッグ マクロおよびレポート関数の使用方法の詳細については、「[レポート用マクロの使用](/visualstudio/debugger/macros-for-reporting)」を参照してください。  
  
 アプリケーションで `_CrtDbgReport` および `_CrtDbgReportW` で提供されるよりさらに柔軟性が必要な場合は、独自のレポート関数を書き込み、[_CrtSetReportHook](../../c-runtime-library/reference/crtsetreporthook.md) 関数を使用してそれを C ランタイム ライブラリのレポート機構にフックすることができます。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_CrtDbgReport`|\<crtdbg.h>|  
|`_CrtDbgReportW`|\<crtdbg.h>|  
  
 `_CrtDbgReport` および `_CrtDbgReportW` は Microsoft 拡張機能です。 詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## <a name="example"></a>例  
  
```  
// crt_crtdbgreport.c  
#include <crtdbg.h>  
  
int main(int argc, char *argv[]) {  
#ifdef _DEBUG  
   _CrtDbgReport(_CRT_ASSERT, __FILE__, __LINE__, argv[0], NULL);  
#endif  
}  
```  
  
 レポート関数を変更する方法の例については、「[crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)   
 [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md)   
 [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md)   
 [printf、_printf_l、wprintf、_wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [_DEBUG](../../c-runtime-library/debug.md)