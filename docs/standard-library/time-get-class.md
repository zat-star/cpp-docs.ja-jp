---
title: "time_get クラス | Microsoft Docs"
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
  - "std.time_get"
  - "xloctime/std::time_get"
  - "time_get"
  - "std::time_get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "time_get クラス"
ms.assetid: 869d5f5b-dbab-4628-8333-bdea7e272023
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# time_get クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスは、`CharType` 型のシーケンスから時刻値への変換を制御するためにロケール ファセットとして使用できるオブジェクトを表します。  
  
## 構文  
  
```  
template <  
   class CharType,  
   class InputIterator = istreambuf_iterator<CharType>  
> class time_get : public time_base;  
```  
  
#### パラメーター  
 `CharType`  
 文字をエンコードするためにプログラム内で使用される型。  
  
 `InputIterator`  
 時刻値の読み取り元の反復子。  
  
## 解説  
 すべてのロケールのファセットと同様、静的オブジェクト ID に最初に格納されている値は 0 です。  格納されている値に初めてアクセスしようとすると、**id** に一意の正の値が格納されます。  
  
### コンストラクター  
  
|||  
|-|-|  
|[time\_get](../Topic/time_get::time_get.md)|`time_get` 型のオブジェクトのコンストラクター。|  
  
### Typedef  
  
|||  
|-|-|  
|[char\_type](../Topic/time_get::char_type.md)|ロケールによって使用される文字を表すために使用される型。|  
|[iter\_type](../Topic/time_get::iter_type.md)|入力反復子を表す型。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[date\_order](../Topic/time_get::date_order.md)|ファセットによって使用される日付順序を返します。|  
|[do\_date\_order](../Topic/time_get::do_date_order.md)|ファセットによって使用される日付順序を返すために呼び出されるプロテクト仮想メンバー関数。|  
|[do\_get](../Topic/time_get::do_get.md)|文字データを読み取り、時刻値に変換します。|  
|[do\_get\_date](../Topic/time_get::do_get_date.md)|`strftime` の `x` 指定子によって生成される日付として文字列を解析するために呼び出されるプロテクト仮想メンバー関数。|  
|[do\_get\_monthname](../Topic/time_get::do_get_monthname.md)|月の名前として文字列を解析するために呼び出されるプロテクト仮想メンバー関数。|  
|[do\_get\_time](../Topic/time_get::do_get_time.md)|`strftime` の `X` 指定子によって生成される日付として文字列を解析するために呼び出されるプロテクト仮想メンバー関数。|  
|[do\_get\_weekday](../Topic/time_get::do_get_weekday.md)|曜日の名前として文字列を解析するために呼び出されるプロテクト仮想メンバー関数。|  
|[do\_get\_year](../Topic/time_get::do_get_year.md)|年の名前として文字列を解析するために呼び出されるプロテクト仮想メンバー関数。|  
|[get](../Topic/time_get::get.md)|文字データのソースからデータを読み取り、そのデータを time 構造体に格納される時刻に変換します。|  
|[get\_date](../Topic/time_get::get_date.md)|`strftime` の `x` 指定子によって生成される日付として文字列を解析します。|  
|[get\_monthname](../Topic/time_get::get_monthname.md)|月の名前として文字列を解析します。|  
|[get\_time](../Topic/time_get::get_time.md)|`strftime` の `X` 指定子によって生成される日付として文字列を解析します。|  
|[get\_weekday](../Topic/time_get::get_weekday.md)|曜日の名前として文字列を解析します。|  
|[get\_year](../Topic/time_get::get_year.md)|年の名前として文字列を解析します。|  
  
## 必要条件  
 **ヘッダー:** \<locale\>  
  
 **名前空間:** std  
  
## 参照  
 [\<locale\>](../standard-library/locale.md)   
 [time\_base クラス](../Topic/time_base%20Class.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)