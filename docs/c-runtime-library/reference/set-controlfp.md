---
title: _set_controlfp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_controlfp
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
- set_controlfp
- _set_controlfp
dev_langs: C++
helpviewer_keywords:
- set_controlfp function
- floating-point functions, setting control word
- _set_controlfp function
ms.assetid: e0689d50-f68a-4028-a9c1-fb23eedee4ad
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 132680e529c8f38b5eb69e778b6e635bd424b412
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="setcontrolfp"></a>_set_controlfp
浮動小数点制御ワードを設定します。  
  
## <a name="syntax"></a>構文  
  
```  
void __cdecl _set_controlfp(  
    unsigned int newControl,  
    unsigned int mask  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `newControl`  
 新しい制御ワードのビット値。  
  
 `mask`  
 新しく設定する制御ワード ビットのマスク。  
  
## <a name="return-value"></a>戻り値  
 なし。  
  
## <a name="remarks"></a>コメント  
 `_set_controlfp` は `_control87` と似ていますが、浮動小数点制御ワードの `newControl` への設定だけを行います。 この値のビットは、浮動小数点のコントロールの状態を示します。 浮動小数点のコントロールの状態を使用すると、プログラムで使用する浮動小数点演算パッケージの精度、丸め、無限大の各モードを変更できます。 `_set_controlfp` を使用して、浮動小数点例外のマスクの設定および解除を行うこともできます。 詳細については、「[_control87、_controlfp、\__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)」を参照してください。  
  
 コンパイルするときにこの関数は使用されなくなりました[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)共通言語ランタイムには、既定の浮動小数点精度のみがサポートされるためです。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|互換性|  
|-------------|---------------------|-------------------|  
|`_set_controlfp`|\<float.h>|x86 プロセッサのみ|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [_clear87、_clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [_status87、_statusfp、_statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)