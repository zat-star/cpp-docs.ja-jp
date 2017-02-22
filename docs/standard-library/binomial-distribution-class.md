---
title: "binomial_distribution クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::binomial_distribution"
  - "std.tr1.binomial_distribution"
  - "tr1::binomial_distribution"
  - "random/std::tr1::binomial_distribution"
  - "tr1.binomial_distribution"
  - "binomial_distribution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "binomial_distribution クラス"
  - "binomial_distribution クラス [TR1]"
ms.assetid: b7c8a26a-da8c-45a5-a3a8-208f7a3609ce
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# binomial_distribution クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

二項分布を生成します。  
  
## 構文  
  
```  
template<class IntType = int> class binomial_distribution { public:     // types     typedef IntType result_type;     struct param_type;     // constructors and reset functions     explicit binomial_distribution(IntType t = 1, double p = 0.5);     explicit binomial_distribution(const param_type& parm);     void reset();     // generating functions     template<class URNG>     result_type operator()(URNG& gen);     template<class URNG>     result_type operator()(URNG& gen, const param_type& parm);     // property functions     IntType t() const;     double p() const;     param_type param() const;     void param(const param_type& parm);     result_type min() const;     result_type max() const; };  
```  
  
#### パラメーター  
 `IntType`  
 結果を表す整数型。既定値は `int` です。  使用可能な型については、「[\<random\>](../standard-library/random.md)」を参照してください。  
  
## 解説  
 このテンプレート クラスは、二項分布の離散確率関数に従って分布した、ユーザー指定の整数型の値または型 `int` の値 \(指定がない場合\) を生成する分布を表します。  次の表は、個々のメンバーに関する記事にリンクしています。  
  
||||  
|-|-|-|  
|[binomial\_distribution::binomial\_distribution](../Topic/binomial_distribution::binomial_distribution.md)|`binomial_distribution::t`|`binomial_distribution::param`|  
|`binomial_distribution::operator()`|`binomial_distribution::p`|[binomial\_distribution::param\_type](../Topic/binomial_distribution::param_type.md)|  
  
 プロパティ メンバー `t()` と `p()` はそれぞれ、格納されている分布パラメーター `t` と `p` の値を返します。  
  
 分布クラスとそのメンバーの詳細については、「[\<random\>](../standard-library/random.md)」を参照してください。  
  
 二項分布の離散確率関数の詳細については、Wolfram MathWorld の記事「[二項分布](http://go.microsoft.com/fwlink/?LinkId=398469)」を参照してください。  
  
## 使用例  
  
```cpp  
 // compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const int t, const double p, const int& s) {  
  
    // uncomment to use a non-deterministic seed  
    //    std::random_device rd;  
    //    std::mt19937 gen(rd());  
    std::mt19937 gen(1729);  
  
    std::binomial_distribution<> distr(t, p);  
  
    std::cout << std::endl;  
    std::cout << "p == " << distr.p() << std::endl;  
    std::cout << "t == " << distr.t() << std::endl;  
  
    // generate the distribution as a histogram  
    std::map<int, int> histogram;  
    for (int i = 0; i < s; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    std::cout << "Histogram for " << s << " samples:" << std::endl;  
    for (const auto& elem : histogram) {  
        std::cout << std::setw(5) << elem.first << ' ' << std::string(elem.second, ':') << std::endl;  
    }  
    std::cout << std::endl;  
}  
  
int main()  
{  
    int    t_dist = 1;  
    double p_dist = 0.5;  
    int    samples = 100;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter an integer value for t distribution (where 0 <= t): ";  
    std::cin >> t_dist;  
    std::cout << "Enter a double value for p distribution (where 0.0 <= p <= 1.0): ";  
    std::cin >> p_dist;  
    std::cout << "Enter an integer value for a sample count: ";  
    std::cin >> samples;  
  
    test(t_dist, p_dist, samples);  
}  
```  
  
## 出力  
 最初の実行:  
  
```  
Use CTRL-Z to bypass data entry and run using default values.  
Enter an integer value for t distribution (where 0 <= t): 22  
Enter a double value for p distribution (where 0.0 <= p <= 1.0): .25  
Enter an integer value for a sample count: 100  
  
p == 0.25  
t == 22  
Histogram for 100 samples:  
    1 :  
    2 ::  
    3 :::::::::::::  
    4 ::::::::::::::  
    5 :::::::::::::::::::::::::  
    6 ::::::::::::::::::  
    7 :::::::::::::  
    8 ::::::  
    9 ::::::  
   11 :  
   12 :  
  
```  
  
 2 回目の実行:  
  
```  
Use CTRL-Z to bypass data entry and run using default values.  
Enter an integer value for t distribution (where 0 <= t): 22  
Enter a double value for p distribution (where 0.0 <= p <= 1.0): .5  
Enter an integer value for a sample count: 100  
  
p == 0.5  
t == 22  
Histogram for 100 samples:  
    6 :  
    7 ::  
    8 :::::::::  
    9 ::::::::::  
   10 ::::::::::::::::  
   11 :::::::::::::::::::  
   12 :::::::::::  
   13 :::::::::::::  
   14 :::::::::::::::  
   15 ::  
   16 ::  
  
```  
  
 3 回目の実行:  
  
```  
Use CTRL-Z to bypass data entry and run using default values.  
Enter an integer value for t distribution (where 0 <= t): 22  
Enter a double value for p distribution (where 0.0 <= p <= 1.0): .75  
Enter an integer value for a sample count: 100  
  
p == 0.75  
t == 22  
Histogram for 100 samples:  
   13 ::::  
   14 :::::::::::  
   15 :::::::::::::::  
   16 :::::::::::::::::::::  
   17 ::::::::::::::  
   18 :::::::::::::::::  
   19 :::::::::::  
   20 ::::::  
   21 :  
```  
  
## 必要条件  
 **ヘッダー:** \<random\>  
  
 **名前空間:** std  
  
## 参照  
 [\<random\>](../standard-library/random.md)