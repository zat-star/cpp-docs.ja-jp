---
title: _CrtSetReportMode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtSetReportMode
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
- _CrtSetReportMode
- CrtSetReportMode
dev_langs:
- C++
helpviewer_keywords:
- _CrtSetReportMode function
- CrtSetReportMode function
ms.assetid: 3ecc6a12-afdd-4242-b046-8187ff6d4b36
caps.latest.revision: 15
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: b7e3cb7562fb63467ef0e0ee28861936fb820fa3
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="crtsetreportmode"></a>_CrtSetReportMode
`_CrtDbgReport` と、[_ASSERT、_ASSERTE、_ASSERT_EXPR のマクロ](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)、[_ASSERT、_ASSERTE、_ASSERT_EXPR のマクロ](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)、[_RPT、_RPTF、_RPTW、_RPTFW のマクロ](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)、[_RPT、_RPTF、_RPTW、_RPTFW のマクロ](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) (デバッグ バージョンのみ) など、[_CrtDbgReport、_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) を呼び出すマクロにより生成された特定のレポート タイプの宛先を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
int _CrtSetReportMode(   
   int reportType,  
   int reportMode   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `reportType`  
 レポートの種類: `_CRT_WARN`、`_CRT_ERROR`、および `_CRT_ASSERT`。  
  
 `reportMode`  
 `reportType` の新しいレポート モード。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合、`_CrtSetReportMode` は `reportType` で指定されたレポートの種類の以前のレポート モードを返します。 無効な値が `reportType` として渡されるか、無効なモードが `reportMode` に指定されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、`_CrtSetReportMode` は無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、-1 を返します。 詳しくは、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
## <a name="remarks"></a>コメント  
 `_CrtSetReportMode` は、`_CrtDbgReport` の出力先を指定します。 マクロ `_ASSERT`、`_ASSERTE`、`_RPT`、および `_RPTF` は `_CrtDbgReport` を呼び出すので、`_CrtSetReportMode` はこれらのマクロで指定されるテキストの出力先を指定します。  
  
 [_DEBUG](../../c-runtime-library/debug.md) が定義されていない場合、 `_CrtSetReportMode` の呼び出しは前処理で削除されます。  
  
 メッセージの出力先を定義するために `_CrtSetReportMode` を呼び出さないと、次の既定値が有効になります。  
  
-   アサーション エラーとエラーは、デバッグ メッセージ ウィンドウに送られます。  
  
-   Windows アプリケーションからの警告は、デバッガーの出力ウィンドウに送られます。  
  
-   コンソール アプリケーションからの警告は表示されません。  
  
 次の表は、Crtdbg.h で定義されているレポートの種類の一覧です。  
  
|レポートの種類|説明|  
|-----------------|-----------------|  
|`_CRT_WARN`|早急の対応を必要としない警告、メッセージ、および情報。|  
|`_CRT_ERROR`|エラー、回復不能な問題、および早急の対応を必要とする問題。|  
|`_CRT_ASSERT`|アサーション エラー (`FALSE` に評価される、アサート対象の式)。|  
  
 `_CrtSetReportMode` 関数は、`reportMode` で指定されたレポートの種類に対して `reportType` で指定された新しいレポート モードを割り当て、`reportType` に対して以前に定義されたレポート モードを返します。 次の表は `reportMode` で使用できる選択肢と、結果となる `_CrtDbgReport` の動作の一覧です。 これらのオプションは、Crtdbg.h でビット フラグとして定義されています。  
  
|レポート モード|_CrtDbgReport の動作|  
|-----------------|-----------------------------|  
|`_CRTDBG_MODE_DEBUG`|デバッガーの出力ウィンドウにメッセージを書き込みます。|  
|`_CRTDBG_MODE_FILE`|ユーザーが指定したファイル ハンドルにメッセージを書き込みます。 書き込み先として使用する特定のファイルまたはストリームを定義するには、[_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) を呼び出す必要があります。|  
|`_CRTDBG_MODE_WNDW`|`Abort`、`Retry`、および `Ignore` ボタンと共にメッセージを表示するメッセージ ボックスを作成します。|  
|`_CRTDBG_REPORT_MODE`|指定した `reportMode` の `reportType` を返します。<br /><br /> 1   `_CRTDBG_MODE_FILE`<br /><br /> 2   `_CRTDBG_MODE_DEBUG`<br /><br /> 4   `_CRTDBG_MODE_WNDW`|  
  
 各レポートの種類は、1 つ、2 つ、または 3 つのモードか、モードなしを使用して報告できます。 したがって、1 つのレポートの種類に対して複数の書き込み先を定義することができます。 たとえば、次のコード片は、デバッグ メッセージ ウィンドウと `stderr` の両方に送られるアサーション エラーを発生させます。  
  
```  
_CrtSetReportMode( _CRT_ASSERT, _CRTDBG_MODE_FILE | _CRTDBG_MODE_WNDW );  
_CrtSetReportFile( _CRT_ASSERT, _CRTDBG_FILE_STDERR );  
```  
  
 さらに、各レポートの種類のレポート モードは、個別に制御できます。 たとえば、`reportType` の `_CRT_WARN` は出力デバッグ文字列に送り、`_CRT_ASSERT` は前に説明したようにデバッグ メッセージ ウィンドウを使用して表示し、`stderr` に送るように指定できます。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|-------------|---------------------|---------------------|  
|`_CrtSetReportMode`|\<crtdbg.h>|\<errno.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
 **ライブラリ:** [CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## <a name="see-also"></a>関連項目  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)
