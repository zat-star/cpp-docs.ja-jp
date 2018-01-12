---
title: "mbrtoc16、mbrtoc323 | Microsoft Docs"
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
- mbrtoc16
- mbrtoc32
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
- mbrtoc16
- mbrtoc32
- uchar/mbrtoc16
- uchar/mbrtoc32
dev_langs: C++
helpviewer_keywords:
- mbrtoc16 function
- mbrtoc32 function
ms.assetid: 099ade4d-56f7-4e61-8b45-493f1d7a64bd
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c24a7426c788ac7ecfc98f3e649397912960505a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="mbrtoc16-mbrtoc32"></a>mbrtoc16、mbrtoc32
半角文字列の最初のマルチバイト文字を等価の UTF-16 や UTF-32 の文字に変換します。  
  
## <a name="syntax"></a>構文  
  
```  
size_t mbrtoc16(   
   char16_t* destination,   
   const char* source,   
   size_t max_bytes,   
   mbstate_t* state   
);  
  
size_t mbrtoc32(  
   char32_t* destination,   
   const char* source,   
   size_t max_bytes,   
   mbstate_t* state   
);  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `destination`  
 変換するマルチバイト文字と等価の `char16_t` または `char32_t` 文字へのポインター。 null の場合、関数は値を格納しません。  
  
 `source`  
 変換するマルチバイト文字列へのポインター。  
  
 `max_bytes`  
 変換する文字を検査する `source` 内の最大バイト数。 これは、1 から `source`内に残っているバイト数 (null 終端記号を含む) の間の値である必要があります。  
  
 `state`  
 マルチバイト文字列を 1 つ以上の出力文字に解釈するために使用される `mbstate_t` 変換状態オブジェクトへのポインター。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、次の条件のうち、現在の `state` 値の場合に当てはまる最初の値を返します。  
  
|[値]|条件|  
|-----------|---------------|  
|0|`max_bytes` から変換された次の `source` 文字以下の文字は null ワイド文字に相当し、これが格納される値です ( `destination` が null でない場合)。<br /><br /> `state` は初期のシフト状態です。|  
|1 以上、 `max_bytes`以下|返される値は、正しいマルチバイト文字を完成するのに必要な `source` のバイト数です。 `destination` が null でない場合、変換されたワイド文字が格納されます。|  
|-3|前回の関数呼び出しの結果として得られた次のワイド文字が `destination` に格納されています ( `destination` が null でない場合)。 今回の関数呼び出しでは `source` のバイトは使用されません。<br /><br /> 複数のワイド文字がないと表現できないマルチバイト文字 (サロゲート ペアなど) を  `source` が指す場合、次の関数呼び出しが追加の文字を書き出すように `state` 値が更新されます。|  
|-2|次の `max_bytes` バイトは、不完全ではあるものの、正しいものになり得るマルチバイト文字です。 `destination`に値は格納されません。 この結果は `max_bytes` がゼロの場合に発生することがあります。|  
|-1|エンコーディング エラーが発生しました。 次の `max_bytes` 以下のバイト数は、完全かつ有効なマルチバイト文字に寄与しません。 `destination`に値は格納されません。<br /><br /> `EILSEQ` が `errno` に格納され、変換状態 `state` は指定されません。|  
  
## <a name="remarks"></a>コメント  
 `mbrtoc16` 関数は `max_bytes` から最大で `source` バイトを読み取って、完全かつ正しい最初のマルチバイト文字を検索し、等価の UTF-16 文字を `destination`に格納します。 ソース バイトは、現在のスレッドのマルチバイト ロケールに従って解釈されます。 マルチバイト文字に複数の UTF-16 出力文字が必要な場合 (サロゲート ペアなど) は、次に `state` を呼び出したときに次の UTF-16 文字が `destination` に格納されるように、 `mbrtoc16`値が設定されます。 `mbrtoc32` 関数は同一ですが、出力は UTF-32 文字として格納されます。  
  
 `source` が null の場合、これらの関数は、 `NULL` が `destination`、 `""` が `source`、 `1` が `max_bytes`の各引数で呼び出した場合と同じものを返します。 `destination` と `max_bytes` に渡した値は無視されます。  
  
 `source` が null でない場合、関数は文字列の先頭から開始し、最大 `max_bytes` バイトを検査して、シフト シーケンスを含め、次のマルチバイト文字を完成させるのに必要なバイト数を判別します。 検査したバイトの中に正しくかつ完全なマルチバイト文字が含まれる場合、関数はその文字を等価の 16 ビットや 32 ビットのワイド文字 1 つまたは複数に変換します。 `destination` が null でない場合、関数は最初の (かつ場合によっては唯一の) 結果の文字を変換先に格納します。 追加の出力文字が必要な場合は、後続の関数呼び出しが追加の文字を出力し、値 -3 を返すよう、 `state`の値が設定されます。 出力文字がこれ以上必要ない場合、 `state` は初期のシフト状態に設定されます。  
  
## <a name="requirements"></a>必要条件  
  
|関数|C ヘッダー|C++ ヘッダー|  
|--------------|--------------|------------------|  
|`mbrtoc16`,                `mbrtoc32`|\<uchar.h>|\<cuchar>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [c16rtomb、c32rtomb](../../c-runtime-library/reference/c16rtomb-c32rtomb1.md)   
 [mbrtowc](../../c-runtime-library/reference/mbrtowc.md)   
 [mbsrtowcs](../../c-runtime-library/reference/mbsrtowcs.md)   
 [mbsrtowcs_s](../../c-runtime-library/reference/mbsrtowcs-s.md)