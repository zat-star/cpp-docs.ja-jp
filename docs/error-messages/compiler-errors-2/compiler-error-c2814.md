---
title: "コンパイラ エラー C2814 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2814
dev_langs:
- C++
helpviewer_keywords:
- C2814
ms.assetid: 7d165136-a08b-4497-a76d-60a21bb19404
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bf44ef54748b214f54f88192d14ba3accbb529f8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2814"></a>コンパイラ エラー C2814
'member' : ネイティブ型をマネージ型または WinRT 型の 'type' の中に入れ子にすることはできません  
  
## <a name="example"></a>例  
 ネイティブ型を CLR 型または WinRT 型の中に入れ子にすることはできません。 次の例では、C2814 を生成し、その修正方法を示しています。  
  
```  
// C2814.cpp  
// compile with: /clr /c  
ref class A {  
   class B {};   // C2814  
   ref class C {};   // OK  
};  
```  
