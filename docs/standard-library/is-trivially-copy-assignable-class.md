---
title: "is_trivially_copy_assignable クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::is_trivially_copy_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copy_assignable
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
caps.latest.revision: 12
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 0f8aad09e3ed083b9ffdd2199c9a9ab6462b840b
ms.contentlocale: ja-jp
ms.lasthandoff: 10/03/2017

---
# <a name="istriviallycopyassignable-class"></a>is_trivially_copy_assignable クラス
型が自明なコピー代入演算子を持つかどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```
template <class Ty>
struct is_trivially_copy_assignable;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 照会する型。  
  
## <a name="remarks"></a>コメント  
 型 `T` が自明なコピー代入演算子を持つクラスの場合、型述語のインスタンスは true を保持します。それ以外の場合は false を保持します。  
  
 クラス `T` の代入コンストラクターが自明となるのは、クラス `T` の代入コンストラクターが暗黙的に指定されており、クラス `T` に仮想関数と仮想基底が含まれず、クラス型の非静的データ メンバーすべてのクラスに自明な代入演算子が含まれており、かつクラスの型配列の非静的データ メンバーすべてでクラスに自明な代入演算子が含まれている場合です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [<type_traits>](../standard-library/type-traits.md)




