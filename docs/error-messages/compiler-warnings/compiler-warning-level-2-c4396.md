---
title: "コンパイラの警告 (レベル 2) C4396 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4396
dev_langs:
- C++
helpviewer_keywords:
- C4396
ms.assetid: 7cd6b283-db17-4574-b299-03e0b913ad70
caps.latest.revision: 11
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 84f0628de933344eb23dc6325679abdcd3699c3a
ms.openlocfilehash: 8e0538cc5a1ec9279c4d84cb9e23e0d6fabfd77e
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-2-c4396"></a>コンパイラの警告 (レベル 2) C4396
"name": フレンド宣言が関数の特殊化を参照している場合、テンプレートのインライン指定子を使用できません  
  
 関数テンプレートの特殊化は、いずれかを指定できない、[インライン](../../cpp/inline-functions-cpp.md)指定子。 コンパイラは、警告 C4396 を発行し、インライン指定子を無視します。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   フレンド関数の宣言から `inline`、 `__inline`、 `__forceinline` の指定子を削除します。  
  
## <a name="example"></a>例  
 次のコード例では、 `inline` 指定子のある無効なフレンド関数の宣言を示します。  
  
```  
// C4396.cpp  
// compile with: /W2 /c  
  
class X;   
template<class T> void Func(T t, int i);  
  
class X {  
    friend inline void Func<char>(char t, int i);  //C4396  
// try the following line instead  
//    friend void Func<char>(char t, int i);   
    int i;  
};  
```
