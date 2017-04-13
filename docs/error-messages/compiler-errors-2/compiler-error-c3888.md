---
title: "コンパイラ エラー C3888 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3888
dev_langs:
- C++
helpviewer_keywords:
- C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 4b85385c97f5873c1b370cd72f0866439263f787
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3888"></a>コンパイラ エラー C3888
'name': このリテラル データ メンバーと関連付けられた const 式は C++/CLI でサポートされていません  
  
 *名前*で宣言されたデータ メンバー、[リテラル](../../windows/literal-cpp-component-extensions.md)キーワードは、コンパイラがサポートしていません値で初期化されます。 コンパイラは、定数の整数型、列挙型、または文字列型のみをサポートしています。 **C3888** エラーの考えられる原因は、データ メンバーがバイト配列で初期化されていることです。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  宣言されたリテラル データ メンバーがサポートされている型であることを確認します。  
  
## <a name="see-also"></a>関連項目  
 [リテラル](../../windows/literal-cpp-component-extensions.md)
