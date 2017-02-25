---
title: "&lt;chrono&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "chrono/std::chrono::nanoseconds"
  - "chrono/std::chrono::minutes"
  - "chrono/std::chrono::seconds"
  - "<chrono>"
  - "chrono/std::chrono::hours"
  - "chrono/std::chrono::milliseconds"
  - "chrono/std::chrono::microseconds"
dev_langs: 
  - "C++"
ms.assetid: 844de749-f306-482e-89bc-6f53c99c8324
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# &lt;chrono&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

期間と時点を表し、操作するクラスと関数を定義するために、標準ヘッダー \<chrono\> を含めます。  
  
 **\(Visual Studio 2015:\)** `steady_clock` の実装が変更され、安定性と単調性のための C\+\+ 標準の要件を満たすようになりました。  現在、`steady_clock` は QueryPerformanceCounter\(\) に基づき、`high_resolution_clock` は `steady_clock` の typedef です。  結果として、Visual C\+\+ では現在、`steady_clock::time_point` は `chrono::time_point<steady_clock>` の typedef です。ただし、他の実装では異なる場合があります。  
  
## 構文  
  
```cpp  
#include <chrono>  
```  
  
### リテラル  
 \<chrono\> ヘッダー内のリテラルは、literals::chrono\_literals インライン名前空間のメンバーです。  詳細については、「[chrono のリテラル](../Topic/chrono%20literals.md)」を参照してください。  
  
|||  
|-|-|  
|operator "" h\(unsigned long long Val\) operator "" h\(long double Val\)|値が時間を表すことを指定します。|  
|operator "" min\(unsigned long long Val\)  operator "" min\(long double Val\)|値が分を表すことを指定します。|  
|operator "" s\(unsigned long long Val\)operator "" s\(long double Val\)|値が秒を表すことを指定します。|  
|operator "" ms\(unsigned long long Val\)operator "" ms\(long double Val\)|値がミリ秒を表すことを指定します。|  
|operator "" us\(unsigned long long Val\)operator "" us\(long double Val\)|値がマイクロ秒を表すことを指定します。|  
|operator "" ns\(unsigned long long Val\)operator "" ns\(long double Val\)|値がナノ秒を表すことを指定します。|  
  
### クラス  
  
|名前|説明|  
|--------|--------|  
|[duration クラス](../standard-library/duration-class.md)|時間間隔を保持する型を表します。|  
|[time\_point クラス](../standard-library/time-point-class.md)|時点を表す型を表します。|  
  
### 構造体  
  
|名前|説明|  
|--------|--------|  
|[common\_type 構造体](../standard-library/common-type-structure.md)|`duration` と `time_point` のインスタンス化のテンプレート クラス [common\_type](../standard-library/common-type-class.md) の特殊化を表します。|  
|[duration\_values 構造体](../standard-library/duration-values-structure.md)|`duration` テンプレート パラメーター `Rep` に特定の値を指定します。|  
|[steady\_clock 構造体](../Topic/steady_clock%20struct.md)|`steady` クロックを表します。|  
|[system\_clock 構造体](../standard-library/system-clock-structure.md)|システムのリアルタイム クロックに基づく*クロックの型*を表します。|  
|[treat\_as\_floating\_point 構造体](../standard-library/treat-as-floating-point-structure.md)|型を浮動小数点型として扱うことができるかどうかを指定します。|  
  
### 関数  
  
|名前|説明|  
|--------|--------|  
|[duration\_cast 関数](../Topic/duration_cast%20Function.md)|`duration` オブジェクトを指定した型にキャストします。|  
|[time\_point\_cast 関数](../Topic/time_point_cast%20Function.md)|`time_point` オブジェクトを指定した型にキャストします。|  
  
### 演算子  
  
