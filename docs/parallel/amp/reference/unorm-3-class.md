---
title: "unorm_3 クラス | Microsoft Docs"
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
  - "amp_short_vectors/Concurrency::graphics::unorm_3::set_zy"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::zxy"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::set_zyx"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::operator-="
  - "amp_short_vectors/Concurrency::graphics::unorm_3::xzy"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::get_xzy"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::zyx"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::rgb"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::set_xz"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::set_yxz"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::set_yx"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::br"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::get_zy"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::set_zx"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::get_xyz"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::b"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::set_xyz"
  - "amp_short_vectors/Concurrency::graphics::unorm_3"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::set_z"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::set_xy"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::get_zyx"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::get_xy"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::x"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::get_zxy"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::z"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::get_x"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::operator="
  - "amp_short_vectors/Concurrency::graphics::unorm_3::yxz"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::get_yx"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::gbr"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::get_yxz"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::operator--"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::operator/="
  - "amp_short_vectors/Concurrency::graphics::unorm_3::brg"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::gb"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::zy"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::set_xzy"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::get_yzx"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::rb"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::gr"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::zx"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::r"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::xyz"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::grb"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::bg"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::get_y"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::g"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::yz"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::yx"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::get_xz"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::set_zxy"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::get_z"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::bgr"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::set_x"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::operator-"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::y"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::set_yzx"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::get_zx"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::yzx"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::operator++"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::set_yz"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::operator+="
  - "amp_short_vectors/Concurrency::graphics::unorm_3::xz"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::rg"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::xy"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::operator*="
  - "amp_short_vectors/Concurrency::graphics::unorm_3::set_y"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::get_yz"
  - "amp_short_vectors/Concurrency::graphics::unorm_3::rbg"
dev_langs: 
  - "C++"
ms.assetid: ea4e7a17-5256-464c-af28-8b01962564c0
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# unorm_3 クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

3 個の符号なし正規数の short ベクターを表します。  
  
## 構文  
  
```  
class unorm_3;  
```  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`value_type`||  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[unorm\_3::unorm\_3 コンストラクター](../Topic/unorm_3::unorm_3%20Constructor.md)|オーバーロードされます。  既定のコンストラクター。すべての要素を 0 で初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|unorm\_3::get\_x メソッド||  
|unorm\_3::get\_xy メソッド||  
|unorm\_3::get\_xyz メソッド||  
|unorm\_3::get\_xz メソッド||  
|unorm\_3::get\_xzy メソッド||  
|unorm\_3::get\_y メソッド||  
|unorm\_3::get\_yx メソッド||  
|unorm\_3::get\_yxz メソッド||  
|unorm\_3::get\_yz メソッド||  
|unorm\_3::get\_yzx メソッド||  
|unorm\_3::get\_z メソッド||  
|unorm\_3::get\_zx メソッド||  
|unorm\_3::get\_zxy メソッド||  
|unorm\_3::get\_zy メソッド||  
|unorm\_3::get\_zyx メソッド||  
|unorm\_3::ref\_b メソッド||  
|unorm\_3::ref\_g メソッド||  
|unorm\_3::ref\_r メソッド||  
|unorm\_3::ref\_x メソッド||  
|unorm\_3::ref\_y メソッド||  
|unorm\_3::ref\_z メソッド||  
|unorm\_3::set\_x メソッド||  
|unorm\_3::set\_xy メソッド||  
|unorm\_3::set\_xyz メソッド||  
|unorm\_3::set\_xz メソッド||  
|unorm\_3::set\_xzy メソッド||  
|unorm\_3::set\_y メソッド||  
|unorm\_3::set\_yx メソッド||  
|unorm\_3::set\_yxz メソッド||  
|unorm\_3::set\_yz メソッド||  
|unorm\_3::set\_yzx メソッド||  
|unorm\_3::set\_z メソッド||  
|unorm\_3::set\_zx メソッド||  
|unorm\_3::set\_zxy メソッド||  
|unorm\_3::set\_zy メソッド||  
|unorm\_3::set\_zyx メソッド||  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|unorm\_3::operator\-\- 演算子||  
|unorm\_3::operator\*\= 演算子||  
|unorm\_3::operator\/\= 演算子||  
|unorm\_3::operator\+\+ 演算子||  
|unorm\_3::operator\+\= 演算子||  
|unorm\_3::operator\= 演算子||  
|unorm\_3::operator\-\= 演算子||  
  
### パブリック定数  
  
|名前|説明|  
|--------|--------|  
|[unorm\_3::size 定数](../Topic/unorm_3::size%20Constant.md)||  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|unorm\_3::b データ メンバー||  
|unorm\_3::bg データ メンバー||  
|unorm\_3::bgr データ メンバー||  
|unorm\_3::br データ メンバー||  
|unorm\_3::brg データ メンバー||  
|unorm\_3::g データ メンバー||  
|unorm\_3::gb データ メンバー||  
|unorm\_3::gbr データ メンバー||  
|unorm\_3::gr データ メンバー||  
|unorm\_3::grb データ メンバー||  
|unorm\_3::r データ メンバー||  
|unorm\_3::rb データ メンバー||  
|unorm\_3::rbg データ メンバー||  
|unorm\_3::rg データ メンバー||  
|unorm\_3::rgb データ メンバー||  
|unorm\_3::x データ メンバー||  
|unorm\_3::xy データ メンバー||  
|unorm\_3::xyz データ メンバー||  
|unorm\_3::xz データ メンバー||  
|unorm\_3::xzy データ メンバー||  
|unorm\_3::y データ メンバー||  
|unorm\_3::yx データ メンバー||  
|unorm\_3::yxz データ メンバー||  
|unorm\_3::yz データ メンバー||  
|unorm\_3::yzx データ メンバー||  
|unorm\_3::z データ メンバー||  
|unorm\_3::zx データ メンバー||  
|unorm\_3::zxy データ メンバー||  
|unorm\_3::zy データ メンバー||  
|unorm\_3::zyx データ メンバー||  
  
## 継承階層  
 `unorm_3`  
  
## 必要条件  
 **ヘッダー:** amp\_short\_vectors.h  
  
 **名前空間:** Concurrency::graphics  
  
## 参照  
 [Concurrency::graphics 名前空間](../../../parallel/amp/reference/concurrency-graphics-namespace.md)