---
title: "gamma_distribution クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "random/std::tr1::gamma_distribution"
  - "std::tr1::gamma_distribution"
  - "std.tr1.gamma_distribution"
  - "tr1.gamma_distribution"
  - "tr1::gamma_distribution"
  - "gamma_distribution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gamma_distribution クラス"
  - "gamma_distribution クラス [TR1]"
ms.assetid: 2a6798ac-6152-41d7-8ef6-d684d92f1572
caps.latest.revision: 18
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# gamma_distribution クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ガンマ分布を生成します。  
  
## 構文  
  
```  
template<class RealType = double> class gamma_distribution { public:     // types     typedef RealType result_type;     struct param_type;     // constructors and reset functions     explicit gamma_distribution(RealType alpha = 1.0, RealType beta = 1.0);     explicit gamma_distribution(const param_type& parm);     void reset();     // generating functions     template<class URNG>     result_type operator()(URNG& gen);     template<class URNG>     result_type operator()(URNG& gen, const param_type& parm);     // property functions     RealType alpha() const;     RealType beta() const;     param_type param() const;     void param(const param_type& parm);     result_type min() const;     result_type max() const; };  
```  
  
#### パラメーター  
 `RealType`  
 結果を表す浮動小数点型。既定値は `double` です。  使用可能な型については、「[\<random\>](../standard-library/random.md)」を参照してください。  
  
## 解説  
 このテンプレート クラスは、ガンマ分布に従って分布した、ユーザー指定の整数型の値または型 `double` の値 \(指定がない場合\) を生成する分布を表します。  次の表は、個々のメンバーに関する記事にリンクしています。  
  
||||  
|-|-|-|  
|[gamma\_distribution::gamma\_distribution](../Topic/gamma_distribution::gamma_distribution.md)|`gamma_distribution::alpha`|`gamma_distribution::param`|  
|`gamma_distribution::operator()`|`gamma_distribution::beta`|[gamma\_distribution::param\_type](../Topic/gamma_distribution::param_type.md)|  
  
 プロパティ関数 `alpha()` と `beta()` はそれぞれ、格納されている分布パラメーター `alpha` と `beta` の値を返します。  
  
 分布クラスとそのメンバーの詳細については、「[\<random\>](../standard-library/random.md)」を参照してください。  
  
 ガンマ分布の詳細については、Wolfram MathWorld の記事「[ガンマ分布](http://go.microsoft.com/fwlink/?LinkId=401111)」を参照してください。  
  
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
  
    std::gamma_distribution<> distr(a, b);  
  
    std::cout << std::endl;  
    std::cout << "min() == " << distr.min() << std::endl;  
    std::cout << "max() == " << distr.max() << std::endl;  
    std::cout << "alpha() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.alpha() << std::endl;  
    std::cout << "beta() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.beta() << std::endl;  
  
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
    std::cout << "Enter a floating point value for the 'alpha' distribution parameter (must be greater than zero): ";  
    std::cin >> a_dist;  
    std::cout << "Enter a floating point value for the 'beta' distribution parameter (must be greater than zero): ";  
    std::cin >> b_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(a_dist, b_dist, samples);  
}  
  
```  
  
## 出力  
  
```  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'alpha' distribution parameter (must be greater than zero): 1  
Enter a floating point value for the 'beta' distribution parameter (must be greater than zero): 1  
Enter an integer value for the sample count: 10  
  
min() == 4.94066e-324  
max() == 1.79769e+308  
alpha() == 1.0000000000  
beta() == 1.0000000000  
Distribution for 10 samples:  
          1:   0.0936880533  
          2:   0.1225944894  
          3:   0.6443593183  
          4:   0.6551171649  
          5:   0.7313457551  
          6:   0.7313557977  
          7:   0.7590097389  
          8:   1.4466885214  
          9:   1.6434088411  
         10:   2.1201210996  
```  
  
## 必要条件  
 **ヘッダー:** \<random\>  
  
 **名前空間:** std  
  
## 参照  
 [\<random\>](../standard-library/random.md)