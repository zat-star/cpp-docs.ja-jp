---
title: "is_trivially_copy_constructible クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_trivially_copy_constructible
- type_traits/std::is_trivially_copy_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
caps.latest.revision: 24
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
translationtype: Machine Translation
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: a9f40518942be5632f13dee3865b603f04cbca84
ms.lasthandoff: 02/24/2017

---
# <a name="istriviallycopyconstructible-class"></a>is_trivially_copy_constructible クラス
型に自明なコピー コンストラクターが含まれるかどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>
struct is_trivially_copy_constructible;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 照会する型。  
  
## <a name="remarks"></a>コメント  
 型 `T` が自明なコピー コンストラクターを持つクラスである場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。  
  
 クラス `T` のコピー コンストラクターが自明となるのは、このコピー コンストラクターが暗黙的に宣言されており、クラス `T` に仮想関数も仮想基底も含まれず、クラス `T` のすべての直接基底が自明なコピー コンストラクターを持ち、クラス型の非静的データ メンバーすべてのクラスが自明なコピー コンストラクターを持ち、かつクラスの型配列の非静的データ メンバーすべてでクラスが自明なコピー コンストラクターを持つ場合です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [<type_traits>](../standard-library/type-traits.md)




