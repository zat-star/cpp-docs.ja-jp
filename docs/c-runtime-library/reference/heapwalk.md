---
title: _heapwalk | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _heapwalk
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- heapwalk
- _heapwalk
dev_langs:
- C++
helpviewer_keywords:
- debugging [CRT], heap-related problems
- heapwalk function
- _heapwalk function
ms.assetid: 2df67649-fb00-4570-a8b1-a4eca5738744
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 82b2a69fba87d86b01c4f4e3b8ad140e2bcde3ef
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="heapwalk"></a>_heapwalk
ヒープを走査し、次のエントリに関する情報を返します。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。ただし、デバッグ ビルドの場合は除きます。 詳細については、次を参照してください。[ユニバーサル Windows プラットフォーム アプリでサポートされない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
int _heapwalk(   
   _HEAPINFO *entryinfo   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `entryinfo`  
 ヒープ情報を格納するバッファー。  
  
## <a name="return-value"></a>戻り値  
 `_heapwalk` は、Malloc.h に定義されている次の整数のマニフェスト定数のいずれかを返します。  
  
 `_HEAPBADBEGIN`  
 初期ヘッダー情報が無効または見つかりません。  
  
 `_HEAPBADNODE`  
 ヒープが破損しているか、不適切なノードが見つかりました。  
  
 `_HEAPBADPTR`  
 `_pentry` 構造体の `_HEAPINFO` フィールドに、ヒープへの有効なポインターが格納されていないか、または `entryinfo` が null ポインターです。  
  
 `_HEAPEND`  
 ヒープの終わりに正常に到達しました。  
  
 `_HEAPEMPTY`  
 ヒープが初期化されていません。  
  
 `_HEAPOK`  
 これまでのところエラーはありません。`entryinfo` は、次のヒープ エントリに関する情報で更新されます。  
  
 また、エラーが発生した場合、`_heapwalk` は `errno` を `ENOSYS` に設定します。  
  
## <a name="remarks"></a>コメント  
 `_heapwalk` 関数は、プログラムのヒープ関連の問題をデバッグするのに役立ちます。 この関数はヒープを走査します。呼び出しごとに 1 つのエントリを走査し、次のヒープ エントリに関する情報を含んだ `_HEAPINFO` 型の構造体へのポインターを返します。 `_HEAPINFO` 型は Malloc.h で定義されており、次の要素を含んでいます。  
  
 `int *_pentry`  
 ヒープ エントリのポインター。  
  
 `size_t _size`  
 ヒープ エントリのサイズ。  
  
 `int _useflag`  
 ヒープ エントリが使用中かどうかを示すフラグ。  
  
 `_heapwalk` を返す `_HEAPOK` を呼び出すと、エントリのサイズが `_size` フィールドに格納され、`_useflag` フィールドが `_FREEENTRY` または `_USEDENTRY` (両方とも Malloc.h に定義されている定数です) に設定されます。 ヒープの最初のエントリに関する情報を取得するには、`_heapwalk` メンバーが `_HEAPINFO` である `_pentry` 構造体へのポインターを `NULL` に渡します。 オペレーティング システムで `_heapwalk` がサポートされていない場合 (Windows 98 など)、この関数は `_HEAPEND` を返し、`errno` を `ENOSYS` に設定します。  
  
 この関数は、そのパラメーターを検証します。 `entryinfo` が null ポインターである場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、`errno` が `EINVAL` に設定され、関数から `_HEAPBADPTR` が返されます。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|  
|-------------|---------------------|---------------------|  
|`_heapwalk`|\<malloc.h>|\<errno.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_heapwalk.c  
  
// This program "walks" the heap, starting  
// at the beginning (_pentry = NULL). It prints out each  
// heap entry's use, location, and size. It also prints  
// out information about the overall state of the heap as  
// soon as _heapwalk returns a value other than _HEAPOK  
// or if the loop has iterated 100 times.  
  
#include <stdio.h>  
#include <malloc.h>  
  
void heapdump(void);  
  
int main(void)  
{  
    char *buffer;  
  
    heapdump();  
    if((buffer = (char *)malloc(59)) != NULL)  
    {  
        heapdump();  
        free(buffer);  
    }  
    heapdump();  
}  
  
void heapdump(void)  
{  
    _HEAPINFO hinfo;  
    int heapstatus;  
    int numLoops;  
    hinfo._pentry = NULL;  
    numLoops = 0;  
    while((heapstatus = _heapwalk(&hinfo)) == _HEAPOK &&  
          numLoops < 100)  
    {  
        printf("%6s block at %Fp of size %4.4X\n",  
               (hinfo._useflag == _USEDENTRY ? "USED" : "FREE"),  
               hinfo._pentry, hinfo._size);  
        numLoops++;  
    }  
  
    switch(heapstatus)  
    {  
    case _HEAPEMPTY:  
        printf("OK - empty heap\n");  
        break;  
    case _HEAPEND:  
        printf("OK - end of heap\n");  
        break;  
    case _HEAPBADPTR:  
        printf("ERROR - bad pointer to heap\n");  
        break;  
    case _HEAPBADBEGIN:  
        printf("ERROR - bad start of heap\n");  
        break;  
    case _HEAPBADNODE:  
        printf("ERROR - bad node in heap\n");  
        break;  
    }  
}  
```  
  
```Output  
  USED block at 00310650 of size 0100  
  USED block at 00310758 of size 0800  
  USED block at 00310F60 of size 0080  
  FREE block at 00310FF0 of size 0398  
  USED block at 00311390 of size 000D  
  USED block at 003113A8 of size 00B4  
  USED block at 00311468 of size 0034  
  USED block at 003114A8 of size 0039  
...  
  USED block at 00312228 of size 0010  
  USED block at 00312240 of size 1000  
  FREE block at 00313250 of size 1DB0  
OK - end of heap  
```  
  
## <a name="see-also"></a>参照  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)   
 [_heapadd](../../c-runtime-library/heapadd.md)   
 [_heapchk](../../c-runtime-library/reference/heapchk.md)   
 [_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [_heapset](../../c-runtime-library/heapset.md)