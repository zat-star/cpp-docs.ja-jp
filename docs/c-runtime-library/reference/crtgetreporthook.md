---
title: _CrtGetReportHook | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _CrtGetReportHook
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
- CrtGetReportHook
- _CrtGetReportHook
dev_langs:
- C++
helpviewer_keywords:
- CrtGetReportHook function
- _CrtGetReportHook function
ms.assetid: 922758ed-7edd-4359-9c92-0535192dc11a
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4b1e499b1663cbde3bcaa0a01a26e96d544ca390
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="crtgetreporthook"></a>_CrtGetReportHook

デバッグ レポート プロセスのために C ランタイムにフックするクライアント定義レポート関数を取得します (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C
_CRT_REPORT_HOOK _CrtGetReportHook( void );
```

## <a name="return-value"></a>戻り値

現在のクライアント定義レポート関数を返します。

## <a name="remarks"></a>コメント

**_CrtGetReportHook**アプリケーションは、C ランタイム デバッグ ライブラリのレポート プロセスの現在のレポート関数を取得します。

フックをサポートするその他のランタイム関数の使い方の詳細と、独自のクライアント定義フック関数の記述方法については、「[デバッグ用フック関数の作成](/visualstudio/debugger/debug-hook-function-writing)」を参照してください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_CrtGetReportHook**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="example"></a>例

使用する方法のサンプルについては **_CrtSetReportHook**を参照してください[レポート](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/report)です。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetReportHook](crtsetreporthook.md)<br/>
