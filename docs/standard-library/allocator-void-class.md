---
title: "allocator&lt;void&gt; クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
dev_langs:
- C++
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
caps.latest.revision: 18
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: ef8af7f3ea22529eed77e2259add8fcde21fbd57
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="allocatorltvoidgt-class"></a>allocator&lt;void&gt; クラス
`void` 型へのテンプレート クラスのアロケーターを特殊化し、このコンテキストで意味を持つ型を定義します。  
  
## <a name="syntax"></a>構文  
  
```
template <>
class allocator<void> {
    typedef void *pointer;
    typedef const void *const_pointer;
    typedef void value_type;
    template <class Other>
    struct rebind;
    allocator();
    allocator(const allocator<void>&);

    template <class Other>
    allocator(const allocator<Other>&);

    template <class Other>
    allocator<void>& operator=(const allocator<Other>&);
};
```  
  
## <a name="remarks"></a>コメント  
 このクラスは、*void* 型のテンプレート クラス [allocator](../standard-library/allocator-class.md) を明示的に特殊化します。 コンストラクターと代入演算子の動作は、同じテンプレート クラスの動作と同じですが、次の型のみを定義します。  
  
- [const_pointer](../standard-library/allocator-class.md#const_pointer)  
  
- [pointer](../standard-library/allocator-class.md#pointer)  
  
- [value_type](../standard-library/allocator-class.md#value_type)  
  
- [rebind](../standard-library/allocator-class.md#rebind)、入れ子になったテンプレート クラス  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<memory>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)




