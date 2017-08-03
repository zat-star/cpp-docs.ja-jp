---
title: "ポインター型との間の変換 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- pointers, converting
- conversions, pointer
- type casts, involving pointers
- void pointers
ms.assetid: 3facc56f-06d3-4570-b1a2-7d4927b83086
caps.latest.revision: 7
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 0dc5c5572e6bd8193fed8d211867246643e5f13b
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="conversions-to-and-from-pointer-types"></a>Conversions to and from Pointer Types (ポインター型との間の変換)
ある型の値へのポインターは、別の型へのポインターに変換できます。 ただし、結果は、各型のストレージのアラインメント要件とサイズの違いにより、未定義になることがあります。 オブジェクトへのポインターは、型のストレージ アラインメントの厳密さが同じか、それ以下のオブジェクトへのポインターに変更でき、変更なしで元に戻すことができます。  
  
 `void` へのポインターは、情報の制限や損失なしに任意の型へのポインターとの間で変換できます。 結果が元の型に戻される場合、元のポインターが復元されます。  
  
 ポインターが、型は同じでも修飾子が異なるか、修飾子の追加された別のポインターに変換される場合、新しいポインターは、新しい修飾子の制限を除いて、古いポインターと同じになります。  
  
 ポインター値は、整数値に変換することもできます。 変換パスは、次の規則に従い、ポインターのサイズと整数型のサイズによって決まります。  
  
-   ポインターのサイズが整数型のサイズ以上である場合、ポインターは、浮動小数点型に変換できない点を除けば、変換で符号なしの値と同様の動作をします。  
  
-   ポインターが整数型より小さい場合、ポインターは最初に整数型と同じサイズのポインターに変換されてから、整数型に変換されます。  
  
 逆に、整数型は、次の規則に従ってポインター型に変換することができます。  
  
-   整数型がポインター型と同じサイズである場合、変換では整数値が単にポインター (符号なし整数) として処理されます。  
  
-   整数型のサイズがポインター型のサイズと異なる場合、整数型は最初に「[符号付き整数型からの変換](../c-language/conversions-from-signed-integral-types.md)」と「[符号なし整数型からの変換](../c-language/conversions-from-unsigned-integral-types.md)」の表で指定された変換パスを使用して、ポインターのサイズに変換されます。 その後、これがポインター値として扱われます。  
  
 値 0 の整数定数式、または **void \*** 型にキャストされた整数定数式は、型キャスト、代入、または任意の型のポインターとの比較によって変換できます。 これによって、同じ型の別の null ポインターと等しい null ポインターが生成されます。しかし、この null ポインターは、関数またはオブジェクトへのポインターとは等しくありません。 定数 0 以外の整数はポインター型に変換することができますが、結果は移植できません。  
  
## <a name="see-also"></a>関連項目  
 [代入の変換](../c-language/assignment-conversions.md)
