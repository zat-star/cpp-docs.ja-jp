---
title: "is_trivially_default_constructible クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_default_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_default_constructible
ms.assetid: 653ecd73-909f-4dd8-b95a-d1164d1c2da4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dd0b63b1f088eadf2ba2a253083d0f2878c2b751
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="istriviallydefaultconstructible-class"></a>is_trivially_default_constructible クラス
型に自明な既定コンストラクターが存在するかどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```
template <class Ty>
struct is_trivially_default_constructible;
```  
  
#### <a name="parameters"></a>パラメーター  
 `Ty`  
 照会する型。  
  
## <a name="remarks"></a>コメント  
 型 `Ty` が自明なコンストラクターを持つクラスである場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。  
  
 クラス `Ty` の既定コンストラクターが自明であるのは、以下の場合です。  
  
-   暗黙的に宣言された既定のコンス トラクターである  
  
-   クラス `Ty` に仮想関数がない  
  
-   クラス `Ty` に仮想基底がない  
  
-   クラス `Ty` のすべての直接基底に自明なコンストラクターがある  
  
-   クラス型のすべての非静的データ メンバーのクラスに自明なコンストラクターがある  
  
-   クラスの型配列のすべての非静的データ メンバーのクラスに自明なコンストラクターがある  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [<type_traits>](../standard-library/type-traits.md)



