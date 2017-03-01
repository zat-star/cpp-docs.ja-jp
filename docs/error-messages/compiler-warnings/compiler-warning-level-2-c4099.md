---
title: "コンパイラの警告 (レベル 2) C4099 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4099
dev_langs:
- C++
helpviewer_keywords:
- C4099
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
caps.latest.revision: 9
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
ms.openlocfilehash: 855b31903ba36f6c1ab3030e91354175441451a9
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-2-c4099"></a>コンパイラの警告 (レベル 2) C4099
'identifier': 'objecttype1' '%objecttype2' を使用しての説明は以上を使用して&1; つ目の種類名  
  
 クラスと構造体として宣言されたオブジェクトが定義されているかをクラスとして宣言されたオブジェクトが、構造体として定義されています。 コンパイラは、定義で指定された型を使用します。  
  
## <a name="example"></a>例  
 次の例では、C4099 を生成します。  
  
```  
// C4099.cpp  
// compile with: /W2 /c  
struct A;  
class A {};   // C4099, use different identifer or use same object type  
```
