---
title: "浮動小数点サポート | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.math"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "浮動小数点数"
  - "浮動小数点数, 数値演算ルーチン"
  - "数値演算ルーチン"
ms.assetid: e4fcaf69-5c8e-4854-a9bb-1f412042131e
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# 浮動小数点サポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

多くの Microsoft ランタイム ライブラリ関数には、数値演算コプロセッサやコンパイラに付随する浮動小数点ライブラリの浮動小数点のサポートが必要となります。  浮動小数点サポート機能は、必要な場合にのみ読み込まれます。  
  
 `printf` または `scanf` ファミリの関数の呼び出しの書式指定文字列で浮動小数点型の指定子を使用する場合、浮動小数点サポートが必要であることをコンパイラに示すために、浮動小数点値または引数リスト内の浮動小数点値へのポインターを指定する必要があります。  
  
 浮動小数点例外の処理方法を示すサンプル コードについては、「[\_fpieee\_flt](../c-runtime-library/reference/fpieee-flt.md)」を参照してください。  
  
 中間値の浮動小数点の精度は、関数 [\_control87、\_controlfp、\_\_control87\_2](../Topic/_control87,%20_controlfp,%20__control87_2.md) によって制御されます。  既定では、`_controlfp` での精度制御は 53 ビット \(\_PC\_53\) に設定されています。  FP10.OBJ を使用してリンクすると、既定の精度制御は 64 ビット \(\_PC\_64\) に変更されます。  リンカーのコマンド ラインで、FP10.OBJ は LIBC.LIB、LIBCMT.LIB、または MSVCRT.LIB の前にある必要があります。  
  
### 浮動小数点関数  
  
