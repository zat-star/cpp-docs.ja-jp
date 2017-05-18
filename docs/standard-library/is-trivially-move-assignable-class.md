---
title: "is_trivially_move_assignable クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_trivially_move_assignable
- type_traits/std::is_trivially_move_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_move_assignable
ms.assetid: 374f7322-0706-4bc1-a1a5-4191d0315e28
caps.latest.revision: 11
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: b9d94304c6fbbd925ac3b670dc7665402b521dfd
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="istriviallymoveassignable-class"></a>is_trivially_move_assignable クラス
型が自明なムーブ代入演算子を持つかどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```
template <class Ty>
struct is_trivially_move_assignable;
```  
  
#### <a name="parameters"></a>パラメーター  
 `Ty`  
 照会する型。  
  
## <a name="remarks"></a>コメント  
 型 `Ty` が自明なムーブ代入演算子を持つクラスの場合、型述語のインスタンスは true を保持します。それ以外の場合は false を保持します。  
  
 次の条件が満たされる場合、クラス `Ty` のムーブ代入演算子は自明です。  
  
 暗黙的に指定されている  
  
 クラス `Ty` に仮想関数がない  
  
 クラス `Ty` に仮想基底がない  
  
 クラス型のすべての非静的データ メンバーのクラスに自明なムーブ代入演算子がある  
  
 クラスの型配列のすべての非静的データ メンバーのクラスに自明なムーブ代入演算子がある  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [<type_traits>](../standard-library/type-traits.md)




