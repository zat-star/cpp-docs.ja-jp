---
title: "unchecked_array_iterator クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- unchecked_array_iterator
- stdext::unchecked_array_iterator
dev_langs:
- C++
ms.assetid: 693b3b30-4e3a-465b-be06-409700bc50b1
caps.latest.revision: 15
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
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 850f1eced3ef5354a382d392c83b8180a18b4dfb
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="uncheckedarrayiterator-class"></a>unchecked_array_iterator クラス
`unchecked_array_iterator` クラスを使用すると、配列またはポインターをチェックを行わない反復子にラップできます。 チェックを行わないポインター警告をグローバルに抑制する代わりに、これらの警告を管理するのに適した方法として、このクラスを生のポインターまたは配列のラッパーとして使用します ([make_unchecked_array_iterator](../standard-library/iterator-functions.md#make_unchecked_array_iterator) 関数を使用)。 可能な場合は、このクラスのチェックを行うバージョンである [checked_array_iterator](../standard-library/checked-array-iterator-class.md) が推奨されます。  
  
> [!NOTE]
>  このクラスは、標準 C++ ライブラリの Microsoft 拡張機能です。 この関数を使用して実装されるコードは、Microsoft 拡張機能をサポートしない C++ 標準ビルド環境には移植できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class Iterator>  
class unchecked_array_iterator;
```  
  
## <a name="remarks"></a>コメント  
 このクラスは、[stdext](../standard-library/stdext-namespace.md) 名前空間で定義されます。  
  
 これは、[checked_array_iterator クラス](../standard-library/checked-array-iterator-class.md)のチェックを行わないバージョンであり、すべての同じオーバーロードおよびメンバーをサポートします。 チェックを行う反復子の機能の詳細とコード サンプルについては、「[チェックを行う反復子](../standard-library/checked-iterators.md)」を参照してください。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<iterator>  
  
 **名前空間:** stdext  
  
## <a name="see-also"></a>関連項目  
 [\<iterator>](../standard-library/iterator.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)




