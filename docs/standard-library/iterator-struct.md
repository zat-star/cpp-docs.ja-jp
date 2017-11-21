---
title: "iterator 構造体 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xutility/std::iterator
dev_langs: C++
helpviewer_keywords:
- iterator class
- iterator struct
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: abcafb8f94265d14a609481a187dcc53267718d3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<iterator>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [\<iterator>](../standard-library/iterator.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)