|ルーチン|用途|同等の .NET Framework 関数|  
|----------|--------|---------------------------|  
|[abs](../Topic/abs.md)|`int` の絶対値を返す|[\<caps:sentence id\="tgt14" sentenceid\="9594ba199e25e9de6b463c8efc9fbe95" class\="tgtSentence"\>System::Math::Abs\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)|  
|[acos、acosf](../c-runtime-library/reference/acos-acosf-acosl.md)|アークコサインを計算する|[\<caps:sentence id\="tgt17" sentenceid\="954a441495360a1fa8b0170297b2ff38" class\="tgtSentence"\>System::Math::Acos\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.acos.aspx)|  
|[asin、asinf](../c-runtime-library/reference/asin-asinf-asinl.md)|アークサインを計算する|[\<caps:sentence id\="tgt20" sentenceid\="313917cde9698a0924536719f5bece25" class\="tgtSentence"\>System::Math::Asin\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.asin.aspx)|  
|[atan、atanf、atan2、atan2f](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|アークタンジェントを計算する|[System::Math::Atan](https://msdn.microsoft.com/en-us/library/system.math.atan.aspx)、[System::Math::Atan2](https://msdn.microsoft.com/en-us/library/system.math.atan2.aspx)|  
|[atof、\_atof\_l、\_wtof、\_wtof\_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|文字列を倍精度浮動小数点値に変換する|[System::Convert::ToSingle](https://msdn.microsoft.com/en-us/library/system.convert.tosingle.aspx)、[System::Convert::ToDouble](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)|  
|[ベッセル関数](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|ベッセル関数 `_j0`、`_j1`、`_jn`、`_y0`、`_y1`、`_yn` を計算する|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_cabs](../Topic/_cabs.md)|複素数の絶対値を求める|該当なし。|  
|[cbrt](../c-runtime-library/reference/cbrt-cbrtf-cbrtl.md)|立方根を計算する|該当なし。|  
|[ceil、ceilf](../c-runtime-library/reference/ceil-ceilf-ceill.md)|整数の切り上げを求める|[\<caps:sentence id\="tgt39" sentenceid\="656009d71fb974368bded363746de018" class\="tgtSentence"\>System::Math::Ceiling\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.ceiling.aspx)|  
|[\_chgsign、\_chgsignf、\_chgsignl](../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)|倍精度浮動小数点または long double 精度浮動小数点引数の符号を反転する|該当なし。|  
|[\_clear87、\_clearfp](../c-runtime-library/reference/clear87-clearfp.md)|浮動小数点ステータス ワードを取得してクリアする|該当なし。|  
|[\_control87、\_controlfp、\_\_control87\_2](../Topic/_control87,%20_controlfp,%20__control87_2.md), [\_controlfp\_s](../c-runtime-library/reference/controlfp-s.md)|古い浮動小数点制御ワードを取得して新しい制御ワード値を設定する|該当なし。|  
|[copysign、copysignf、copysignl、\_copysign、\_copysignf、\_copysignl](../c-runtime-library/reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)|別の符号を持つ値を 1 つ返す|該当なし。|  
|[cos、cosf、cosh、coshf](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|コサインを計算する|[System::Math::Cos](https://msdn.microsoft.com/en-us/library/system.math.cos.aspx)、[System::Math::Cosh](https://msdn.microsoft.com/en-us/library/system.math.cosh.aspx)|  
|[difftime](../c-runtime-library/reference/difftime-difftime32-difftime64.md)|指定された 2 つの時間値の差を計算する|[\<caps:sentence id\="tgt54" sentenceid\="5f4f365a3cd7f368db2f6ce31b797fdf" class\="tgtSentence"\>System::DateTime::Subtract\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.datetime.subtract.aspx)|  
|[div](../c-runtime-library/reference/div.md)|1 つの整数を別の整数で除算し、商と剰余を返す|該当なし。|  
|[\_ecvt](../c-runtime-library/reference/ecvt.md), [\_ecvt\_s](../Topic/_ecvt_s.md)|`double` を指定された長さの文字列に変換する|[\<caps:sentence id\="tgt60" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[exp、expf](../c-runtime-library/reference/exp-expf.md)|指数関数を計算する|[\<caps:sentence id\="tgt63" sentenceid\="81a65df6ac66cdc4a4b12c2f7e555487" class\="tgtSentence"\>System::Math::Exp\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.exp.aspx)|  
|[fabs、fabsf](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|絶対値を求める|[\<caps:sentence id\="tgt66" sentenceid\="9594ba199e25e9de6b463c8efc9fbe95" class\="tgtSentence"\>System::Math::Abs\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)|  
|[\_fcvt](../Topic/_fcvt.md)、[\_fcvt\_s](../c-runtime-library/reference/fcvt-s.md)|`double` を小数点以下が指定された桁数である文字列に変換する|[\<caps:sentence id\="tgt69" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[\_finite](../c-runtime-library/reference/finite-finitef.md)|指定された倍精度浮動小数点値が有限かどうかを判別する|[\<caps:sentence id\="tgt72" sentenceid\="8d081c50adeda3dde4cebab81a0b3583" class\="tgtSentence"\>System::Double::IsInfinity\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.double.isinfinity.aspx)|  
|[floor、floorf](../c-runtime-library/reference/floor-floorf-floorl.md)|引数以下の最大の整数を求める|[\<caps:sentence id\="tgt75" sentenceid\="609db9ab0433b647d5350d3b965d70f9" class\="tgtSentence"\>System::Math::Floor\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.floor.aspx)|  
|[fmod、fmodf](../Topic/fmod,%20fmodf.md)|浮動小数点の剰余を求める|[\<caps:sentence id\="tgt78" sentenceid\="127a04426267ccb17fb4b566ad56de9c" class\="tgtSentence"\>System::Math::IEEERemainder\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.ieeeremainder.aspx)|  
|[\_fpclass](../c-runtime-library/reference/fpclass-fpclassf.md)|浮動小数点クラスに関する情報を含むステータス ワードを返す|[System::Double::IsInfinity](https://msdn.microsoft.com/en-us/library/system.double.isinfinity.aspx)、[System::Double::IsNegativeInfinity](https://msdn.microsoft.com/en-us/library/system.double.isnegativeinfinity.aspx)、[System::Double::IsPositiveInfinity](https://msdn.microsoft.com/en-us/library/system.double.ispositiveinfinity.aspx)、[System::Double::IsNan](https://msdn.microsoft.com/en-us/library/system.double.isnan.aspx)|  
|[\_fpieee\_flt](../c-runtime-library/reference/fpieee-flt.md)|IEEE 浮動小数点例外用のユーザー定義トラップ ハンドラーを呼び出す|該当なし。|  
|[\_fpreset](../c-runtime-library/reference/fpreset.md)|浮動小数点演算パッケージを再初期化する||  
|[frexp](../c-runtime-library/reference/frexp.md)|指数値を計算する|該当なし。|  
|[\_gcvt](../c-runtime-library/reference/gcvt.md)、[\_gcvt\_s](../c-runtime-library/reference/gcvt-s.md)|浮動小数点値を文字列に変換する|[\<caps:sentence id\="tgt92" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[hypot、hypotf、hypotl、\_hypot、\_hypotf、\_hypotl](../c-runtime-library/reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md)|直角三角形の斜辺を計算する|該当なし。|  
|[\_isnan](../c-runtime-library/reference/isnan-isnan-isnanf.md)|指定された倍精度浮動小数点値が非数 \(NaN\) であることをチェックする|[\<caps:sentence id\="tgt97" sentenceid\="18f7dc07d0c506c23f2f7eb89262d274" class\="tgtSentence"\>System::Double::IsNan\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.double.isnan.aspx)|  
|[labs](../misc/labs-llabs.md)|`long` の絶対値を返す|[\<caps:sentence id\="tgt100" sentenceid\="9594ba199e25e9de6b463c8efc9fbe95" class\="tgtSentence"\>System::Math::Abs\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)|  
|[ldexp](../c-runtime-library/reference/ldexp.md)|引数と 2<sup>exp</sup> \(指定された累乗\) の積を計算する|[\<caps:sentence id\="tgt103" sentenceid\="839e85fe5fb98e8520d40a703d06932b" class\="tgtSentence"\>System::Math::Pow\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.pow.aspx)|  
|[ldiv](../Topic/ldiv,%20lldiv.md)|1 つの `long` 整数を別の long 整数で除算し、商と剰余を返す|該当なし。|  
|[log、logf、log10、log10f](../Topic/log,%20logf,%20log10,%20log10f.md)|自然対数または 10 を底とする対数を計算する|[System::Math::Log](https://msdn.microsoft.com/en-us/library/system.math.log.aspx)、[System::Math::Log10](https://msdn.microsoft.com/en-us/library/system.math.log10.aspx)|  
|[\_logb](../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)|倍精度浮動小数点引数の指数値を抽出する|該当なし。|  
|[\_lrotl、\_lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|`unsigned long int` を左 \(`_lrotl`\) または右 \(`_lrotr`\) にシフトする|該当なし。|  
|[\_matherr](../c-runtime-library/reference/matherr.md)|数値演算エラーを処理する|該当なし。|  
|[\_\_max](../c-runtime-library/reference/max.md)|2 つの値のうち大きい方を返す|[\<caps:sentence id\="tgt121" sentenceid\="6f9dcb228534c3e5b0013615b2b1d003" class\="tgtSentence"\>System::Math::Max\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.max.aspx)|  
|[\_\_min](../c-runtime-library/reference/min.md)|2 つの値のうち小さい方を返す|[\<caps:sentence id\="tgt124" sentenceid\="ff471983fc666dec7ba58b17a0bf76e6" class\="tgtSentence"\>System::Math::Min\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.min.aspx)|  
|[modf、modff](../c-runtime-library/reference/modf-modff-modfl.md)|引数を整数部と小数部に分割する|該当なし。|  
|[nan、nanf、nanl](../c-runtime-library/reference/nan-nanf-nanl.md)|簡易な NaN 値を返す|[\<caps:sentence id\="tgt129" sentenceid\="c251043405ffa73fe857c83428b58fdc" class\="tgtSentence"\>System::Double::NaN\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.double.nan.aspx)|  
|[\_nextafter](../c-runtime-library/reference/nextafter-functions.md)|次の表現可能なネイバーを返す|該当なし。|  
|[pow、powf](../Topic/pow,%20powf,%20powl.md)|累乗された値を計算する|[\<caps:sentence id\="tgt135" sentenceid\="839e85fe5fb98e8520d40a703d06932b" class\="tgtSentence"\>System::Math::Pow\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.pow.aspx)|  
|[printf、\_printf\_l、wprintf、\_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md), [printf\_s、\_printf\_s\_l、wprintf\_s、\_wprintf\_s\_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|指定された書式に従ってデータを `stdout` に書き込む|[System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)、[System::Console::WriteLine](https://msdn.microsoft.com/en-us/library/system.console.writeline.aspx)|  
|[rand](../Topic/rand.md)、[rand\_s](../c-runtime-library/reference/rand-s.md)|疑似乱数を取得する|[\<caps:sentence id\="tgt141" sentenceid\="00574fde17be9de3e07567ef5abe0110" class\="tgtSentence"\>System::Random Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.random.aspx)|  
|[rint、rintf、rintl](../c-runtime-library/reference/rint-rintf-rintl.md)|浮動小数点形式で最も近い整数に丸める|[\<caps:sentence id\="tgt143" sentenceid\="1c04aeb4aeff1752cb65adabcee29f53" class\="tgtSentence"\>System::Math::Round\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.round.aspx)|  
|[\_rotl、\_rotr](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|`unsigned int` を左 \(`_rotl`\) または右 \(`_rotr`\) にシフトする|該当なし。|  
|[\_scalb](../c-runtime-library/reference/scalb.md)|引数を 2 の累乗で増減する|該当なし。|  
|[scalbn、scalbnf、scalbnl、scalbln、scalblnf、scalblnl](../c-runtime-library/reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md)|`FLT_RADIX` の累乗を乗算する|該当なし。|  
|[scanf、wscanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)、[scanf\_s、\_scanf\_s\_l、wscanf\_s、\_wscanf\_s\_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)|指定された書式に従ってデータを `stdin` から読み取り、指定された場所にデータを書き込む|[System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)、[System::Console::ReadLine](https://msdn.microsoft.com/en-us/library/system.console.readline.aspx)|  
|[\_set\_controlfp](../c-runtime-library/reference/set-controlfp.md)|新しい制御ワード値を設定する|該当なし。|  
|[sin、sinf、sinh、sinhf](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|サインまたはハイパーボリック サインを計算する|[System::Math::Sin](https://msdn.microsoft.com/en-us/library/system.math.sin.aspx)、[System::Math::Sinh](https://msdn.microsoft.com/en-us/library/system.math.sinh.aspx)|  
|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|平方根を求める|[\<caps:sentence id\="tgt162" sentenceid\="1a91af0bd8c63b4be64c7a0bec8dc8c4" class\="tgtSentence"\>System::Math::Sqrt\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.sqrt.aspx)|  
|[srand](../c-runtime-library/reference/srand.md)|疑似乱数列を初期化する|[\<caps:sentence id\="tgt165" sentenceid\="00574fde17be9de3e07567ef5abe0110" class\="tgtSentence"\>System::Random Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.random.aspx)|  
|[\_status87、\_statusfp、\_statusfp2](../c-runtime-library/reference/status87-statusfp-statusfp2.md)|浮動小数点ステータス ワードを取得する|該当なし。|  
|[strtod、\_strtod\_l、wcstod、\_wcstod\_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|文字列を倍精度値に変換する|[\<caps:sentence id\="tgt169" sentenceid\="363f8f2cb09f8ca850491a65df66522e" class\="tgtSentence"\>System::Convert::ToDouble\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)|  
|[tan、tanf、tanh、tanhf](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|タンジェントまたはハイパーボリック タンジェントを計算する|[System::Math::Tan](https://msdn.microsoft.com/en-us/library/system.math.tan.aspx)、[System::Math::Tanh](https://msdn.microsoft.com/en-us/library/system.math.tanh.aspx)|  
  
## 参照  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)