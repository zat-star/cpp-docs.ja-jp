---
title: "_CrtSetReportMode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtSetReportMode"
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
  - "_CrtSetReportMode"
  - "CrtSetReportMode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CrtSetReportMode 関数"
  - "CrtSetReportMode 関数"
ms.assetid: 3ecc6a12-afdd-4242-b046-8187ff6d4b36
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _CrtSetReportMode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`_CrtDbgReport` と、[\_CrtDbgReport、\_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) を呼び出すいずれかのマクロ \([\_ASSERT、\_ASSERTE、\_ASSERT\_EXPR マクロ](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md)、[\_ASSERT、\_ASSERTE、\_ASSERT\_EXPR マクロ](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md)、[\_RPT、\_RPTF、\_RPTW、\_RPTFW のマクロ](../Topic/_RPT,%20_RPTF,%20_RPTW,%20_RPTFW%20Macros.md)、[\_RPT、\_RPTF、\_RPTW、\_RPTFW のマクロ](../Topic/_RPT,%20_RPTF,%20_RPTW,%20_RPTFW%20Macros.md) など\) によって生成される特定のレポートの種類の出力先を指定します \(デバッグ バージョンのみ\)。  
  
## 構文  
  
```  
int _CrtSetReportMode(   
   int reportType,  
   int reportMode   
);  
```  
  
#### パラメーター  
 `reportType`  
 レポートの種類: `_CRT_WARN`、`_CRT_ERROR`、および `_CRT_ASSERT`。  
  
 `reportMode`  
 `reportType` の新しいレポート モード。  
  
## 戻り値  
 正常に終了した場合、`_CrtSetReportMode` は `reportType` で指定されたレポートの種類の以前のレポート モードを返します。  無効な値が `reportType` として渡されるか、無効なモードが `reportMode` に指定されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、`_CrtSetReportMode` は無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、\-1 を返します。  詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `_CrtSetReportMode` は、`_CrtDbgReport` の出力先を指定します。  マクロ `_ASSERT`、`_ASSERTE`、`_RPT`、および `_RPTF` は `_CrtDbgReport` を呼び出すので、`_CrtSetReportMode` はこれらのマクロで指定されるテキストの出力先を指定します。  
  
 [\_DEBUG](../Topic/_DEBUG.md) が未定義の場合、`_CrtSetReportMode` の呼び出しはプリプロセスで削除されます。  
  
 メッセージの出力先を定義するために `_CrtSetReportMode` を呼び出さないと、次の既定値が有効になります。  
  
-   アサーション エラーとエラーは、デバッグ メッセージ ウィンドウに送られます。  
  
-   Windows アプリケーションからの警告は、デバッガーの出力ウィンドウに送られます。  
  
-   コンソール アプリケーションからの警告は表示されません。  
  
 次の表は、Crtdbg.h で定義されているレポートの種類の一覧です。  
  
|レポートの種類|説明|  
|-------------|--------|  
|`_CRT_WARN`|早急の対応を必要としない警告、メッセージ、および情報。|  
|`_CRT_ERROR`|エラー、回復不能な問題、および早急の対応を必要とする問題。|  
|`_CRT_ASSERT`|アサーション エラー \(`FALSE` に評価される、アサート対象の式\)。|  
  
 `_CrtSetReportMode` 関数は、`reportType` で指定されたレポートの種類に対して `reportMode` で指定された新しいレポート モードを割り当て、`reportType` に対して以前に定義されたレポート モードを返します。  次の表は `reportMode` で使用できる選択肢と、結果となる `_CrtDbgReport` の動作の一覧です。  これらのオプションは、Crtdbg.h でビット フラグとして定義されています。  
  
|レポート モード|\_CrtDbgReport の動作|  
|--------------|------------------------|  
|`_CRTDBG_MODE_DEBUG`|デバッガーの出力ウィンドウにメッセージを書き込みます。|  
|`_CRTDBG_MODE_FILE`|ユーザーが指定したファイル ハンドルにメッセージを書き込みます。  書き込み先として使用する特定のファイルまたはストリームを定義するには、[\_CrtSetReportFile](../Topic/_CrtSetReportFile.md) を呼び出す必要があります。|  
|`_CRTDBG_MODE_WNDW`|`Abort`、`Retry`、および `Ignore` ボタンと共にメッセージを表示するメッセージ ボックスを作成します。|  
|`_CRTDBG_REPORT_MODE`|指定した `reportType` の `reportMode` を返します。<br /><br /> 1   `_CRTDBG_MODE_FILE`<br /><br /> 2   `_CRTDBG_MODE_DEBUG`<br /><br /> 4   `_CRTDBG_MODE_WNDW`|  
  
 各レポートの種類は、1 つ、2 つ、または 3 つのモードか、モードなしを使用して報告できます。  したがって、1 つのレポートの種類に対して複数の書き込み先を定義することができます。  たとえば、次のコード片は、デバッグ メッセージ ウィンドウと `stderr` の両方に送られるアサーション エラーを発生させます。  
  
```  
_CrtSetReportMode( _CRT_ASSERT, _CRTDBG_MODE_FILE | _CRTDBG_MODE_WNDW );  
_CrtSetReportFile( _CRT_ASSERT, _CRTDBG_FILE_STDERR );  
```  
  
 さらに、各レポートの種類のレポート モードは、個別に制御できます。  たとえば、`_CRT_WARN` の `reportType` は出力デバッグ文字列に送り、`_CRT_ASSERT` は前に説明したようにデバッグ メッセージ ウィンドウを使用して表示し、`stderr` に送るように指定できます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|----------|------------|----------------|  
|`_CrtSetReportMode`|\<crtdbg.h\>|\<errno.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
 **ライブラリ:** [CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md) のデバッグ バージョンのみ。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)