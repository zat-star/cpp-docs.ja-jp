---
title: "conditional クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::conditional
dev_langs: C++
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0a106f2361dccbeb33c662c88edd40223a604639
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [<type_traits>](../standard-library/type-traits.md)



