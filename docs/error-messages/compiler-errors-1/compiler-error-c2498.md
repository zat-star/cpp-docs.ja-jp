---
title: "コンパイラ エラー C2498 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2498
dev_langs: C++
helpviewer_keywords: C2498
ms.assetid: 0839f12c-aaa4-4a02-bb33-7f072715dd14
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0324ebd2cb27e1d48221b72bec2caaea5c4fc698
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2498"></a>コンパイラ エラー C2498
'function': 'novtable' は、クラス宣言または定義にのみ適用できます  
  
 使用してこのエラーは発生する`__declspec(novtable)`関数を使用します。  
  
## <a name="example"></a>例  
 次の例では、C2498 が生成されます。  
  
```  
// C2498.cpp  
// compile with: /c  
void __declspec(novtable) f() {}   // C2498  
class __declspec(novtable) A {};   // OK  
```