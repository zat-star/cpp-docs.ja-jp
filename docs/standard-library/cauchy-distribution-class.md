---
title: "cauchy_distribution クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cauchy_distribution"
  - "random/std::tr1::cauchy_distribution"
  - "std::tr1::cauchy_distribution"
  - "std.tr1.cauchy_distribution"
  - "tr1::cauchy_distribution"
  - "tr1.cauchy_distribution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cauchy_distribution クラス"
ms.assetid: 21522351-f2f1-46d9-97f0-d358c932356c
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# cauchy_distribution クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コーシー分布を生成します。  
  
## 構文  
  
```  
template<class RealType = double> class cauchy_distribution { public:     // types     typedef RealType result_type;     struct param_type;     // constructor and reset functions     explicit cauchy_distribution(RealType a = 0.0, RealType b = 1.0);     explicit cauchy_distribution(const param_type& parm);     void reset();     // generating functions     template<class URNG>     result_type operator()(URNG& gen);     template<class URNG>     result_type operator()(URNG& gen, const param_type& parm);     // property functions     RealType a() const;     RealType b() const;     param_type param() const;     void param(const param_type& parm);     result_type min() const;     result_type max() const; };  
```  
  
#### パラメーター  
 `RealType`  
 結果を表す浮動小数点型。既定値は `double` です。  使用可能な型については、「[\<random\>](../standard-library/random.md)」を参照してください。  
  
## 解説  
 このテンプレート クラスは、コーシー分布に従って分布した、ユーザー指定の整数型の値または型 `double` の値 \(指定がない場合\) を生成する分布を表します。  次の表は、個々のメンバーに関する記事にリンクしています。  
  
||||  
|-|-|-|  
|[cauchy\_distribution::cauchy\_distribution](../Topic/cauchy_distribution::cauchy_distribution.md)|`cauchy_distribution::a`|`cauchy_distribution::param`|  
|`cauchy_distribution::operator()`|`cauchy_distribution::b`|[cauchy\_distribution::param\_type](../Topic/cauchy_distribution::param_type.md)|  
  
 プロパティ関数 `a()` と `b()` はそれぞれ、格納されている分布パラメーター `a` と `b` の値を返します。  
  
 分布クラスとそのメンバーの詳細については、「[\<random\>](../standard-library/random.md)」を参照してください。  
  
 コーシー分布の詳細については、Wolfram MathWorld の記事「[コーシー分布](http://go.microsoft.com/fwlink/?LinkId=400523)」を参照してください。  
  
## 使用例  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const double a, const double b, const int s) {  
  
    // uncomment to use a non-deterministic generator  
    //    std::random_device gen;  
  
    std::mt19937 gen(1701);  
  
    std::cauchy_distribution<> distr(a, b);  
  
    std::cout << std::endl;  
    std::cout << "min() == " << distr.min() << std::endl;  
    std::cout << "max() == " << distr.max() << std::endl;  
    std::cout << "a() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.a() << std::endl;  
    std::cout << "b() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.b() << std::endl;  
  
    // generate the distribution as a histogram  
    std::map<double, int> histogram;  
    for (int i = 0; i < s; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    std::cout << "Distribution for " << s << " samples:" << std::endl;  
    int counter = 0;  
    for (const auto& elem : histogram) {  
        std::cout << std::fixed << std::setw(11) << ++counter << ": "  
            << std::setw(14) << std::setprecision(10) << elem.first << std::endl;  
    }  
    std::cout << std::endl;  
}  
  
int main()  
{  
    double a_dist = 0.0;  
    double b_dist = 1;  
  
    int samples = 10;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a floating point value for the 'a' distribution parameter: ";  
    std::cin >> a_dist;  
    std::cout << "Enter a floating point value for the 'b' distribution parameter (must be greater than zero): ";  
    std::cin >> b_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(a_dist, b_dist, samples);  
}  
  
```  
  
## 出力  
 最初の実行:  
  
```  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'a' distribution parameter: 0  
Enter a floating point value for the 'b' distribution parameter (must be greater than zero): 1  
Enter an integer value for the sample count: 10  
  
min() == -1.79769e+308  
max() == 1.79769e+308  
a() == 0.0000000000  
b() == 1.0000000000  
Distribution for 10 samples:  
          1:  -3.4650392984  
          2:  -2.6369564174  
          3:  -0.0786978867  
          4:  -0.0609632093  
          5:   0.0589387400  
          6:   0.0589539764  
          7:   0.1004592006  
          8:   1.0965724260  
          9:   1.4389408122  
         10:   2.5253154706  
```  
  
 2 回目の実行:  
  
```  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'a' distribution parameter: 0  
Enter a floating point value for the 'b' distribution parameter (must be greater than zero): 10  
Enter an integer value for the sample count: 10  
  
min() == -1.79769e+308  
max() == 1.79769e+308  
a() == 0.0000000000  
b() == 10.0000000000  
Distribution for 10 samples:  
          1: -34.6503929840  
          2: -26.3695641736  
          3:  -0.7869788674  
          4:  -0.6096320926  
          5:   0.5893873999  
          6:   0.5895397637  
          7:   1.0045920062  
          8:  10.9657242597  
          9:  14.3894081218  
         10:  25.2531547063  
```  
  
 3 回目の実行:  
  
```  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'a' distribution parameter: 10  
Enter a floating point value for the 'b' distribution parameter (must be greater than zero): 10  
Enter an integer value for the sample count: 10  
  
min() == -1.79769e+308  
max() == 1.79769e+308  
a() == 10.0000000000  
b() == 10.0000000000  
Distribution for 10 samples:  
          1: -24.6503929840  
          2: -16.3695641736  
          3:   9.2130211326  
          4:   9.3903679074  
          5:  10.5893873999  
          6:  10.5895397637  
          7:  11.0045920062  
          8:  20.9657242597  
          9:  24.3894081218  
         10:  35.2531547063  
```  
  
## 必要条件  
 **ヘッダー:** \<random\>  
  
 **名前空間:** std  
  
## 参照  
 [\<random\>](../standard-library/random.md)