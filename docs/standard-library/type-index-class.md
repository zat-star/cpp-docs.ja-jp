---
title: "type_index クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "typeindex/std::type_index"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "type_index クラス"
ms.assetid: db366119-74cb-43e8-aacf-9679e561fa2f
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# type_index クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`type_index` クラスは [type\_info Class](../cpp/type-info-class.md) にこのようなオブジェクトによってインデックスに役立つようにポインターをラップします。  
  
```  
class type_index {  
public:  
    type_index(const type_info& tinfo);  
    const char *name() const;  
    size_t hash_code() const;  
    bool operator==(const type_info& right) const;  
    bool operator!=(const type_info& right) const;  
    bool operator<(const type_info& right) const;  
    bool operator<=(const type_info& right) const;  
    bool operator>(const type_info& right) const;  
    bool operator>=(const type_info& right) const;  
};  
```  
  
 コンストラクターは `&tinfo`に `ptr` を初期化します。  
  
 `name` が `ptr->name()` を返します。  
  
 `hash_code` は `ptr->hash_code().` を返します。  
  
 `operator==` が `*ptr == right.ptr` を返します。  
  
 `operator!=` が `!(*this == right)` を返します。  
  
 `operator<` が `*ptr->before(*right.ptr)` を返します。  
  
 `operator<=` は `!(right < *this).` を返します。  
  
 `operator>` の戻り `right < *this`。  
  
 `operator>=` が `!(*this < right)` を返します。  
  
## 参照  
 [ランタイム型情報](../Topic/Run-Time%20Type%20Information.md)   
 [\<typeindex\>](../standard-library/typeindex.md)