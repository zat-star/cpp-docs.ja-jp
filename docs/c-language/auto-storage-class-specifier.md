---
title: "auto ストレージ クラス指定子 | Microsoft Docs"
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
ms.assetid: 8e73f57e-aa92-4e41-91ea-5c8ad2a2b332
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: a5c470eb63060b92e10ae3e31c2d6ccb6df22165
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="auto-storage-class-specifier"></a>auto ストレージ クラス指定子
**auto** ストレージ クラス指定子は、自動変数 (ローカルな有効期間を持つ変数) を宣言します。 **auto** 変数は、宣言されたブロック内でのみ表示されます。 **auto** 変数の宣言には、「[初期化](../c-language/initialization.md)」に説明されているように、初期化子を含めることができます。 **auto** ストレージ クラスと一緒に指定された変数は自動的に初期化されないため、宣言するときに明示的に初期化するか、ブロック内のステートメントの初期値を代入する必要があります。 初期化されていない **auto** 変数の値は未定義です (**auto** または **register** ストレージ クラスのローカル変数は、初期化子が与えられた場合にスコープに入るたびに初期化されます)。  
  
 内部 **static** 変数 (ローカルまたはブロック スコープを持つ静的変数) は外部項目または **static** 項目のアドレスで初期化できますが、**auto** 項目のアドレスが定数ではないため、別の **auto** 項目のアドレスではできません。  
  
## <a name="see-also"></a>関連項目  
 [auto キーワード](../cpp/auto-keyword.md)
