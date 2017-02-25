---
title: "_CrtDbgReport、_CrtDbgReportW | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtDbgReport"
  - "_CrtDbgReportW"
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
  - "CrtDbgReport"
  - "CrtDbgReportW"
  - "_CrtDbgReportW"
  - "_CrtDbgReport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "デバッグ レポート"
  - "_CrtDbgReport 関数"
  - "CrtDbgReport 関数"
  - "CrtDbgReportW 関数"
  - "_CrtDbgReportW 関数"
ms.assetid: 6e581fb6-f7fb-4716-9432-f0145d639ecc
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _CrtDbgReport、_CrtDbgReportW
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

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
 レポートのすべての宛先について、`_CrtDbgReport` および `_CrtDbgReportW` は、エラーが発生した場合は –1、エラーが発生しなかった場合は 0 を返します。 ただし、クリックしたレポートの宛先がデバッグ メッセージ ウィンドウとユーザーの場合、 **再試行** ボタン、これらの関数は 1 を返します。 ユーザーがクリックした場合、 **中止** ボタン デバッグ メッセージ ウィンドウでこれらの関数すぐに中止され、値は返されません。  
  
  [_RPT、_RPTF](../Topic/_RPT,%20_RPTF,%20_RPTW,%20_RPTFW%20Macros.md) マクロの呼び出しをデバッグ `_CrtDbgReport` レポートをデバッグを生成します。 これらのマクロのワイド文字バージョンと [_ASSERT & #91。&#93;](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md), 、`_RPTW``n` と `_RPTFW``n`, を使用して `_CrtDbgReportW` レポートをデバッグを生成します。 `_CrtDbgReport` または `_CrtDbgReportW` が 1 を返す場合は、Just-In-Time (JIT) デバッグが有効であれば、これらのマクロ デバッガーが開始しています。  
  
## <a name="remarks"></a>コメント  
 `_CrtDbgReport` および `_CrtDbgReportW` は、3 種類の宛先へデバッグ レポートを送信できます。デバッグ レポート ファイル、デバッグ モニター ([!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] デバッガー)、またはデバッグ メッセージ ウィンドウです。 2 つの構成関数 [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) と [_CrtSetReportFile](../Topic/_CrtSetReportFile.md), は、各レポートの種類の宛先の指定に使用します。 これらの関数では、各レポートの種類に対するレポートの宛先を個別に管理できます。 たとえば、`reportType` の `_CRT_WARN` をデバッグ モニターのみに送信したり、`reportType` の `_CRT_ASSERT` をデバッグ メッセージ ウィンドウとユーザー定義のレポート ファイルに送信するよう指定できます。  
  
 `_CrtDbgReportW` 関数は、`_CrtDbgReport` 関数のワイド文字バージョンです。 すべての出力および文字列のパラメーターは、ワイド文字列内にあり、それ以外の場合は 1 バイト文字バージョンと同じです。  
  
 `_CrtDbgReport` および `_CrtDbgReportW` は、`argument` または `n` 関数により定義されている同じ規則を使用して、`format`[`printf`] 引数を `wprintf` 文字列に置き換えることでデバッグ レポートのユーザー メッセージを作成します。 次にこれらの関数は、`reportType` に定義されている現在のレポート モードおよびファイルに基づいて、デバッグ レポートを生成し、宛先を決定します。 レポートがデバッグ メッセージ ウィンドウに送信される場合、ウィンドウに表示される情報には `filename`、`lineNumber`、および `moduleName` が含まれます。  
  
 次の表に、`_CrtDbgReport` および `_CrtDbgReportW` のレポート モードとファイルで使用できるオプションおよび結果の動作を示します。 これらのオプションは、\<crtdbg.h> でビット フラグとして定義されています。  
  
|レポート モード|レポート ファイル|`_CrtDbgReport` および `_CrtDbgReportW` の動作|  
|-----------------|-----------------|------------------------------------------------|  
|`_CRTDBG_MODE_DEBUG`|利用不可|Windows を使用して、メッセージを書き込みます [OutputDebugString](http://msdn.microsoft.com/library/windows/desktop/aa363362.aspx) API です。|  
|`_CRTDBG_MODE_WNDW`|利用不可|Windows を呼び出す [メッセージ ボックス](http://msdn.microsoft.com/library/windows/desktop/ms645505) と共にメッセージを表示するメッセージ ボックスを作成する API **中止**, 、**再試行**, と **無視** ボタン。 ユーザーがクリックすると **中止**, 、`_CrtDbgReport` または `_CrtDbgReport` すぐに中止します。 ユーザーがクリックすると **再試行**, 、1 を返します。 ユーザーがクリックした場合 **を無視する**, 、実行が継続し、 `_CrtDbgReport` と `_CrtDbgReportW` 0 を返します。 クリックすると **無視** 、エラー状態が「未定義の動作」多くの場合、結果に存在する場合|  
|`_CRTDBG_MODE_FILE`|`__HFILE`|ユーザーが指定したメッセージを書き込みます `HANDLE`, 、Windows を使用して [WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747.aspx) API とはファイル ハンドルの有効性を検証しません。 アプリケーションは、レポート ファイルを開くと、有効なファイル ハンドルを渡すことを担当します。|  
|`_CRTDBG_MODE_FILE`|`_CRTDBG_FILE_STDERR`|`stderr` にメッセージを書き込みます。|  
|`_CRTDBG_MODE_FILE`|`_CRTDBG_FILE_STDOUT`|
          `stdout` にメッセージを書き込みます。|  
  
 レポートは 1 つ、2 つ、または 3 つの宛先に送信できます。またどの宛先にも送信しないこともできます。 詳細については、レポート モードおよびレポート ファイルを指定する、次を参照してください。、 [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) と [_CrtSetReportFile](../Topic/_CrtSetReportFile.md) 関数です。 デバッグ マクロを使用して、レポートなどの機能に関する詳細については、次を参照してください。 [レポート用マクロ](../Topic/Macros%20for%20Reporting.md)します。  
  
 によって提供されるよりさらに柔軟性が、アプリケーションに必要なかどうかは `_CrtDbgReport` と `_CrtDbgReportW`, 、独自のレポート関数を記述し、それをレポート メカニズムを使用して、C ランタイム ライブラリにフック、 [_CrtSetReportHook](../../c-runtime-library/reference/crtsetreporthook.md) 関数です。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_CrtDbgReport`|\<crtdbg.h>|  
|`_CrtDbgReportW`|\<crtdbg.h>|  
  
 `_CrtDbgReport` および `_CrtDbgReportW` は Microsoft 拡張機能です。 詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 デバッグ バージョン [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md) のみです。  
  
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
  
 参照してください [crt_dbg2](http://msdn.microsoft.com/ja-jp/21e1346a-6a17-4f57-b275-c76813089167) レポート関数を変更する方法の例です。  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
  
-   [System::Diagnostics::Debug::Write](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.write.aspx)  
  
-   [System::Diagnostics::Debug::Writeline](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.writeline.aspx)  
  
-   [System::Diagnostics::Debug::WriteIf](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.writeif.aspx)  
  
-   [System::Diagnostics::Debug::WriteLineIf](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.writelineif.aspx)  
  
## <a name="see-also"></a>関連項目  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)   
 [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md)   
 [_CrtSetReportFile](../Topic/_CrtSetReportFile.md)   
 [printf、_printf_l、wprintf、_wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [_DEBUG](../Topic/_DEBUG.md)