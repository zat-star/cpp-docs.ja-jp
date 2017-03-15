---
title: "コンパイラ エラー C3282 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3282
dev_langs:
- C++
helpviewer_keywords:
- C3282
ms.assetid: bac2ac89-c360-4c24-bb81-c20c62ece9ba
caps.latest.revision: 5
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
ms.openlocfilehash: 351d42b7fe7a8f94088d452dfb53c233aaabf80a
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3282"></a>コンパイラ エラー C3282
ジェネリック パラメーターのリストにのみ表示されます管理または WinRTclasses、構造体、または関数。  
  
 ジェネリック パラメーター リストが正しく使用されていません。  詳細については、次を参照してください。[ジェネリック](../../windows/generics-cpp-component-extensions.md)します。  
  
## <a name="example"></a>例  
 次の例では C3282 を生成し、その修正方法を示しています。  
  
```  
// C3282.cpp  
// compile with: /clr /c  
generic <typename T> int x;   // C3282  
  
ref struct GC0 {  
   generic <typename T> int x;   // C3282  
};  
  
// OK  
generic <typename T>  
ref class M {};  
```
