---
title: _lock_file | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _lock_file
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
- _lock_file
- lock_file
dev_langs:
- C++
helpviewer_keywords:
- file locking [C++]
- _lock_file function
- lock_file function
ms.assetid: 75c7e0e6-efff-4747-b6ed-9bcf2b0894c3
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6c70d3b006cb3748b735be0b8989578876c10e50
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="lockfile"></a>_lock_file

ロック、**ファイル**オブジェクトにアクセスするスレッドの一貫性を確保する、**ファイル**オブジェクトを同時にします。

## <a name="syntax"></a>構文

```C
void _lock_file( FILE* file );
```

### <a name="parameters"></a>パラメーター

*ファイル*ファイル ハンドル。

## <a name="remarks"></a>コメント

**_Lock_file**関数のロック、**ファイル**で指定されたオブジェクト*ファイル*です。 によって、基になるファイルがロックされていない **_lock_file**です。 ファイルのロックを解除するには、[_unlock_file](unlock-file.md) を使用します。 呼び出す **_lock_file**と **_unlock_file**のスレッドに一致する必要があります。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_lock_file**|\<stdio.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_lock_file.c
// This example creates multiple threads that write to standard output
// concurrently, first with _file_lock, then without.

#include <stdio.h>
#include <process.h>// _beginthread
#include <windows.h>// HANDLE

void Task_locked( void* str )
{
    for( int i=0; i<1000; ++i )
    {
        _lock_file( stdout );
        for( char* cp = (char*)str; *cp; ++cp )
        {
            _fputc_nolock( *cp, stdout );
        }
        _unlock_file( stdout );
    }
}

void Task_unlocked( void* str )
{
    for( int i=0; i<1000; ++i )
    {
        for( char* cp = (char*)str; *cp; ++cp )
        {
            fputc( *cp, stdout );
        }
    }
}

int main()
{
    HANDLE h[3];
    h[0] = (HANDLE)_beginthread( &Task_locked, 0, "First\n" );
    h[1] = (HANDLE)_beginthread( &Task_locked, 0, "Second\n" );
    h[2] = (HANDLE)_beginthread( &Task_locked, 0, "Third\n" );

    WaitForMultipleObjects( 3, h, true, INFINITE );

    h[0] = (HANDLE)_beginthread( &Task_unlocked, 0, "First\n" );
    h[1] = (HANDLE)_beginthread( &Task_unlocked, 0, "Second\n" );
    h[2] = (HANDLE)_beginthread( &Task_unlocked, 0, "Third\n" );

    WaitForMultipleObjects( 3, h, true, INFINITE );
}
```

```Output
...
First
Second
First
Second
Third
Second
Third
Second
...
FSiercsotn
dF
iSrescto
nFdi
rSsetc
oFnidr
sSte
cFoinrds
tS
eFciornsdt
```

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[_creat、_wcreat](creat-wcreat.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_unlock_file](unlock-file.md)<br/>
