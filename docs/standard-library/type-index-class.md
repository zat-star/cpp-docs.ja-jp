---
title: "type_index クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: typeindex/std::type_index
dev_langs: C++
helpviewer_keywords: type_index class
ms.assetid: db366119-74cb-43e8-aacf-9679e561fa2f
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e27a626a7371c0358f05c49b33d0a9c1a019e72e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="typeindex-class"></a>type_index クラス
`type_index` クラスは、[type_info クラス](../cpp/type-info-class.md)へのポインターをラップして、このクラスのオブジェクトでインデックスを作成しやすくします。  
  
class type_index { public: type_index(const type_info& tinfo); const char *name() const; size_t hash_code() const; bool operator==(const type_info& right) const; bool operator!=(const type_info& right) const; bool operator<(const type_info& right) const; bool operator\<=(const type_info& right) const; bool operator>(const type_info& right) const; bool operator>=(const type_info& right) const; };  
  
 このコンストラクターは、`ptr` を `&tinfo`に初期化します。  
  
 `name` は、`ptr->name()` を返します。  
  
 `hash_code` の場合、`ptr->hash_code().` が返されます。  
  
 `operator==` は、`*ptr == right.ptr` を返します。  
  
 `operator!=` は、`!(*this == right)` を返します。  
  
 `operator<` は、`*ptr->before(*right.ptr)` を返します。  
  
 `operator<=` の場合、`!(right < *this).` が返されます。  
  
 `operator>` は、`right < *this` を返します。  
  
 `operator>=` は、`!(*this < right)` を返します。  
  
## <a name="see-also"></a>参照  
 [ランタイム型情報](../cpp/run-time-type-information.md)   
 [\<typeindex>](../standard-library/typeindex.md)



