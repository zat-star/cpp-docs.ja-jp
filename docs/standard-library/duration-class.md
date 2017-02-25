---
title: "duration クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "chrono/std::chrono::duration"
dev_langs: 
  - "C++"
ms.assetid: 06b863b3-65be-4ded-a72e-6e1eb1531077
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# duration クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

2 つの時点の間における経過時間である *time interval* を保持する型を記述します。  
  
## 構文  
  
```  
template<  
   class Rep,  
   class Period = ratio<1>  
>  
class duration;  
template<  
   class Rep,  
   class Period  
>  
class duration;  
template<  
   class Rep,  
   class Period1,  
   class Period2  
>  
class duration  
   <duration<Rep, Period1>, Period2>;  
```  
  
## 解説  
 テンプレート引数 `Rep` では、間隔内でのクロック ティック数を保持するために使用する型を記述します。  テンプレート引数 `Period` は、各ティックが表す間隔のサイズを記述する[比率](../standard-library/ratio.md)のインスタンス化です。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|[duration::period Typedef](http://msdn.microsoft.com/ja-jp/ebf2a1b9-769f-475f-8c66-cf9ed12015f2)|テンプレート パラメーター `Period` のシノニムを表します。|  
|[duration::rep Typedef](http://msdn.microsoft.com/ja-jp/f47b8abb-ae2c-4dc8-858a-f44695156950)|テンプレート パラメーター `Rep` のシノニムを表します。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[duration::duration コンストラクター](../Topic/duration::duration%20Constructor.md)|`duration` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[duration::count メソッド](../Topic/duration::count%20Method.md)|時間間隔内でのクロック ティック数を返します。|  
|[duration::max メソッド](../Topic/duration::max%20Method.md)|静的。  テンプレート パラメーター `Ref` の最大許容値を返します。|  
|[duration::min メソッド](../Topic/duration::min%20Method.md)|静的。  テンプレート パラメーター `Ref` の最小許容値を返します。|  
|[duration::zero メソッド](../Topic/duration::zero%20Method.md)|静的。  実際には、`Rep`\(0\) を返します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[duration::operator\- 演算子](../Topic/duration::operator-%20Operator.md)|無効にされたティック カウントと共に、`duration` オブジェクトのコピーを返します。|  
|[duration::operator\-\- 演算子](../Topic/duration::operator--%20Operator.md)|格納されたティック カウントをデクリメントします。|  
|[duration::operator\= 演算子](../Topic/duration::operator=%20Operator.md)|格納されたティック カウントを指定された値だけ少なくします。|  
|[duration::operator\*\= 演算子](../Topic/duration::operator*=%20Operator.md)|格納されたティック カウントを指定した値で乗算します。|  
|[duration::operator\/\= 演算子](../Topic/duration::operator-=%20Operator1.md)|格納されたティック カウントを、指定した `duration` オブジェクトのティック カウントで除算します。|  
|[duration::operator\+ 演算子](../Topic/duration::operator+%20Operator.md)|`*this` を返します。|  
|[duration::operator\+\+ 演算子](../Topic/duration::operator++%20Operator.md)|格納されたティック カウントをインクリメントします。|  
|[duration::operator\+\= 演算子](../Topic/duration::operator+=%20Operator.md)|指定した `duration` オブジェクトのティック カウントを、格納されたティック カウントに加算します。|  
|[duration::operator\-\= 演算子](../Topic/duration::operator-=%20Operator2.md)|指定した `duration` オブジェクトのティック カウントを、格納されたティック カウントから減算します。|  
  
## 必要条件  
 **ヘッダー:** chrono  
  
 **名前空間:** std::chrono  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)   
 [duration\_values 構造体](../standard-library/duration-values-structure.md)