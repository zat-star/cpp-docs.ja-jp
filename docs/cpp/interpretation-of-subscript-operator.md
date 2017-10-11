---
title: "添字演算子の解釈 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- subscript operator [C++], interpretation of
- arrays [C++], subscripting
- interpreting subscript operators [C++]
- operators [C++], interpretation of subscript
ms.assetid: 8852ca18-9d5b-43f7-b8bd-abc89364fbf2
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 1a83ff6aea4380688d3b6298b93e04caab1dbb7f
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="interpretation-of-subscript-operator"></a>添字演算子の解釈
その他の演算子、添字演算子のように (****)、ユーザーによって再定義することができます。 添字演算子の既定の動作では、オーバーロードしない場合、次のメソッドを使用して配列名と添字を組み合わせます。  
  
 \*((*配列名*) + (*添字*))  
  
 ポインター型を含むすべての加算と同様に、スケーリングは型のサイズを調整するように自動的に実行されます。 したがって、結果の値は*添字*の原点からのバイト*配列名*以外の場合は代わりは、*添字*番目の要素の配列のです。 (この変換の詳細については、次を参照してください[加法演算子](../cpp/additive-operators-plus-and.md)。)。  
  
 同様に、多次元配列の場合は、次のメソッドを使用してアドレスが派生されます。  
  
 **((**   
 ***配列名*) + (**   
 ***添字*1***max*2 * \* max*3*...max に書き換え*n) ** + ***添字*2 * \* max*3*...max に書き換え*n)。   」を参照してください。 」を参照してください。 *+**添字*n))  
  
## <a name="see-also"></a>関連項目  
 [配列](../cpp/arrays-cpp.md)
