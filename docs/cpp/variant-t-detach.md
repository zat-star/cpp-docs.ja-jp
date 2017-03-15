---
title: "_variant_t::Detach | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_variant_t::Detach"
  - "_variant_t.Detach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Detach メソッド"
  - "VARIANT オブジェクト"
  - "VARIANT オブジェクト, デタッチ"
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# _variant_t::Detach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 この `_variant_t` オブジェクトからカプセル化された **VARIANT** オブジェクトをデタッチします。  
  
## 構文  
  
```  
  
VARIANT Detach( );  
  
```  
  
## 戻り値  
 カプセル化された **VARIANT**。  
  
## 解説  
 カプセル化された **VARIANT** を抽出して戻し、この `_variant_t` オブジェクトを破棄せずにクリアします。  このメンバー関数は、カプセル化から **VARIANT** を削除し、この `_variant_t` オブジェクトの **VARTYPE** を `VT_EMPTY` に設定します。  返された **VARIANT** は、開発者が [VariantClear](http://msdn.microsoft.com/ja-jp/28741d81-8404-4f85-95d3-5c209ec13835) を呼び出して解放します。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_variant\_t クラス](../cpp/variant-t-class.md)