---
title: "コンパイラ エラー C2084 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2084
dev_langs:
- C++
helpviewer_keywords:
- C2084
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
caps.latest.revision: 7
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 653dc7a4a5d330efc89942fbe4ddd07bff81f770
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2084"></a>コンパイラ エラー C2084
関数 '*関数*'、本文には既に  
  
 関数は既に定義されています。  
  
 バージョンの Visual Studio の 2002 年前に Visual C  
  
-   コンパイラは、追加の定義を使用することは決して同じの実際の型に解決される複数のテンプレートの特殊化を受け入れるは。 コンパイラは、今すぐこれら複数の定義を検出します。  
  
-   `__int32`および`int`別個の型として扱われました。 コンパイラはこれで扱います`__int32`のシノニムとして`int`です。 これは、コンパイラでは、両方の関数がオーバー ロードする場合、複数の定義がによって検出されたことを意味`__int32`と`int`エラーとなります。  
  
## <a name="example"></a>例  
 次の例では、C2084 が生成されます。  
  
```cpp  
// C2084.cpp  
void Func(int);  
void Func(int) {}   // define function  
void Func(int) {}   // C2084 second definition  
```  
  
このエラーを解決するには、重複する定義を削除します。  
  
```  
// C2084b.cpp  
// compile with: /c  
void Func(int);  
void Func(int) {}  
```
