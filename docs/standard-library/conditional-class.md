---
title: "conditional クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::conditional
dev_langs:
- C++
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
caps.latest.revision: 22
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 2c764bfc42d633a3036f2e567078b9ea39feea8b
ms.contentlocale: ja-jp
ms.lasthandoff: 10/03/2017

---
# <a name="conditional-class"></a>conditional クラス
指定された条件に基づいて、2 つの型のいずれかを選択します。  
  
## <a name="syntax"></a>構文  
  
```
template <bool B, class T1, class T2>  
struct conditional;

template <bool _Test, class _T1, class _T2>  
using conditional_t = typename conditional<_Test, _T1, _T2>::type;
```  
  
#### <a name="parameters"></a>パラメーター  
 `B`  
 選択される型を決定する値。  
  
 `T1`  
 B が true の場合の型の結果。  
  
 `T2`  
 B が false の場合の型の結果。  
  
## <a name="remarks"></a>コメント  
 テンプレート メンバー typedef `conditional<B, T1, T2>::type` は、 `T1` が `B` に評価されるときは `true`として、 `T2` が `B` に評価されるときは `false`として評価されます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [<type_traits>](../standard-library/type-traits.md)




