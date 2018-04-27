---
title: _commit | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _commit
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _commit
- commit
dev_langs:
- C++
helpviewer_keywords:
- files [C++], flushing
- flushing files to disk
- commit function
- _commit function
- committing files to disk
ms.assetid: d0c74d3a-4f2d-4fb0-b140-2d687db3d233
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9396fd502f5137b469c9f92110bfc23c9d2fb246
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="commit"></a>_commit

ファイルを直接ディスクにフラッシュします。

## <a name="syntax"></a>構文

```C
int _commit(
   int fd
);
```

### <a name="parameters"></a>パラメーター

*fd*<br/>
開いているファイルを参照するファイル記述子。

## <a name="return-value"></a>戻り値

**_commit**ファイルが正常に 0 を返しますディスクにフラッシュします。 戻り値-1 はエラーを示します。

## <a name="remarks"></a>コメント

**_Commit**関数は、オペレーティング システムに関連付けられているファイルに書き込む*fd*をディスクにします。 この関数を呼び出すと、オペレーティング システムのタイミングではなく、即時に指定したファイルがフラッシュされます。

場合*fd* 、無効なファイル記述子で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、関数は-1 を返しますと**errno**に設定されている**EBADF**です。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|省略可能なヘッダー|
|-------------|---------------------|----------------------|
|**_commit**|\<io.h>|\<errno.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[下位入出力](../../c-runtime-library/low-level-i-o.md)<br/>
[_creat、_wcreat](creat-wcreat.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_read](read.md)<br/>
[_write](write.md)<br/>
