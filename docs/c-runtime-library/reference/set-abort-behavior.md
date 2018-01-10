---
title: _set_abort_behavior | Microsoft Docs
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_abort_behavior
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
dev_langs: C++
helpviewer_keywords:
- aborting programs
- _set_abort_behavior function
- set_abort_behavior function
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 965ff160fd8098c60f53f639cb95aedf890edd86
ms.sourcegitcommit: a5d8f5b92cb5e984d5d6c9d67fe8a1241f3fe184
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2018
---
# <a name="setabortbehavior"></a>_set_abort_behavior

プログラムが異常終了した場合に実行するアクションを指定します。

> [!NOTE]
> 使用しないで、`abort`テスト シナリオまたはデバッグ シナリオを除く、Microsoft ストアのアプリをシャット ダウンする関数。 ストア アプリを閉じる方法はプログラムや UI はに従って許可されていません、 [Microsoft ストアのポリシー](http://go.microsoft.com/fwlink/?LinkId=865936)です。 詳細については、次を参照してください。 [UWP アプリのライフ サイクル](http://go.microsoft.com/fwlink/p/?LinkId=865934)です。

## <a name="syntax"></a>構文

```C
unsigned int _set_abort_behavior(
   unsigned int flags,
   unsigned int mask
);
```

### <a name="parameters"></a>パラメーター

[in]_フラグ_  
`abort` フラグの新しい値。

[in]_マスク_  
設定する `abort` フラグのビットのマスク。

## <a name="return-value"></a>戻り値

フラグの元の値。

## <a name="remarks"></a>コメント

`abort` フラグには、`_WRITE_ABORT_MSG` と `_CALL_REPORTFAULT` の 2 つの種類があります。 `_WRITE_ABORT_MSG` は、プログラムが異常終了したときに説明のテキスト メッセージを出力するかどうかを指定します。 メッセージは、アプリケーションが `abort` の関数を呼び出したことを示します。 既定の動作はメッセージを表示することです。 `_CALL_REPORTFAULT` が設定されていると、`abort` が呼び出されたときにワトソン クラッシュ ダンプが生成され、報告されます。 既定では、クラッシュ ダンプのレポートは、非デバッグ ビルドで有効になっています。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|`_set_abort_behavior`|\<stdlib.h>|

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

[abort](../../c-runtime-library/reference/abort.md)  
