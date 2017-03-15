---
title: "c16rtomb、c32rtomb1 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- c16rtomb
- c32rtomb
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- c16rtomb
- c32rtomb
- uchar/c16rtomb
- uchar/c32rtomb
dev_langs:
- C++
helpviewer_keywords:
- c16rtomb function
- c32rtomb function
ms.assetid: 7f5743ca-a90e-4e3f-a310-c73e16f4e14d
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 585fd26bf3ea6a2d392a61b4f7793a0a9e84e267
ms.lasthandoff: 02/24/2017

---
# <a name="c16rtomb-c32rtomb"></a>c16rtomb、c32rtomb
UTF-16 または UTF-32 ワイド文字を現在のロケールのマルチバイト文字に変換します。  
  
## <a name="syntax"></a>構文  
  
```  
size_t c16rtomb(  
    char *mbchar,   
    char16_t wchar,  
    mbstate_t *state  
);  
size_t c32rtomb(  
    char *mbchar,   
    char32_t wchar,  
    mbstate_t *state  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `mbchar`  
 変換されたマルチバイト文字を格納する配列へのポインター。  
  
 [入力] `wchar`  
 変換するワイド文字。  
  
 [入力、出力] `state`  
 `mbstate_t` オブジェクトへのポインター。  
  
## <a name="return-value"></a>戻り値  
 配列オブジェクト `mbchar`に格納されるバイト数 (シフト シーケンスを含む)。 `wchar` が有効なワイド文字でない場合、値 (`size_t`)(-1) が返され、 `errno` は `EILSEQ`に設定され、 `state` の値は指定されません。  
  
## <a name="remarks"></a>コメント  
 `c16rtomb` 関数は、UTF-16 文字 `wchar` を現在のロケールの同等のマルチバイトのナロウ文字シーケンスに変換します。 `mbchar` が null ポインターでない場合、関数は、 `mbchar`が指す配列オブジェクトの変換されたシーケンスを格納します。 最大 `MB_CUR_MAX` バイトが `mbchar`に格納され、 `state` は、結果として生成されるシフト状態に設定されます。    `wchar` が null ワイド文字である場合、初期シフト状態の復元に必要なシーケンスが格納され、必要であれば null 文字が後に続き、 `state` が初期変換状態に設定されます。 `c32rtomb` 関数は同一ですが、UTF-32 文字を変換します。  
  
 `mbchar` が null ポインターの場合、動作は、 `mbchar` の内部バッファーおよび `wchar`のワイド null 文字を置換する関数の呼び出しと同等です。  
  
 `state` 変換状態オブジェクトにより、この関数とマルチバイト出力のシフト状態を維持するその他の再開可能な関数を続けて呼び出すことが可能になります。 再開可能関数と再開不可能関数を一緒に使用する場合、または、再開可能関数間で `setlocale` が呼び出される場合、結果は未定義です。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`c16rtomb`, `c32rtomb`|C、C++: \<uchar.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbrtoc16、mbrtoc32](../../c-runtime-library/reference/mbrtoc16-mbrtoc323.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb_s](../../c-runtime-library/reference/wcrtomb-s.md)
