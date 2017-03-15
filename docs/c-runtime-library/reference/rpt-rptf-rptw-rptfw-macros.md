---
title: "_RPT、_RPTF、_RPTW、_RPTFW のマクロ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- RPT3
- RPTF4
- _RPT4
- RPT1
- _RPTF0
- RPTF3
- _RPTF4
- RPTF1
- RPT4
- _RPT1
- _RPT0
- RPT0
- _RPTF2
- RPTF0
- _RPT3
- _RPT2
- _RPTF3
- RPT2
- _RPTF1
dev_langs:
- C++
helpviewer_keywords:
- debugging [CRT], using macros
- _RPTW3 macro
- _RPT0 macro
- RPTW4 macro
- _RPTF3 macro
- _RPTW4 macro
- RPTF4 macro
- RPTFW2 macro
- RPTW macros
- RPT1 macro
- _RPTF macros
- RPTFW3 macro
- _RPTW0 macro
- _RPTF0 macro
- macros, debugging with
- _RPTW2 macro
- RPTF3 macro
- RPT3 macro
- RPT0 macro
- _RPT macros
- RPTW3 macro
- _RPTFW macros
- debug reporting macros
- RPTF macros
- RPT macros
- _RPTW macros
- RPTF2 macro
- _RPTF1 macro
- _RPT1 macro
- _RPT4 macro
- _RPTFW2 macro
- _RPTFW1 macro
- RPTF0 macro
- _RPT2 macro
- RPTFW macros
- _RPTW1 macro
- _RPTFW0 macro
- RPT4 macro
- _RPT3 macro
- _RPTFW3 macro
- _RPTF4 macro
- _RPTFW4 macro
- _RPTF2 macro
- RPTW0 macro
- RPTFW4 macro
- RPTFW0 macro
- RPTW2 macro
- RPTF1 macro
- RPT2 macro
- RPTFW1 macro
- RPTW1 macro
ms.assetid: a5bf8b30-57f7-4971-8030-e773b7a1ae13
caps.latest.revision: 14
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: d8611402652268e0a85170a36355619e5c7335ac
ms.lasthandoff: 02/24/2017

---
# <a name="rpt-rptf-rptw-rptfw-macros"></a>_RPT、_RPTF、_RPTW、_RPTFW のマクロ
デバッグ レポートを生成してアプリケーションの進行状況を追跡します (デバッグ バージョンのみ)。 *n* には、`args` 内の引数の数を指定し、0、1、2、3、4、または 5 のいずれかを使用できることにご注意ください。  
  
## <a name="syntax"></a>構文  
  
```  
  
      _RPT  
      n  
      (  
   reportType,  
   format,  
...[args]  
);  
_RPTFn(  
   reportType,  
   format,  
   [args]  
);  
_RPTWn(  
   reportType,  
   format   
   [args]  
);  
_RPTFWn(  
   reportType,  
   format   
   [args]  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `reportType`  
 レポートの種類: `_CRT_WARN`、`_CRT_ERROR`、または `_CRT_ASSERT`。  
  
 `format`  
 ユーザー メッセージの作成に使用される書式指定文字列。  
  
 `args`  
 `format` で使用される代替引数。  
  
## <a name="remarks"></a>コメント  
 これらのマクロはどれも、`reportType` パラメーターと `format` パラメーターを受け取ります。 また、マクロ名に追加された数字で示される最大&4; つの追加引数を受け取る場合もあります。 たとえば、`_RPT0` と `_RPTF0` は追加引数を受け取らず、`_RPT1` と `_RPTF1` は `arg1` を、`_RPT2` と `_RPTF2` は `arg1` と `arg2` を受け取るなどです。  
  
 `_RPT` マクロと `_RPTF` マクロは、デバッグ プロセス中のアプリケーションの進行状況を追跡するために使用できるため、[printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) 関数に似ています。 ただし、アプリケーションの製品版ビルドで呼び出されないようにするために `#ifdef` ステートメントで囲む必要がないため、これらのマクロには `printf` よりも高い柔軟性があります。 この柔軟性は、[_DEBUG](../../c-runtime-library/debug.md) マクロを使用することで実現できます。`_RPT` マクロと `_RPTF` マクロを使用できるのは、`_DEBUG` フラグが定義されている場合のみです。 `_DEBUG` が定義されていない場合、これらのマクロの呼び出しは前処理で削除されます。  
  
 `_RPTW` マクロと `_RPTFW` マクロは、これらのマクロのワイド文字バージョンです。 これらは、`wprintf` に似ており、引数としてワイド文字列を受け取ります。  
  
 `_RPT` マクロは [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) 関数を呼び出して、ユーザー メッセージを含むデバッグ レポートを生成します。 `_RPTW` マクロは、`_CrtDbgReportW` 関数を呼び出して、ワイド文字で同じレポートを生成します。 `_RPTF` マクロと `_RPTFW` マクロは、ユーザー メッセージに加え、レポート マクロが呼び出された場所のソース ファイルと行番号を含むデバッグ レポートを作成します。 ユーザー メッセージは、[printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) 関数で定義されている同じ規則を使用して、`arg`[*n*] 引数を `format` 文字列に置き換えることで作成されます。  
  
 `_CrtDbgReport` または `_CrtDbgReportW` は、`reportType` に定義されている現在のレポート モードとファイルに基づいて、デバッグ レポートを生成し、その宛先を決定します。 [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) 関数と [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) 関数は、各レポートの種類の宛先を定義するために使用されます。  
  
 `_RPT` マクロが呼び出され、`_CrtSetReportMode` と `_CrtSetReportFile` のいずれも呼び出されていない場合は、メッセージは次のように表示されます。  
  
|レポートの種類|出力先|  
|-----------------|------------------------|  
|`_CRT_WARN`|警告テキストは表示されません。|  
|`_CRT_ERROR`|ポップアップ ウィンドウ。 `_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_WNDW);` が指定されている場合と同じです。|  
|`_CRT_ASSERT`|`_CRT_ERROR` と同じ。|  
  
 宛先がデバッグ メッセージ ウィンドウであるときにユーザーが **[再試行]** ボタンを選択すると、`_CrtDbgReport` または `_CrtDbgReportW` は 1 を返します。これにより、これらのマクロはデバッガーを開始します (Just-In-Time (JIT) デバッグが有効な場合)。 これらのマクロをデバッグ エラーの処理機構として使用する方法の詳細については、[確認とレポート用マクロの使用](/visualstudio/debugger/macros-for-reporting)に関するページを参照してください。  
  
 デバッグ レポートを生成するマクロが他にも&2; つ存在します。 [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) マクロは、その式の引数が FALSE に評価される場合にのみ、レポートを生成します。 [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) は `_ASSERT` とまったく同じですが、生成されるレポートに失敗した式が含まれます。  
  
## <a name="requirements"></a>要件  
  
|マクロ|必須ヘッダー|  
|-----------|---------------------|  
|`_RPT` マクロ|\<crtdbg.h>|  
|`_RPTF` マクロ|\<crtdbg.h>|  
|`_RPTW` マクロ|\<crtdbg.h>|  
|`_RPTFW` マクロ|\<crtdbg.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
 これらはマクロであり、Crtdbg.h を組み込むと取得されますが、アプリケーションは、デバッグ ライブラリのいずれかとリンクする必要があります。これらのマクロは、他のランタイム関数を呼び出すからです。  
  
## <a name="example"></a>例  
 「[_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)」のトピックの例を参照してください。  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)
