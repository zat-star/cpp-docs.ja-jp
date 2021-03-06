---
title: "コンパイラの警告 (レベル 1) C4526 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4526
dev_langs:
- C++
helpviewer_keywords:
- C4526
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a74d7d2e2c745a4c8e29736c1e3a7fc38892d5f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4526"></a>コンパイラの警告 (レベル 1) C4526
'function': 静的メンバー関数は仮想関数をオーバーライドできません ' 仮想 function'override が無視されます、仮想関数を非表示には  
  
 静的メンバー関数では、仮想と静的メンバー関数は、仮想関数をオーバーライドする条件を満たしています。  
  
 次のコードには、C4526 が生成されます。  
  
```  
// C4526.cpp  
// compile with: /W1 /c  
// C4526 expected  
struct myStruct1 {  
   virtual void __stdcall func( int ) = 0;  
};  
  
struct myStruct2: public myStruct1 {  
   static void __stdcall func( int );  
};  
```  
  
 考えられる修正方法を次に示します。  
  
-   関数が基底クラスの仮想関数をオーバーライドするためのもので、静的な指定子を削除します。  
  
-   関数は、静的メンバー関数を意図した場合、基底クラスの仮想関数とも競合しないように変更します。