---
title: "is_literal_type クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::is_literal_type
dev_langs:
- C++
helpviewer_keywords:
- is_literal_type
ms.assetid: a03a4ebb-ee66-48d6-91bb-41cf72b2401f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 09a1531458df692be2b78a97a1723366f912d087
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="isliteraltype-class"></a>is_literal_type クラス
型を `constexpr` 変数として使用できるか、または `constexpr` 関数で構築、使用、または返すことができるかをテストします。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
struct is_literal_type;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 照会する型。  
  
## <a name="remarks"></a>コメント  
 型 `T` が*リテラル型*である場合、型の述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。 リテラル型は、`void`、スカラー型、参照型、リテラル型の配列、またはリテラル クラス型のいずれかです。 リテラル クラス型は、単純なデストラクターを持つクラス型であり、集計の型であるか、または少なくとも 1 つのムーブ禁止、コピー禁止の `constexpr` コンストラクターを持ち、そのすべての基底クラスと非静的データ メンバーは、非 volatile のリテラル型です。 リテラルの型は常にリテラル型ですが、リテラル型の概念は、コンパイラがコンパイル時に `constexpr` として評価できるあらゆるものを含みます。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [<type_traits>](../standard-library/type-traits.md)



