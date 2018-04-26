---
title: _findclose | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _findclose
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _findclose
- findclose
dev_langs:
- C++
helpviewer_keywords:
- _findclose function
- findclose function
ms.assetid: 9216c573-0878-444c-b5d7-cdaf16fb9163
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 89c1f515bb072c649a93b77e49b500ea4636e423
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="findclose"></a>_findclose

指定した検索のハンドルを終了し、関連付けられているリソースを解放します。

## <a name="syntax"></a>構文

```C
int _findclose(
   intptr_t handle
);
```

### <a name="parameters"></a>パラメーター

*handle*<br/>
前の呼び出しによって返されたハンドルは検索 **_findfirst**です。

## <a name="return-value"></a>戻り値

成功した場合、 **_findclose** 0 を返します。 -1 を返しますそれ以外の場合、設定と**errno**に**ENOENT**、これ以上の一致するファイルがあることを示すが見つかりませんでした。

## <a name="requirements"></a>要件

|関数|必須ヘッダー|
|--------------|---------------------|
|**_findclose**|\<io.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[システム コール](../../c-runtime-library/system-calls.md)<br/>
[ファイル名検索関数](../../c-runtime-library/filename-search-functions.md)<br/>