|名前|説明|  
|--------|--------|  
|[operator\- 演算子 \(STL\)](../Topic/operator-%20Operator%20\(STL\)1.md)|`duration` オブジェクトおよび `time_point` オブジェクトの減算または否定の演算子。|  
|[operator\!\= 演算子 \(STL\)](../Topic/operator!=%20Operator%20\(STL\).md)|`duration` オブジェクトおよび `time_point` オブジェクトで使用される非等値演算子。|  
|[modulo 演算子 \(STL\)](../Topic/operator%20modulo%20\(STL\).md)|`duration` オブジェクトに対するモジュロ演算の演算子。|  
|[operator\* 演算子 \(STL\)](../Topic/operator*%20Operator%20\(STL\).md)|`duration` オブジェクトの乗算演算子。|  
|[operator\/ 演算子 \(STL\)](../Topic/operator-%20Operator%20\(STL\)2.md)|`duration` オブジェクトの除算演算子。|  
|[operator\+ 演算子 \(STL\)](../Topic/operator+%20Operator%20\(STL\).md)|`duration` オブジェクトおよび `time_point` オブジェクトを追加します。|  
|[operator\< 演算子 \(STL\)](../Topic/operator%3C%20Operator%20\(STL\).md)|一方の `duration` オブジェクトまたは `time_point` オブジェクトの値が、もう一方の `duration` オブジェクトまたは `time_point` オブジェクトの値未満かどうかを判断します。|  
|[operator\<\= 演算子 \(STL\)](../Topic/operator%3C=%20Operator%20\(STL\).md)|一方の `duration` オブジェクトまたは `time_point` オブジェクトの値が、もう一方の `duration` オブジェクトまたは `time_point` オブジェクトの値以下かどうかを判断します。|  
|[operator\=\= 演算子 \(STL\)](../Topic/operator==%20Operator%20\(STL\).md)|2 つの `duration` オブジェクトが同じ長さの時間間隔を表しているかどうか、または 2 つの `time_point` オブジェクトが同じ時点を表しているかどうかを判断します。|  
|[operator\> 演算子 \(STL\)](../Topic/operator%3E%20Operator%20\(STL\).md)|一方の `duration` オブジェクトまたは `time_point` オブジェクトの値が、もう一方の `duration` オブジェクトまたは `time_point` オブジェクトの値より大きいかどうかを判断します。|  
|[operator\>\= 演算子 \(STL\)](../Topic/operator%3E=%20Operator%20\(STL\).md)|一方の `duration` オブジェクトまたは `time_point` オブジェクトの値が、もう一方の `duration` オブジェクトまたは `time_point` オブジェクトの値以上かどうかを判断します。|  
  
### 定義済みの期間の種類  
 次の typedef で使用される比率の種類の詳細については、「[\<ratio\>](../standard-library/ratio.md)」を参照してください。  
  
|Typedef|説明|  
|-------------|--------|  
|`typedef duration<long long, nano> nanoseconds;`|ティック間隔が 1 ナノ秒の `duration` 型のシノニムです。|  
|`typedef duration<long long, micro> microseconds;`|ティック間隔が 1 マイクロ秒の `duration` 型のシノニムです。|  
|`typedef duration<long long, milli> milliseconds;`|ティック間隔が 1 ミリ秒の `duration` 型のシノニムです。|  
|`typedef duration<long long> seconds;`|ティック間隔が 1 秒の `duration` 型のシノニムです。|  
|`typedef duration<int, ratio<60> > minutes;`|ティック間隔が 1 分の `duration` 型のシノニムです。|  
|`typedef duration<int, ratio<3600> > hours;`|ティック間隔が 1 時間の `duration` 型のシノニムです。|  
  
### リテラル  
 **\(C\+\+11\)** \<chrono\> ヘッダーでは、次の[ユーザー定義リテラル](../Topic/User-Defined%20Literals%20%20\(C++\).md)を定義します。これを使用することで、コードの利便性、タイプ セーフ、保守性が向上します。  これらのリテラルは `literals::chrono_literals` インライン名前空間で定義されており、std::chrono がスコープに含まれている場合にスコープに含まれます。  
  
|リテラル|説明|  
|----------|--------|  
|chrono::hours operator "" h\(unsigned long long Val\)|時間を整数値として指定します。|  
|chrono::duration\<double, ratio\<3600\> \> operator "" h\(long double Val\)|時間を浮動小数点値として指定します。|  
|chrono::minutes \(operator "" min\)\(unsigned long long Val\)|分を整数値として指定します。|  
|chrono::duration\<double, ratio\<60\> \> \(operator "" min\)\( long double Val\)|分を浮動小数点値として指定します。|  
|chrono::seconds operator "" s\(unsigned long long Val\)|分を整数値として指定します。|  
|chrono::duration\<double\> operator "" s\(long double Val\)|秒を浮動小数点値として指定します。|  
|chrono::milliseconds operator "" ms\(unsigned long long Val\)|ミリ秒を整数値として指定します。|  
|chrono::duration\<double, milli\> operator "" ms\(long double Val\)|ミリ秒を浮動小数点値として指定します。|  
|chrono::microseconds operator "" us\(unsigned long long Val\)|マイクロ秒を整数値として指定します。|  
|chrono::duration\<double, micro\> operator "" us\(long double Val\)|マイクロ秒を浮動小数点値として指定します。|  
|chrono::nanoseconds operator "" ns\(unsigned long long Val\)|ナノ秒を整数値として指定します。|  
|chrono::duration\<double, nano\> operator "" ns\(long double Val\)|ナノ秒を浮動小数点値として指定します。|  
|||  
  
## 解説  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)