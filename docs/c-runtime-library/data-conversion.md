---
title: "データ変換 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.conversions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "変換 (データを)"
  - "データ変換ルーチン [C++]"
ms.assetid: b15b5268-7467-49f1-bf95-5299b598f94c
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# データ変換
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これらのルーチンは、ある形式から別の形式にデータを変換します。  通常、これらのルーチンは、ユーザーが作成した変換より速く変換を実行します。  `to` プレフィックスで始まるルーチンは、それぞれ、関数およびマクロとして実装されます。  実装の使い分けについては、「[関数とマクロの使い分け](../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)」を参照してください。  
  
### データ変換ルーチン  
  
|ルーチン|使用方法|同等の .NET Framework 関数|  
|----------|----------|---------------------------|  
|[abs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|整数の絶対値を求める|[\<caps:sentence id\="tgt11" sentenceid\="9594ba199e25e9de6b463c8efc9fbe95" class\="tgtSentence"\>System::Math::Abs\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)|  
|[atof、\_atof\_l、\_wtof、\_wtof\_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|文字列を `float` に変換する|[\<caps:sentence id\="tgt13" sentenceid\="363f8f2cb09f8ca850491a65df66522e" class\="tgtSentence"\>System::Convert::ToDouble\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)|  
|[atoi、\_atoi\_l、\_wtoi、\_wtoi\_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|文字列を `int` に変換する|[System::Convert::ToInt32](https://msdn.microsoft.com/en-us/library/system.convert.toint32.aspx), [System::Convert::ToUInt32](https://msdn.microsoft.com/en-us/library/system.convert.touint32.aspx)|  
|[\_atoi64、\_atoi64\_l、\_wtoi64、\_wtoi64\_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|文字列を `__int64` に変換する|[System::Convert::ToInt64](https://msdn.microsoft.com/en-us/library/system.convert.toint64.aspx), [System::Convert::ToUInt64](https://msdn.microsoft.com/en-us/library/system.convert.touint64.aspx)|  
|[atol、\_atol\_l、\_wtol、\_wtol\_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|文字列を `long` に変換する|[System::Convert::ToInt64](https://msdn.microsoft.com/en-us/library/system.convert.toint64.aspx), [System::Convert::ToUInt64](https://msdn.microsoft.com/en-us/library/system.convert.touint64.aspx)|  
|[\_ecvt](../c-runtime-library/reference/ecvt.md), [\_ecvt\_s](../Topic/_ecvt_s.md)|`double` を指定された長さの文字列に変換する|[\<caps:sentence id\="tgt22" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[\_fcvt](../Topic/_fcvt.md)、[\_fcvt\_s](../c-runtime-library/reference/fcvt-s.md)|`double` を小数点の以下が指定された桁数である文字列に変換する|[\<caps:sentence id\="tgt25" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[\_gcvt](../c-runtime-library/reference/gcvt.md)、[\_gcvt\_s](../c-runtime-library/reference/gcvt-s.md)|`double` 数を文字列に変換する。文字列をバッファーに格納する|[\<caps:sentence id\="tgt28" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[\_itoa、\_i64toa、\_ui64toa、\_itow、\_i64tow、\_ui64tow](../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md), [\_itoa\_s、\_i64toa\_s、\_ui64toa\_s、\_itow\_s、\_i64tow\_s、\_ui64tow\_s](../c-runtime-library/reference/itoa-s-i64toa-s-ui64toa-s-itow-s-i64tow-s-ui64tow-s.md)|`int`、または `__int64` を文字列に変換する|[\<caps:sentence id\="tgt31" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[labs](../misc/labs-llabs.md)|`long` 整数の絶対値を求める|[\<caps:sentence id\="tgt34" sentenceid\="9594ba199e25e9de6b463c8efc9fbe95" class\="tgtSentence"\>System::Math::Abs\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)|  
|[\_ltoa、\_ltow](../Topic/_ltoa,%20_ltow.md), [\_ltoa\_s、\_ltow\_s](../c-runtime-library/reference/ltoa-s-ltow-s.md)|`long` を文字列に変換する|[\<caps:sentence id\="tgt37" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[\_mbbtombc、\_mbbtombc\_l](../c-runtime-library/reference/mbbtombc-mbbtombc-l.md)|1 バイト マルチバイト文字を、対応する 2 バイト マルチバイト文字に変換する|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_mbcjistojms、\_mbcjistojms\_l、\_mbcjmstojis、\_mbcjmstojis\_l](../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)|日本工業標準 \(JIS: Japan Industry Standard\) 文字を Japan Microsoft \(JMS\) 文字に変換する|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_mbcjistojms、\_mbcjistojms\_l、\_mbcjmstojis、\_mbcjmstojis\_l](../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)|JMS 文字を JIS 文字に変換する|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_mbctohira、\_mbctohira\_l、\_mbctokata、\_mbctokata\_l](../Topic/_mbctohira,%20_mbctohira_l,%20_mbctokata,%20_mbctokata_l.md)|マルチバイト文字を 1 バイトのひらがなコードに変換する|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_mbctohira、\_mbctohira\_l、\_mbctokata、\_mbctokata\_l](../Topic/_mbctohira,%20_mbctohira_l,%20_mbctokata,%20_mbctokata_l.md)|マルチバイト文字を 1 バイト カタカナ コードに変換する|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_mbctombb、\_mbctombb\_l](../c-runtime-library/reference/mbctombb-mbctombb-l.md)|2 バイト マルチバイト文字を、対応する 1 バイト マルチバイト文字に変換する|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[mbstowcs、\_mbstowcs\_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md), [mbstowcs\_s、\_mbstowcs\_s\_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|マルチバイト文字のシーケンスを、対応するワイド文字のシーケンスに変換|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[mbtowc、\_mbtowc\_l](../Topic/mbtowc,%20_mbtowc_l.md)|マルチバイト文字を対応するワイド文字に変換|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[strtod、\_strtod\_l、wcstod、\_wcstod\_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|文字列を `double` に変換する|[\<caps:sentence id\="tgt72" sentenceid\="363f8f2cb09f8ca850491a65df66522e" class\="tgtSentence"\>System::Convert::ToDouble\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)|  
|[strtol、wcstol、\_strtol\_l、\_wcstol\_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)|文字列を `long` 整数に変換する|[\<caps:sentence id\="tgt74" sentenceid\="e227c715eb07e76d963577b7a799c2bb" class\="tgtSentence"\>System::Convert::ToInt32\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.toint32.aspx)|  
|[strtoul、\_strtoul\_l、wcstoul、\_wcstoul\_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)|文字列を `unsigned long` 整数に変換する|[\<caps:sentence id\="tgt76" sentenceid\="121858e0b5a36f51abe1c266ab6fba6a" class\="tgtSentence"\>System::Convert::ToUInt32\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.touint32.aspx)|  
|[strxfrm、wcsxfrm、\_strxfrm\_l、\_wcsxfrm\_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)|ロケール固有の情報に基づいて、文字列を照合形式に変換します。|[\<caps:sentence id\="tgt78" sentenceid\="f57d3343223d1337ec503c6d3e02bac0" class\="tgtSentence"\>System::IFormattable::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.iformattable.tostring.aspx)|  
|[toascii \_ \_toascii](../c-runtime-library/reference/toascii-toascii.md)|文字を ASCII コードに変換する||  
|[tolower、\_tolower、towlower、\_tolower\_l、\_towlower\_l](../Topic/tolower,%20_tolower,%20towlower,%20_tolower_l,%20_towlower_l.md), [\_mbctolower、\_mbctolower\_l、\_mbctoupper、\_mbctoupper\_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|文字を調べ、現在大文字の場合は小文字に変換する|[\<caps:sentence id\="tgt82" sentenceid\="531bb90548dfdc9e9adea31b19ef1cc1" class\="tgtSentence"\>System::Char::ToLower\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.char.tolower.aspx)|  
|[tolower、\_tolower、towlower、\_tolower\_l、\_towlower\_l](../Topic/tolower,%20_tolower,%20towlower,%20_tolower_l,%20_towlower_l.md)|文字を無条件に小文字に変換する|[\<caps:sentence id\="tgt84" sentenceid\="067c0d5e10b0facda111402483f5cd3a" class\="tgtSentence"\>System::String::ToLower\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.string.tolower.aspx)|  
|[toupper、\_toupper、towupper、\_toupper\_l、\_towupper\_l](../Topic/toupper,%20_toupper,%20towupper,%20_toupper_l,%20_towupper_l.md), [\_mbctolower、\_mbctolower\_l、\_mbctoupper、\_mbctoupper\_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|文字を調べ、現在小文字の場合は大文字に変換する|[\<caps:sentence id\="tgt87" sentenceid\="fb184167443ee6ce1ae71a9ab9b01edb" class\="tgtSentence"\>System::Char::ToUpper\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.char.toupper.aspx)|  
|[toupper、\_toupper、towupper、\_toupper\_l、\_towupper\_l](../Topic/toupper,%20_toupper,%20towupper,%20_toupper_l,%20_towupper_l.md)|文字を無条件に大文字に変換する|[\<caps:sentence id\="tgt89" sentenceid\="86a1b4a5abf74ef908414687bc4c78df" class\="tgtSentence"\>System::String::ToUpper\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.string.toupper.aspx)|  
|[\_ultoa、\_ultow](../c-runtime-library/reference/ultoa-ultow.md), [\_ultoa\_s、\_ultow\_s](../Topic/_ultoa_s,%20_ultow_s.md)|文字列に変換 `unsigned``long`|[\<caps:sentence id\="tgt92" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[wcstombs、\_wcstombs\_l](../Topic/wcstombs,%20_wcstombs_l.md), [wcstombs\_s、\_wcstombs\_s\_l](../Topic/wcstombs_s,%20_wcstombs_s_l.md)|ワイド文字のシーケンスを、対応するマルチバイト文字のシーケンスに変換する|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[wctomb、\_wctomb\_l](../c-runtime-library/reference/wctomb-wctomb-l.md), [wctomb\_s、\_wctomb\_s\_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|ワイド文字を対応するマルチバイト文字に変換する|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[atof、\_atof\_l、\_wtof、\_wtof\_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|ワイド文字列を `double` に変換する|[System::Convert::ToInt64](https://msdn.microsoft.com/en-us/library/system.convert.toint64.aspx), [System::Convert::ToUInt64](https://msdn.microsoft.com/en-us/library/system.convert.touint64.aspx), [System::Convert::ToSingle](https://msdn.microsoft.com/en-us/library/system.convert.tosingle.aspx), [System::Convert::ToDouble](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)|  
|[atoi、\_atoi\_l、\_wtoi、\_wtoi\_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|ワイド文字列を `int` に変換する|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_atoi64、\_atoi64\_l、\_wtoi64、\_wtoi64\_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|ワイド文字列を `__int64` に変換する|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[atol、\_atol\_l、\_wtol、\_wtol\_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|ワイド文字列を `long` に変換する|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
  
## 参照  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)