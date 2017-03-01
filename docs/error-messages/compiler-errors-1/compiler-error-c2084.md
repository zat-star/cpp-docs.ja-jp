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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 0ecd2db7dc5ac207d8257b725be83cdce983d5c8
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2084"></a>コンパイラ エラー C2084
関数 'function' は既に本体  
  
 関数は既に定義されています。  
  
 Visual C の以前のバージョン  
  
-   コンパイラは、追加の定義を使用することは決して同じ実際の型に解決される複数のテンプレートの特殊化を受け入れるとします。 コンパイラがこれらの複数の定義を検出するようになりました  
  
-   _ _int32 と int は、別個の型として扱われました。 コンパイラはこれで扱います\__int32 は int のシノニムとして つまり、関数が両方のオーバー ロードされた場合に、コンパイラで複数の定義が検出する\__int32 と int とエラーを指定します。  
  
 次の例では、c2084 エラーが生成されます。  
  
```  
// C2084.cpp  
void Func(int);  
void Func(int) {}   // define function  
void Func(int) {}   // C2084 second definition  
```  
  
 考えられる解決策:  
  
```  
// C2084b.cpp  
// compile with: /c  
void Func(int);  
void Func(int) {}  
```
