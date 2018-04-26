---
title: _set_abort_behavior | Microsoft Docs
ms.custom: ''
ms.date: 1/02/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _set_abort_behavior
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_abort_behavior
- set_abort_behavior
dev_langs:
- C++
helpviewer_keywords:
- aborting programs
- _set_abort_behavior function
- set_abort_behavior function
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b7ee65b603997a0be4fe9e937299eab9520c6f5b
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="setabortbehavior"></a>_set_abort_behavior

プログラムが異常終了した場合に実行するアクションを指定します。

> [!NOTE]
> 使用しないで、[中止](abort.md)テスト シナリオまたはデバッグ シナリオを除く、Microsoft ストアのアプリをシャット ダウンする関数。 ストア アプリを閉じる方法はプログラムや UI はに従って許可されていません、 [Microsoft ストアのポリシー](http://go.microsoft.com/fwlink/?LinkId=865936)です。 詳細については、次を参照してください。 [UWP アプリのライフ サイクル](http://go.microsoft.com/fwlink/p/?LinkId=865934)です。

## <a name="syntax"></a>構文

```C
unsigned int _set_abort_behavior(
   unsigned int flags,
   unsigned int mask
);
```

### <a name="parameters"></a>パラメーター

*flags*<br/>
新しい値、[中止](abort.md)フラグ。

*マスク*<br/>
マスク、[中止](abort.md)フラグのビットを設定します。

## <a name="return-value"></a>戻り値

フラグの元の値。

## <a name="remarks"></a>コメント

2 つ[中止](abort.md)フラグ: **_WRITE_ABORT_MSG**と **_CALL_REPORTFAULT**です。 **_WRITE_ABORT_MSG**プログラムが異常終了したときに、説明のテキスト メッセージを印刷するかどうかを決定します。 そのアプリケーションが呼び出される、メッセージの状態、[中止](abort.md)関数。 既定の動作はメッセージを表示することです。 **_CALL_REPORTFAULT**場合は、設定、ワトソン クラッシュ ダンプが生成され、ときに報告されることを示す[中止](abort.md)と呼びます。 既定では、クラッシュ ダンプのレポートは、非デバッグ ビルドで有効になっています。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_set_abort_behavior**|\<stdlib.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_set_abort_behavior.c
// compile with: /TC
#include <stdlib.h>

int main()
{
   printf("Suppressing the abort message. If successful, this message"
          " will be the only output.\n");
   // Suppress the abort message
   _set_abort_behavior( 0, _WRITE_ABORT_MSG);
   abort();
}
```

```Output
Suppressing the abort message. If successful, this message will be the only output.
```

## <a name="see-also"></a>関連項目

[abort](abort.md)<br/>
