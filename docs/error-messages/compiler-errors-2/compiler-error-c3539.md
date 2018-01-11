---
title: "コンパイラ エラー C3539 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3539
dev_langs: C++
helpviewer_keywords: C3539
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ccfa0b6ca6306de4d1454fa112bd413151450ae0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3539"></a>コンパイラ エラー C3539
'type': テンプレート引数が 'auto' を含む型にすることはできません  
  
 指定されたテンプレート引数の型は、使用量を含めることはできません、`auto`キーワード。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  使用するテンプレート引数を指定しない、`auto`キーワード。  
  
## <a name="example"></a>例  
 次の例では、C3539 が生成されます。  
  
```  
// C3539.cpp  
// Compile with /Zc:auto  
template<class T> class C{};  
int main()  
{  
   C<auto> c;   // C3539  
   return 0;  
}  
```  
  
## <a name="see-also"></a>参照  
 [auto キーワード](../../cpp/auto-keyword.md)