---
title: "geometric_distribution クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.geometric_distribution"
  - "random/std::tr1::geometric_distribution"
  - "tr1::geometric_distribution"
  - "tr1.geometric_distribution"
  - "geometric_distribution"
  - "std::tr1::geometric_distribution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "geometric_distribution クラス"
  - "geometric_distribution クラス [TR1]"
ms.assetid: 38f933af-3b49-492e-9d26-b6b272a60013
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# geometric_distribution クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

幾何分布を生成します。  
  
## 構文  
  
```  
template<class IntType = int> class geometric_distribution { public:     // types     typedef IntType result_type;     struct param_type;     // constructors and reset functions     explicit geometric_distribution(double p = 0.5);     explicit geometric_distribution(const param_type& parm);     void reset();     // generating functions     template<class URNG>     result_type operator()(URNG& gen);     template<class URNG>     result_type operator()(URNG& gen, const param_type& parm);     // property functions     double p() const;     param_type param() const;     void param(const param_type& parm);     result_type min() const;     result_type max() const; };  
```  
  
#### パラメーター  
 `IntType`  
 結果を表す整数型。既定値は `int` です。  使用可能な型については、「[\<random\>](../standard-library/random.md)」を参照してください。  
  
## 解説  
 このテンプレート クラスは、幾何分布を使用してユーザー指定の整数型の値を生成する分布を表します。  次の表は、個々のメンバーに関する記事にリンクしています。  
  
||||  
|-|-|-|  
|[geometric\_distribution::geometric\_distribution](../Topic/geometric_distribution::geometric_distribution.md)|`geometric_distribution::p`|`geometric_distribution::param`|  
|`geometric_distribution::operator()`||[geometric\_distribution::param\_type](../Topic/geometric_distribution::param_type.md)|  
  
 プロパティ関数 `p()` は、格納されている分布パラメーター `p` の値を返します。  
  
 分布クラスとそのメンバーの詳細については、「[\<random\>](../standard-library/random.md)」を参照してください。  
  
 カイ 2 乗分布の詳細については、Wolfram MathWorld の記事「[Geometric Distribution \(幾何分布\)](http://go.microsoft.com/fwlink/?LinkId=400529)」を参照してください。  
  
## 使用例  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const double p, const int s) {  
  
    // uncomment to use a non-deterministic generator  
    //    std::random_device gen;  
    std::mt19937 gen(1701);  
  
    std::geometric_distribution<> distr(p);  
  
    std::cout << std::endl;  
    std::cout << "min() == " << distr.min() << std::endl;  
    std::cout << "max() == " << distr.max() << std::endl;  
    std::cout << "p() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.p() << std::endl;  
  
    // generate the distribution as a histogram  
    std::map<int, int> histogram;  
    for (int i = 0; i < s; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    std::cout << "Distribution for " << s << " samples:" << std::endl;  
    for (const auto& elem : histogram) {  
        std::cout << std::setw(5) << elem.first << ' ' << std::string(elem.second, ':') << std::endl;  
    }  
    std::cout << std::endl;  
}  
  
int main()  
{  
    double p_dist = 0.5;  
  
    int samples = 100;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a floating point value for the \'p\' distribution parameter: ";  
    std::cin >> p_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(p_dist, samples);  
}  
  
```  
  
## 出力  
 最初のテスト:  
  
  **Use CTRL\-Z to bypass data entry and run using default values.  Enter a floating point value for the 'p' distribution parameter: 0.5**  
**Enter an integer value for the sample count: 100**  
**min\(\) \=\= 0**  
**max\(\) \=\= 2147483647**  
**p\(\) \=\= 0.5000000000**  
**Distribution for 100 samples:**  
 **0 ::::::::::::::::::::::::::::::::::::::::::::::::::::**  
 **1 ::::::::::::::::::::::::**  
 **2 ::::::::::::::**  
 **3 :::::**  
 **4 ::**  
 **5 ::**  
**6 :**  2 回目のテスト:  
  
  **Use CTRL\-Z to bypass data entry and run using default values.  Enter a floating point value for the 'p' distribution parameter: .1**  
**Enter an integer value for the sample count: 100**  
**min\(\) \=\= 0**  
**max\(\) \=\= 2147483647**  
**p\(\) \=\= 0.1000000000**  
**Distribution for 100 samples:**  
 **0 :::::::::**  
 **1 :::::::::::**  
 **2 :::::::**  
 **3 ::::::::**  
 **4 ::::::::**  
 **5 ::::::**  
 **6 :::::**  
 **7 ::::::**  
 **8 :::::**  
 **9 ::::**  
 **10 ::::**  
 **11 ::**  
 **12 :**  
 **13 :**  
 **14 :::**  
 **15 ::::**  
 **16 :::**  
 **17 :**  
 **18 :**  
 **19 :**  
 **20 ::**  
 **21 :**  
 **22 :**  
 **23 :**  
 **28 ::**  
 **33 :**  
 **35 :**  
**40 :**    
## 必要条件  
 **ヘッダー:** \<random\>  
  
 **名前空間:** std  
  
## 参照  
 [\<random\>](../standard-library/random.md)