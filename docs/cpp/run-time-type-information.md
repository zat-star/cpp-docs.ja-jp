---
title: "実行時型情報 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: 'index-page '
dev_langs:
- C++
helpviewer_keywords:
- RTTI compiler option
- run-time type information
- run time, type checking
- type information, run-time type checking
- run-time checks, type checking
ms.assetid: becbd0e5-0439-4c61-854f-8a74f7160c54
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: ec36acfdba274a0eaf36c099da11f4462f2aad70
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="run-time-type-information"></a>ランタイム型情報
実行時型情報 (RTTI: Run-Time Type Information) は、プログラムの実行中にオブジェクトの型を決定するための機能です。 クラス ライブラリの多くのベンダーがこの機能を独自に実装していたことから、RTTI が C++ 言語に追加されましたが、 これによってライブラリの間に非互換性が発生しました。 したがって、実行時型情報を言語レベルでサポートする必要があります。  
  
 RTTI についてわかりやすく説明するため、ここでは対象をポインターに限定しています。 ただし、ここで説明する概念は参照にも適用されます。  
  
 C++ 言語には、実行時型情報を扱う 3 つの主要要素があります。  
  
-   [Dynamic_cast](../cpp/dynamic-cast-operator.md)演算子。  
  
     ポリモーフィック型を変換します。  
  
-   [Typeid](../cpp/typeid-operator.md)演算子。  
  
     オブジェクトの正確な型を特定します。  
  
-   [Type_info](../cpp/type-info-class.md)クラスです。  
  
     `typeid` 演算子によって返される型情報を格納します。  
  
## <a name="see-also"></a>関連項目  
 [キャスト](../cpp/casting.md)
