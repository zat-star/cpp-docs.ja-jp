---
title: "hash 構造体 (C++ 標準ライブラリ) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- thread/std::hash
dev_langs:
- C++
ms.assetid: 4a8bf5bc-4334-4070-936b-98585f8a073b
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.openlocfilehash: 1af8dc2f8fef535883088c413827a98a35539980
ms.contentlocale: ja-jp
ms.lasthandoff: 04/19/2017

---
# <a name="hash-structure-c-standard-library"></a>hash 構造体 (C++ 標準ライブラリ)
`Val` によって一意に決定される値を返すメンバー関数を定義します。 メンバー関数は、`thread::id` 型の値をインデックス値の分布にマッピングするために適した[ハッシュ](../standard-library/hash-class.md)関数を定義します。  
  
## <a name="syntax"></a>構文  
  
```  
template <>  
struct hash<thread::id> :   
    public unary_function<thread::id, size_t>  
{  
    size_t operator()(thread::id Val) const;

 
};  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<スレッド >  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<スレッド>](../standard-library/thread.md)   
 [unary_function 構造体](../standard-library/unary-function-struct.md)

