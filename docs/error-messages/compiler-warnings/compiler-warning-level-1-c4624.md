---
title: "コンパイラの警告 (レベル 1) C4624 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4624
dev_langs:
- C++
helpviewer_keywords:
- C4624
ms.assetid: 14f61769-d92e-482b-9515-debd87b30a66
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a3acf93e1609b6a53f6654afb83a51bad49da84
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4624"></a>コンパイラの警告 (レベル 1) C4624
'derived class' : 基底クラスのデストラクターへのアクセスまたはその削除ができないため、デストラクターを暗黙的に削除済みとして定義しました  
  
 デストラクターは基底クラスでアクセスできないか削除されているため、派生クラスでは生成されません。 スタックにこの型のオブジェクトを作成しようとすると、コンパイル エラーが発生します。  
  
 次の例では、C4624 を生成し、その修正方法を示しています。  
  
```  
// C4624.cpp  
// compile with: /W1 /c  
class B {  
// Uncomment the following line to fix.  
// public:  
   ~B();  
};  
  
class D : public B {};   // C4624 B's destructor not public  
```