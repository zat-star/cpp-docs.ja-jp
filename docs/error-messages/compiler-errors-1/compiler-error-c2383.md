---
title: "コンパイラ エラー C2383 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2383
dev_langs:
- C++
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
caps.latest.revision: 11
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
ms.openlocfilehash: faa2aa2c29ea34009f0812a3796d450a6877ca48
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2383"></a>コンパイラ エラー C2383
'*シンボル*': 既定の引数はこのシンボルでは許可されていません  
  
 C++ コンパイラでは、関数へのポインターに関する既定の引数は許可されません。  
  
 このコードは、Visual Studio 2005 より前に、のバージョンの Visual C コンパイラによって受け入れられましたが、エラーになりました。 Visual C のすべてのバージョンで動作するコードでは、関数へのポインター引数に既定値は割り当てないでください。  
  
## <a name="example"></a>例  
 次の例では、C2383 を生成し、考えられる解決方法を示しています。  
  
```cpp  
// C2383.cpp  
// compile with: /c   
void (*pf)(int = 0);   // C2383  
void (*pf)(int);   // OK  
```
