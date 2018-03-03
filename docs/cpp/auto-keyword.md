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
- auto_cpp
dev_langs:
- C++
helpviewer_keywords:
- automatic storage class [C++], auto keyword
- auto keyword [C++]
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3508217e7dc333543fa2dbff9cf0643d6faff060
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
  
## <a name="see-also"></a>参照  
 [キーワード](../cpp/keywords-cpp.md)