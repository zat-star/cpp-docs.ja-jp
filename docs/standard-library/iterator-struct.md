---
title: "iterator 構造体 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xutility/std::iterator
dev_langs:
- C++
helpviewer_keywords:
- iterator class
- iterator struct
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 274d472e3f3768a67a49ed6ca074f3a126bfd0fd
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="iterator-struct"></a>iterator 構造体
ユーザー定義の iterator クラスが **iterator_traits** で正しく動作することを確実にするために使用される空の基本構造体。  
  
## <a name="syntax"></a>構文  
```    
struct iterator {
   typedef Category iterator_category;
   typedef Type value_type;
   typedef Distance difference_type;
   typedef Distance distance_type;
   typedef Pointer pointer;
   typedef Reference reference;
   };  
```    
## <a name="remarks"></a>コメント  
 このテンプレート構造体は、すべての反復子の基本データ型として機能します。 これは、メンバーの型を定義します。  
  
- `iterator_category` (テンプレート パラメーター `Category` のシノニム)。  
  
- `value_type` (テンプレート パラメーター **Type** のシノニム)。  
  
- `difference_type` (テンプレート パラメーター `Distance` のシノニム)。  
  
- `distance_type` (テンプレート パラメーター `Distance` のシノニム)。  
  
- `pointer` (テンプレート パラメーター `Pointer` のシノニム)。  
  
- `reference` (テンプレート パラメーター `Reference` のシノニム)。  
  
 **ポインター**が const **Type** のオブジェクトを指しており、参照が const **Type** のオブジェクトを指定している場合でも、`value_type` を定数型にすることはできません。  
  
## <a name="example"></a>例  
 反復子の基底クラスの型の宣言方法や使用例については、「[iterator_traits](../standard-library/iterator-traits-struct.md)」を参照してください。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<iterator>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [\<iterator>](../standard-library/iterator.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)



