---
title: "is_final クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_final
dev_langs: C++
helpviewer_keywords: is_final
ms.assetid: 9dbad82f-6685-4909-94e8-98e4a93994b9
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1c8385e3c229c9740bae4d59b3076b189cb1842d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="isfinal-class"></a>is_final クラス
型が `final` でマークされたクラス型であるかどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>
struct is_final;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 照会する型。  
  
## <a name="remarks"></a>コメント  
 型 `T` が `final` でマークされたクラス型である場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。 `T` がクラス型の場合、完全な型である必要があります。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [<type_traits>](../standard-library/type-traits.md)   
 [final 指定子](../cpp/final-specifier.md)



