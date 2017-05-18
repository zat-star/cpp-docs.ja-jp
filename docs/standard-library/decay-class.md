---
title: "decay クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- decay
- type_traits/std::decay
dev_langs:
- C++
helpviewer_keywords:
- decay class
ms.assetid: 96baa2fd-c8e0-49af-be91-ba375ba7f9dc
caps.latest.revision: 20
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
ms.openlocfilehash: cb75f00c4f7dfc46122c8e69e5572de1ec23f8ed
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="decay-class"></a>decay クラス
値で渡されように型を生成します。 型を非参照、非定数、非揮発性にします。または、関数からの型または配列型へのポインターを作成します。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>
struct decay;

template <class T>  
using decay_t = typename decay<T>::type;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 変更する型。  
  
## <a name="remarks"></a>コメント  
 型が引数として値で渡されたかのように結果の型を生成するには、decay テンプレートを使います。 テンプレート クラスのメンバー typedef `type` は、次の段階で定義された修飾型を保持します。  
  
-   型 `U` が `remove_reference<T>::type` として定義されます。  
  
-   `is_array<U>::value` が true の場合、修飾型 `type` は `remove_extent<U>::type *` になります。  
  
-   `is_function<U>::value` が true の場合、修飾型 `type` は `add_pointer<U>::type` になります。  
  
-   それ以外の場合、修飾型 `type` は `remove_cv<U>::type` になります。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [<type_traits>](../standard-library/type-traits.md)




