---
title: "コンパイラ エラー C2657 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2657
dev_langs: C++
helpviewer_keywords: C2657
ms.assetid: f7cf29a9-684a-4605-9469-ecfee9ba4b03
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 709adacf558341dc31a48defd0ca7da5e08879ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2657"></a>コンパイラ エラー C2657
' クラス:: *' ステートメントの先頭が見つかりました (を忘れましたか種類を指定しますか?)  
  
 メンバーへのポインターの識別子を持つ行を開始しました。  
  
 このエラーは、メンバーへのポインターの宣言で型指定子がありませんが発生することができます。  
  
 次の例では、C2657 が生成されます。  
  
```  
// C2657.cpp  
class C {};  
int main() {  
   C::* pmc1;        // C2657  
   int C::* pmc2;   // OK  
}  
```