---
title: "unorm_2 クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::operator+="
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::y"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::set_y"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::x"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::get_yx"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::operator--"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::set_xy"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::operator*="
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::xy"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::get_y"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::operator="
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::set_x"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::rg"
  - "amp_short_vectors/Concurrency::graphics::unorm_2"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::operator-="
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::operator/="
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::get_xy"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::set_yx"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::yx"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::gr"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::r"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::operator-"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::get_x"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::g"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::operator++"
dev_langs: 
  - "C++"
ms.assetid: 62e88ea7-e29f-4f62-95ce-61a1f39f5e34
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# unorm_2 クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

2 個の符号なし正規数の short ベクターを表します。  
  
## 構文  
  
```  
class unorm_2;  
```  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`value_type`||  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[unorm\_2::unorm\_2 コンストラクター](../Topic/unorm_2::unorm_2%20Constructor.md)|オーバーロードされます。  既定のコンストラクター。すべての要素を 0 で初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|unorm\_2::get\_x メソッド||  
|unorm\_2::get\_xy メソッド||  
|unorm\_2::get\_y メソッド||  
|unorm\_2::get\_yx メソッド||  
|unorm\_2::ref\_g メソッド||  
|unorm\_2::ref\_r メソッド||  
|unorm\_2::ref\_x メソッド||  
|unorm\_2::ref\_y メソッド||  
|unorm\_2::set\_x メソッド||  
|unorm\_2::set\_xy メソッド||  
|unorm\_2::set\_y メソッド||  
|unorm\_2::set\_yx メソッド||  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|unorm\_2::operator\-\- 演算子||  
|unorm\_2::operator\*\= 演算子||  
|unorm\_2::operator\/\= 演算子||  
|unorm\_2::operator\+\+ 演算子||  
|unorm\_2::operator\+\= 演算子||  
|unorm\_2::operator\= 演算子||  
|unorm\_2::operator\-\= 演算子||  
  
### パブリック定数  
  
|名前|説明|  
|--------|--------|  
|unorm\_2::size 定数||  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|unorm\_2::g データ メンバー||  
|unorm\_2::gr データ メンバー||  
|unorm\_2::r データ メンバー||  
|unorm\_2::rg データ メンバー||  
|unorm\_2::x データ メンバー||  
|unorm\_2::xy データ メンバー||  
|unorm\_2::y データ メンバー||  
|unorm\_2::yx データ メンバー||  
  
## 継承階層  
 `unorm_2`  
  
## 必要条件  
 **ヘッダー:** amp\_short\_vectors.h  
  
 **名前空間:** Concurrency::graphics  
  
## 参照  
 [Concurrency::graphics 名前空間](../../../parallel/amp/reference/concurrency-graphics-namespace.md)