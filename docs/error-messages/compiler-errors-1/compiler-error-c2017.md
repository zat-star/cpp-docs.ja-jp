---
title: "コンパイラ エラー C2017 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2017
dev_langs: C++
helpviewer_keywords: C2017
ms.assetid: 1083eed9-9906-4a97-883c-54e52d7e82cd
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5d978ebf635f5d042d2cd454581625033c0f306e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2017"></a>コンパイラ エラー C2017
無効なエスケープ シーケンス  
  
 \T などのエスケープ シーケンスが文字または文字列の外部で出現定数。  
  
 次の例では、C2017 が生成されます。  
  
```  
// C2017.cpp  
int main() {  
   char test1='a'\n;   // C2017  
   char test2='a\n';   // ok  
}  
```  
  
 C2017 は、エスケープ シーケンスを含む文字列を文字列化演算子を使用する場合に発生することができます。  
  
 次の例では、C2017 が生成されます。  
  
```  
// C2017b.cpp  
#define TestDfn(x) AfxMessageBox(#x)  
TestDfn(CString("\\") + CString(".h\"\n\n"));   // C2017  
```