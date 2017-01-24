---
title: "alignment_of クラス | Microsoft Docs"
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
  - "std.tr1.alignment_of"
  - "std::tr1::alignment_of"
  - "alignment_of"
  - "std.alignment_of"
  - "std::alignment_of"
  - "type_traits/std::alignment_of"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "alignment_of クラス [TR1]"
  - "alignment_of"
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
caps.latest.revision: 22
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# alignment_of クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定された型のアラインメントを取得します。  この構造体は、[alignof](../cpp/alignof-and-alignas-cpp.md) の観点から実装されています。  単にアラインメント値を照会すればよい場合は、`alignof` を直接使用します。  タグ ディスパッチを行うときのように整数定数が必要な場合は、alignment\_of を使用します。  
  
## 構文  
  
```  
template<class Ty>  
    struct alignment_of;  
```  
  
#### パラメーター  
 `Ty`  
 照会する型。  
  
## 解説  
 型クエリは、型 `Ty` のアラインメントの値を保持します。  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [aligned\_storage クラス](../standard-library/aligned-storage-class.md)