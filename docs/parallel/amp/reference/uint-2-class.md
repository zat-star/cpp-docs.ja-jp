---
title: "uint_2 クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_short_vectors/Concurrency::graphics::uint_2::set_xy"
  - "amp_short_vectors/Concurrency::graphics::uint_2::y"
  - "amp_short_vectors/Concurrency::graphics::uint_2::gr"
  - "amp_short_vectors/Concurrency::graphics::uint_2::operator-"
  - "amp_short_vectors/Concurrency::graphics::uint_2::get_x"
  - "amp_short_vectors/Concurrency::graphics::uint_2::operator-="
  - "amp_short_vectors/Concurrency::graphics::uint_2::r"
  - "amp_short_vectors/Concurrency::graphics::uint_2::yx"
  - "amp_short_vectors/Concurrency::graphics::uint_2::operator--"
  - "amp_short_vectors/Concurrency::graphics::uint_2::set_yx"
  - "amp_short_vectors/Concurrency::graphics::uint_2::operator="
  - "amp_short_vectors/Concurrency::graphics::uint_2::set_x"
  - "amp_short_vectors/Concurrency::graphics::uint_2::operator+="
  - "amp_short_vectors/Concurrency::graphics::uint_2::get_y"
  - "amp_short_vectors/Concurrency::graphics::uint_2::xy"
  - "amp_short_vectors/Concurrency::graphics::uint_2::x"
  - "amp_short_vectors/Concurrency::graphics::uint_2::get_xy"
  - "amp_short_vectors/Concurrency::graphics::uint_2::set_y"
  - "amp_short_vectors/Concurrency::graphics::uint_2"
  - "amp_short_vectors/Concurrency::graphics::uint_2::operator*="
  - "amp_short_vectors/Concurrency::graphics::uint_2::get_yx"
  - "amp_short_vectors/Concurrency::graphics::uint_2::operator/="
  - "amp_short_vectors/Concurrency::graphics::uint_2::g"
  - "amp_short_vectors/Concurrency::graphics::uint_2::operator++"
  - "amp_short_vectors/Concurrency::graphics::uint_2::rg"
dev_langs: 
  - "C++"
ms.assetid: 9fcc9129-72b1-4da7-9012-4d3be15f1c52
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# uint_2 クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

2 個の符号なし整数の short ベクターを表します。  
  
## 構文  
  
```  
class uint_2;  
```  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`value_type`||  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[uint\_2::uint\_2 コンストラクター](../Topic/uint_2::uint_2%20Constructor.md)|オーバーロードされます。  既定のコンストラクター。すべての要素を 0 で初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|uint\_2::get\_x メソッド||  
|uint\_2::get\_xy メソッド||  
|uint\_2::get\_y メソッド||  
|uint\_2::get\_yx メソッド||  
|uint\_2::ref\_g メソッド||  
|uint\_2::ref\_r メソッド||  
|uint\_2::ref\_x メソッド||  
|uint\_2::ref\_y メソッド||  
|uint\_2::set\_x メソッド||  
|uint\_2::set\_xy メソッド||  
|uint\_2::set\_y メソッド||  
|uint\_2::set\_yx メソッド||  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|uint\_2::operator\-\- 演算子||  
|uint\_2::operator%\= 演算子||  
|uint\_2::operator&\= 演算子||  
|uint\_2::operator\*\= 演算子||  
|uint\_2::operator\/\= 演算子||  
|uint\_2::operator^\= 演算子||  
|uint\_2::operator&#124;\= 演算子||  
|uint\_2::operator~ 演算子||  
|uint\_2::operator\+\+ 演算子||  
|uint\_2::operator\+\= 演算子||  
|uint\_2::operator\<\<\= 演算子||  
|uint\_2::operator\= 演算子||  
|uint\_2::operator\-\= 演算子||  
|uint\_2::operator\>\>\= 演算子||  
  
### パブリック定数  
  
|名前|説明|  
|--------|--------|  
|[uint\_2::size 定数](../Topic/uint_2::size%20Constant.md)||  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|uint\_2::g データ メンバー||  
|uint\_2::gr データ メンバー||  
|uint\_2::r データ メンバー||  
|uint\_2::rg データ メンバー||  
|uint\_2::x データ メンバー||  
|uint\_2::xy データ メンバー||  
|uint\_2::y データ メンバー||  
|uint\_2::yx データ メンバー||  
  
## 継承階層  
 `uint_2`  
  
## 必要条件  
 **ヘッダー:** amp\_short\_vectors.h  
  
 **名前空間:** Concurrency::graphics  
  
## 参照  
 [Concurrency::graphics 名前空間](../../../parallel/amp/reference/concurrency-graphics-namespace.md)