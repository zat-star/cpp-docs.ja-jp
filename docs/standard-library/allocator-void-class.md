---
title: "allocator&lt;void&gt; クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
dev_langs: C++
helpviewer_keywords: allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9e6a457323d99ec36c019e099ebcd5fef4ab2f0b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<memory>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)



