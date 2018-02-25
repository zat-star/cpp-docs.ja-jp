---
title: "is_trivially_copy_constructible クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_copy_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 438a5e2aa262eefaa7d2c6cfcfe5786051646b87
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
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
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [<type_traits>](../standard-library/type-traits.md)



