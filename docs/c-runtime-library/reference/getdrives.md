---
title: _getdrives | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _getdrives
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
- getdrives
- _getdrives
dev_langs:
- C++
helpviewer_keywords:
- _getdrives function
- getdrives function
- disk drives
ms.assetid: 869bb51f-4209-4328-846e-3aadebaceb9c
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 1a00023e4d3e31ddb6381e90a50231449b1de18d
ms.openlocfilehash: 314c8633ce43a154533873efadc7f3a0006a1aff
ms.contentlocale: ja-jp
ms.lasthandoff: 02/28/2017

---
# <a name="getdrives"></a>_getdrives
現在使用できるディスク ドライブを表すビットマスクを返します。  
  
> [!IMPORTANT]
>  この API は、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned long _getdrives( void );  
```  
  
## <a name="return-value"></a>戻り値  
 関数が成功した場合、戻り値は、現在使用できるディスク ドライブを表すビットマスクです。 ビット位置 0 (最下位ビット) はドライブ A、ビット位置 1 はドライブ B、ビット位置 2 は C ドライブです (以下同様)。 関数が失敗した場合は、0 を返します。 拡張されたエラー情報を取得するには、`GetLastError` を呼び出します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_getdrives`|\<direct.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```C  
// crt_getdrives.c  
// This program retrives and lists out  
// all the logical drives that are   
// currently mounted on the machine.  
  
#include <windows.h>  
#include <direct.h>  
#include <stdio.h>  
#include <tchar.h>  
  
TCHAR g_szDrvMsg[] = _T("A:\n");  
  
int main(int argc, char* argv[]) {  
   ULONG uDriveMask = _getdrives();  
  
   if (uDriveMask == 0)  
   {  
      printf( "_getdrives() failed with failure code: %d\n",  
              GetLastError());  
   }  
   else  
   {  
      printf("The following logical drives are being used:\n");  
  
      while (uDriveMask) {  
         if (uDriveMask & 1)  
            printf(g_szDrvMsg);  
  
         ++g_szDrvMsg[0];  
         uDriveMask >>= 1;  
      }  
   }  
}  
```  
  
```Output  
The following logical drives are being used:  
A:  
C:  
D:  
E:  
```  
  
## <a name="see-also"></a>関連項目  
 [ディレクトリ制御](../../c-runtime-library/directory-control.md)
