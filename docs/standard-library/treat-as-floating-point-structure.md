---
title: "treat_as_floating_point 構造体 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::chrono::treat_as_floating_point
dev_langs:
- C++
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
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
ms.openlocfilehash: 9d9e6b0b281fb97475b0c23acb4bf7d0fc391a52
ms.contentlocale: ja-jp
ms.lasthandoff: 04/19/2017

---
# <a name="treatasfloatingpoint-structure"></a>treat_as_floating_point 構造体
`Rep` を浮動小数点型として扱うことができるかどうかを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Rep>  
struct treat_as_floating_point : is_floating_point<Rep>;  
```  
  
## <a name="remarks"></a>コメント  
 `Rep` は、特殊化 `treat_as_floating_point<Rep>` が [true_type](../standard-library/type-traits-typedefs.md#true_type) から派生したときにのみ浮動小数点型として処理できます。 このテンプレート クラスは、ユーザー定義型に特殊化することができます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<chrono >  
  
 **名前空間:** std::chrono  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)


