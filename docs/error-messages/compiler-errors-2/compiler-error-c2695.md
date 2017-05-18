---
title: "コンパイラ エラー C2695 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2695
dev_langs:
- C++
helpviewer_keywords:
- C2695
ms.assetid: 3f6f2091-c38b-40ea-ab6c-f1846f5702d7
caps.latest.revision: 7
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 48599871b90a3ff74d97dcaff0ad19ea319771da
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2695"></a>コンパイラ エラー C2695
'function1': 仮想関数をオーバーライドする唯一の相違点 'function2' の呼び出し規約  
  
 派生クラスで関数のシグネチャは、基本クラスの関数をオーバーライドし、呼び出し規約を変更できません。  
  
 次の例では、c2695 エラーが生成されます。  
  
```  
// C2695.cpp  
class C {  
   virtual void __fastcall func();  
};  
  
class D : public C {  
   virtual void __clrcall func();   // C2695  
};  
```
