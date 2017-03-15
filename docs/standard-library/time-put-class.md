---
title: "time_put クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::time_put"
  - "time_put"
  - "xloctime/std::time_put"
  - "std.time_put"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "time_put クラス"
ms.assetid: df79493e-3331-48d2-97c3-ac3a745f0791
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# time_put クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスは、時刻値から `CharType` 型のシーケンスへの変換を制御するためにロケール ファセットとして使用できるオブジェクトを表します。  
  
## 構文  
  
```  
template <  
   class CharType,  
   class OutputIterator = ostreambuf_iterator<CharType>  
> class time_put : public locale::facet;  
```  
  
#### パラメーター  
 `CharType`  
 文字をエンコードするためにプログラム内で使用される型。  
  
 `OutputIterator`  
 時刻の put 関数が出力を書き込む反復子の型。  
  
## 解説  
 すべてのロケールのファセットと同様、静的オブジェクト ID に最初に格納されている値は 0 です。  格納されている値に初めてアクセスしようとすると、**id** に一意の正の値が格納されます。  
  
### コンストラクター  
  
|||  
|-|-|  
|[time\_put](../Topic/time_put::time_put.md)|`time_put` 型のオブジェクトのコンストラクター。|  
  
### Typedef  
  
|||  
|-|-|  
|[char\_type](../Topic/time_put::char_type.md)|ロケールによって使用される文字を表すために使用される型。|  
|[iter\_type](../Topic/time_put::iter_type.md)|出力反復子を表す型。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[do\_put](../Topic/time_put::do_put.md)|時刻と日付の情報を `CharType` のシーケンスとして出力する仮想関数。|  
|[put](../Topic/time_put::put.md)|時刻と日付の情報を `CharType` のシーケンスとして出力します。|  
  
## 必要条件  
 **ヘッダー:** \<locale\>  
  
 **名前空間:** std  
  
## 参照  
 [\<locale\>](../standard-library/locale.md)   
 [time\_base クラス](../Topic/time_base%20Class.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)