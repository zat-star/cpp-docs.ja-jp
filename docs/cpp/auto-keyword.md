---
title: "auto キーワード |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- auto
- auto_cpp
dev_langs:
- C++
helpviewer_keywords:
- automatic storage class, auto keyword
- auto keyword
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
caps.latest.revision: 14
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
ms.openlocfilehash: 0413fd47b486cf1613b7c249b93e6a3507a5577c
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="auto-keyword"></a>auto キーワード
`auto` キーワードは宣言指定子です。 ただし、C++ 標準ではこのキーワードの元の意味と変更後の意味が定義されます。 Visual C 2010 では、前に、`auto`キーワードで宣言内の変数、*自動*ストレージ クラスです。 つまり、ローカルの有効期間を持つ変数です。 Visual C 2010、始まる、`auto`キーワードは、その宣言で初期化式から推測される型の変数を宣言します。 [/Zc:auto &#91;-&#93;](../build/reference/zc-auto-deduce-variable-type.md)コンパイラ オプションの意味を制御する、`auto`キーワード。  
  
## <a name="syntax"></a>構文  
  
```cpp  
auto declarator ;  
auto declarator initializer;  
```  
  
## <a name="remarks"></a>コメント  
 `auto` キーワードの定義は、C++ プログラミング言語では変化しますが、C プログラミング言語では変化しません。  
  
 ここからのトピックでは、`auto` キーワードと、対応するコンパイラ オプションについて説明します。  
  
-   [自動](../cpp/auto-cpp.md)の新しい定義の説明、`auto`キーワード。  
  
  
-   [/Zc:auto (変数の型の推測)](../build/reference/zc-auto-deduce-variable-type.md)のどの定義をコンパイラに指示するコンパイラ オプションについて説明します、`auto`キーワードを使用します。  
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)
