---
title: _set_error_mode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_error_mode
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
- set_error_mode
- _set_error_mode
dev_langs:
- C++
helpviewer_keywords:
- _set_error_mode function
- set_error_mode function
ms.assetid: f0807be5-73d1-4a32-a701-3c9bdd139c5c
caps.latest.revision: 21
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 205a6bed342ce1489664a5e9e37880612492b04d
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="seterrormode"></a>_set_error_mode
`__error_mode` を変更し、プログラム終了の可能性があるエラーの場合に C ランタイムがエラー メッセージを書き込む、既定以外の位置を決定します。  
  
> [!IMPORTANT]
>  この API は、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
int _set_error_mode(  
   int modeval   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `modeval`  
 エラー メッセージの書き込み先。  
  
## <a name="return-value"></a>戻り値  
 エラーが発生した場合、以前の設定または-1 を返します。  
  
## <a name="remarks"></a>コメント  
 `__error_mode` の値を設定することにより、エラー出力シンクを制御します。 たとえば、標準エラーを出力先に指定することも、`MessageBox` API を使用することもできます。  
  
 `modeval` パラメーターには、次のいずれかの値を設定できます。  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`_OUT_TO_DEFAULT`|エラー シンクは `__app_type` によって決まります。|  
|`_OUT_TO_STDERR`|エラー シンクは、標準エラーです。|  
|`_OUT_TO_MSGBOX`|エラー シンクは、メッセージ ボックスです。|  
|`_REPORT_ERRMODE`|現在の `__error_mode` 値をレポートします。|  
  
 リストされている以外の値が渡された場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、`_set_error_mode` は `errno` を `EINVAL` に設定し、-1 を返します。  
  
 [アサート](../../c-runtime-library/reference/assert-macro-assert-wassert.md)と併用する場合、`_set_error_mode` はダイアログ ボックスに障害ステートメントを表示し、`Ignore` ボタンでプログラムの実行を継続することを選択できるようにします。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_set_error_mode`|\<stdlib.h>|  
  
## <a name="example"></a>例  
  
```C  
// crt_set_error_mode.c  
// compile with: /c  
#include <stdlib.h>  
#include <assert.h>  
  
int main()  
{  
   _set_error_mode(_OUT_TO_STDERR);  
   assert(2+2==5);  
}  
```  
  
```Output  
Assertion failed: 2+2==5, file crt_set_error_mode.c, line 8  
  
This application has requested the Runtime to terminate it in an unusual way.  
Please contact the application's support team for more information.  
```  
  
## <a name="see-also"></a>関連項目  
 [assert マクロ、_assert、_wassert](../../c-runtime-library/reference/assert-macro-assert-wassert.md)
