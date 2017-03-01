---
title: _set_controlfp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_controlfp
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
dev_langs:
- C++
helpviewer_keywords:
- set_controlfp function
- floating-point functions, setting control word
- _set_controlfp function
ms.assetid: e0689d50-f68a-4028-a9c1-fb23eedee4ad
caps.latest.revision: 11
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
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: f7cf06b52624178a3d5bbe5907289eab7f57cbb5
ms.lasthandoff: 02/24/2017

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
  
 コンパイルすると、この関数は使用されなくなりました[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)共通言語ランタイムでは、浮動小数点の既定の精度のみがサポートされるためです。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|互換性|  
|-------------|---------------------|-------------------|  
|`_set_controlfp`|\<float.h>|x86 プロセッサのみ|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [_clear87、_clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [_status87、_statusfp、_statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)
