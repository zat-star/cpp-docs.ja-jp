---
title: "コンパイラ エラー C2383 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2383
dev_langs: C++
helpviewer_keywords: C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7f89545b9428bd5e901c72d895b5c23317646c26
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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