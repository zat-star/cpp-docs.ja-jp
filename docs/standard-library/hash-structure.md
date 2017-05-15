---
title: "hash 構造体 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- typeindex/std::hash
dev_langs:
- C++
ms.assetid: e5a41202-ef3b-45d0-b3a7-4c2dbdc0487a
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 7c9acac4b68f5d1abfd5cb68e1d8742eb20ff6b9
ms.contentlocale: ja-jp
ms.lasthandoff: 04/19/2017

---
# <a name="hash-structure"></a>hash 構造体
テンプレート クラスは `val.hash_code()` を返すようにメソッドを定義します。 メソッドは、ハッシュ関数を定義します。これは [type_index](../standard-library/type-index-class.md) 型の値をインデックス値の分布にマッピングするために使用されます。  
  
## <a name="syntax"></a>構文  
  
```
template <>
struct hash<type_index>  
: public unary_function<type_index, size_t>
 { // hashes a typeinfo object
    size_t operator()(type_index val) const;

 };
```  
  
## <a name="see-also"></a>関連項目  
 [\<typeindex>](../standard-library/typeindex.md)




