---
title: _CrtSetReportHook | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtSetReportHook
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
- _CrtSetReportHook
- CrtSetReportHook
dev_langs:
- C++
helpviewer_keywords:
- CrtSetReportHook function
- _CrtSetReportHook function
ms.assetid: 1ae7c64f-8c84-4797-9574-b59f00f7a509
caps.latest.revision: 13
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
ms.openlocfilehash: 58def9d726c74e67df67bcacb108f9643027a952
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="crtsetreporthook"></a>_CrtSetReportHook
C ランタイム デバッグ レポート プロセスにフックして、クライアント定義レポート関数をインストールします (デバッグ バージョンのみ)。  
  
## <a name="syntax"></a>構文  
  
```  
_CRT_REPORT_HOOK _CrtSetReportHook(   
   _CRT_REPORT_HOOK reportHook   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `reportHook`  
 C ランタイム デバッグ レポート プロセスにフックする新しいクライアント定義レポート関数。  
  
## <a name="return-value"></a>戻り値  
 以前のクライアント定義レポート関数を返します。  
  
## <a name="remarks"></a>コメント  
 `_CrtSetReportHook` は、C ランタイム デバッグ ライブラリのレポート プロセスのためにアプリケーションが独自のレポート関数を使用できるようにします。 その結果、デバッグ レポートを生成するために [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) が呼び出されるたびに、アプリケーションのレポート関数が先に呼び出されます。 この機能によって、アプリケーションはデバッグ レポートのフィルター処理などの操作を実行して特定の割り当ての種類に焦点を当てたり、`_CrtDbgReport` では対応できない宛先にレポートを送信したりすることができます。 [_DEBUG](../../c-runtime-library/debug.md) が定義されていない場合、`_CrtSetReportHook` の呼び出しは前処理で削除されます。  
  
 `_CrtSetReportHook` のより堅牢なバージョンについては、「[_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md)」を参照してください。  
  
 `_CrtSetReportHook` 関数は、`reportHook` で指定された新しいクライアント定義レポート関数をインストールし、以前のクライアント定義フックを返します。 次の例は、クライアント定義レポート フックをどのようにプロトタイプ宣言するかを示しています。  
  
```  
int YourReportHook( int reportType, char *message, int *returnValue );  
```  
  
 ここで、`reportType` はデバッグ レポートの種類 (`_CRT_WARN`、`_CRT_ERROR`、または `_CRT_ASSERT`) で、`message` はレポートに含められる完全にアセンブルされたデバッグ ユーザー メッセージです。また、`returnValue` は `_CrtDbgReport` によって返される、クライアント定義レポート関数によって指定された値です。 使用できるレポートの種類の詳細については、[_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) 関数を参照してください。  
  
 クライアント定義レポート関数が、それ以上のレポートを必要としないほど完全にデバッグ メッセージを処理できる場合は、関数が `TRUE` を返すようにします。 関数が `FALSE` を返す場合は、`_CrtDbgReport` が呼び出され、レポートの種類、モード、およびファイルに関する現在の設定を使用してデバッグ レポートが生成されます。 また、`_CrtDbgReport` の `returnValue` 戻り値を指定することで、デバッグ ブレークが発生するかどうかをアプリケーションが制御することもできます。 デバッグ レポートがどのように構成および生成されるかの詳細については、「`_CrtSetReportMode`」、「[_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md)」、および「`_CrtDbgReport`」を参照してください。  
  
 フックをサポートするその他のランタイム関数の使い方の詳細と、独自のクライアント定義フック関数の記述方法については、「[デバッグ用フック関数の作成](/visualstudio/debugger/debug-hook-function-writing)」を参照してください。  
  
> [!NOTE]
>  アプリケーションが `/clr` でコンパイルされ、main が終了した後でレポート関数が呼び出された場合、レポート関数がいずれかの CRT 関数を呼び出すと、CLR は例外をスローします。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_CrtSetReportHook`|\<crtdbg.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## <a name="see-also"></a>関連項目  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)   
 [_CrtGetReportHook](../../c-runtime-library/reference/crtgetreporthook.md)
