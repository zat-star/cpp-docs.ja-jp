---
title: "time_point クラス | Microsoft Docs"
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
  - "chrono/std::chrono::time_point"
dev_langs: 
  - "C++"
ms.assetid: 18be1e52-57b9-489a-8a9b-f58894f0aaad
caps.latest.revision: 10
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# time_point クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`time_point` では、時点を表す型について記述します。  これは、テンプレート引数 `Clock` によって表される新しいエポック以降の経過時間を格納する [duration](../standard-library/duration-class.md) 型のオブジェクトを保持します。  
  
## 構文  
  
```  
template<  
   class Clock,  
   class Duration = typename Clock::duration  
>  
class time_point;  
```  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`time_point::clock`|テンプレート パラメーター `Clock` のシノニム。|  
|`time_point::duration`|テンプレート パラメーター `Duration` のシノニム。|  
|`time_point::period`|入れ子にされた型の名前 `duration::period` のシノニム。|  
|`time_point::rep`|入れ子にされた型の名前 `duration::rep` のシノニム。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[time\_point::time\_point コンストラクター](../Topic/time_point::time_point%20Constructor.md)|`time_point` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[time\_point::max メソッド](../Topic/time_point::max%20Method.md)|`time_point::ref` の上限を指定します。|  
|[time\_point::min メソッド](../Topic/time_point::min%20Method.md)|`time_point::ref` の下限を指定します。|  
|[time\_point::time\_since\_epoch メソッド](../Topic/time_point::time_since_epoch%20Method.md)|格納された `duration` の値を返します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[time\_point::operator\+\= 演算子](../Topic/time_point::operator+=%20Operator.md)|指定した値を格納された期間に加算します。|  
|[time\_point::operator\-\= 演算子](../Topic/time_point::operator-=%20Operator.md)|指定した値を格納された期間から減算します。|  
  
## 必要条件  
 **ヘッダー:** chrono  
  
 **名前空間:** std::chrono  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)