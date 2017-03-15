---
title: "numeric_limits クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::numeric_limits"
  - "std.numeric_limits"
  - "numeric_limits"
  - "limits/std::numeric_limits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "numeric_limits クラス"
ms.assetid: 9e817177-0e91-48e6-b680-0531c4b26625
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# numeric_limits クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスでは、組み込みの数値型の算術プロパティについて記述します。  
  
## 構文  
  
```  
template<classType> class numeric_limits  
```  
  
#### パラメーター  
 `Type`  
 プロパティがテスト、照会、設定対象になる基本的な要素のデータ型。  
  
## 解説  
 ヘッダーは次の型の明示的な特殊化を定義します。`wchar_t`、`bool`、`char`、`signed char`、`unsigned char`、`short`、`unsigned short`、`int`、`unsigned int`、`long`、`unsigned long`、`float`、`double`、`long double`**、**`long long`、`unsigned long long`、`char16_t`、および `char32_t`。 これらの明示的な特殊化では、メンバー [numeric\_limits::is\_specialized](../Topic/numeric_limits::is_specialized.md) は `true` で、関連するすべてのメンバーには有効な値が含まれます。 プログラムによって、その他の明示的な特殊化を行えます。 クラスのほとんどのメンバー関数は、`float` の可能な実装について記述またはテストします。  
  
 任意の特殊化の場合、メンバーに有効な値が含まれません。 有効な値が含まれないメンバー オブジェクトは、0 \(または `false`\) を格納します。有効な値を返さないメンバー関数は `Type(0)` を返します。  
  
### 静的な関数と定数  
  
|||  
|-|-|  
|[denorm\_min](../Topic/numeric_limits::denorm_min.md)|0 以外の最小の非正規化値を返します。|  
|[数字](../Topic/numeric_limits::digits.md)|型が精度を失うことなく表現できる基数桁数を返します。|  
|[digits10](../Topic/numeric_limits::digits10.md)|型が精度を失うことなく表現できる小数点数桁数を返します。|  
|[epsilon](../Topic/numeric_limits::epsilon.md)|1 と、データ型が表すことのできる 1 より大きい最小値との差を返します。|  
|[has\_denorm](../Topic/numeric_limits::has_denorm.md)|型が非正規化値を許可するかどうかをテストします。|  
|[has\_denorm\_loss](../Topic/numeric_limits::has_denorm_loss.md)|精度の損失が、不正確な結果ではなく、非正規化の損失として検出されるかどうかをテストします。|  
|[has\_infinity](../Topic/numeric_limits::has_infinity.md)|型が正の無限大を表すことができるかどうかをテストします。|  
|[has\_quiet\_NaN](../Topic/numeric_limits::has_quiet_NaN.md)|型が静かな \(シグナルを発生させない\) 非数 \(NaN\) を表せるかどうかをテストします。|  
|[has\_signaling\_NaN](../Topic/numeric_limits::has_signaling_NaN.md)|型がシグナルを発生する非数 \(NAN\) を表せるかどうかをテストします。|  
|[infinity](../Topic/numeric_limits::infinity.md)|型の正の無限大の表現 \(使用可能な場合\)。|  
|[is\_bounded](../Topic/numeric_limits::is_bounded.md)|型が表すことができる値のセットが有限かどうかをテストします。|  
|[is\_exact](../Topic/numeric_limits::is_exact.md)|型で実行される計算に丸め誤差がないかどうかをテストします。|  
|[is\_iec559](../Topic/numeric_limits::is_iec559.md)|型が IEC 559 標準に準拠しているかどうかをテストします。|  
|[is\_integer](../Topic/numeric_limits::is_integer.md)|型が整数を表せるかどうかをテストします。|  
|[is\_modulo](../Topic/numeric_limits::is_modulo.md)|型が剰余を表せるかどうかをテストします。|  
|[is\_signed](../Topic/numeric_limits::is_signed.md)|型が符号付きを表せるかどうかをテストします。|  
|[is\_specialized](../Topic/numeric_limits::is_specialized.md)|型に、テンプレート クラス `numeric_limits` で定義されている明示的な特殊化が含まれるかどうかをテストします。|  
|[lowest](../Topic/numeric_limits::lowest.md)|負の最小有限値を返します。|  
|[max](../Topic/numeric_limits::max.md)|型の最大の有限値を返します。|  
|[max\_digits10](../Topic/numeric_limits::max_digits10.md)|その型の 2 つの値が別個の異なる 10 進表現であることを確証するために必要な 10 進桁数を返します。|  
|[max\_exponent](../Topic/numeric_limits::max_exponent.md)|基数を累乗した場合に、浮動小数点型が有限値として表すことができる正の整数の最大指数を返します。|  
|[max\_exponent10](../Topic/numeric_limits::max_exponent10.md)|10 の基数を累乗した場合に、浮動小数点型が有限値として表すことができる正の整数の最大指数を返します。|  
|[分](../Topic/numeric_limits::min.md)|型の最小の正規化値を返します。|  
|[min\_exponent](../Topic/numeric_limits::min_exponent.md)|基数の底を累乗した場合に、浮動小数点型が有限値として表すことができる負の整数の最大指数を返します。|  
|[min\_exponent10](../Topic/numeric_limits::min_exponent10.md)|10 の基数を累乗した場合に、浮動小数点型が有限値として表すことができる負の整数の最大指数を返します。|  
|[quiet\_NaN](../Topic/numeric_limits::quiet_NaN.md)|型の静かな非数表現 \(NAN\) を返します。|  
|[radix](../Topic/numeric_limits::radix.md)|型の表現に使用される、基数と呼ばれる整数の底を返します。|  
|[round\_error](../Topic/numeric_limits::round_error.md)|型の丸め誤差の最大値を返します。|  
|[round\_style](../Topic/numeric_limits::round_style.md)|実装において、浮動小数点値を整数値に丸め処理を行うために選択可能なさまざまな方式を記述した値を返します。|  
|[signaling\_NaN](../Topic/numeric_limits::signaling_NaN.md)|型のシグナリング非数 \(NAN\) の表現を返します。|  
|[tinyness\_before](../Topic/numeric_limits::tinyness_before.md)|型が、値を丸める前に正規化された値として表現するには小さすぎることを確認できるかどうかをテストします。|  
|[traps](../Topic/numeric_limits::traps.md)|型において算術例外に関するレポートをトラップするように実装されているかどうかをテストします。|  
  
## 必要条件  
 **ヘッダー:** \<limits\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)