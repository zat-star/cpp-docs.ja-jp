---
title: "コンパイラの警告 (レベル 1 および 4) C4112 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4112
dev_langs:
- C++
helpviewer_keywords:
- C4112
ms.assetid: aff64897-bb79-4a67-9b6f-902c6d44f3dc
caps.latest.revision: 10
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
ms.openlocfilehash: 8a2c08b6c4bc8e1f2cf20e0236f76b5cd3020de4
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-levels-1-and-4-c4112"></a>コンパイラの警告 (レベル 1 および 4) C4112
\#行 1 と番号の間の整数が必要です。  
  
 [#Line](../../preprocessor/hash-line-directive-c-cpp.md)ディレクティブが許容範囲外である整数パラメーターを指定します。  
  
 指定したパラメーターが 1 より小さい場合、行カウンターは 1 にリセットされます。 指定したパラメーターが、コンパイラで定義された制限値である *number*より大きい場合、行カウンターは変更されません。 これは、ANSI 互換レベル 1 の警告 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) と Microsoft の拡張機能のレベル 4 の警告 ([/Ze](../../build/reference/za-ze-disable-language-extensions.md))。  
  
 次の例では C4112 が生成されます。  
  
```  
// C4112.cpp  
// compile with: /W4  
#line 0   // C4112, value must be between 1 and number  
  
int main() {  
}  
```
