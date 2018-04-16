---
title: "コンパイラの警告 (レベル 1) C4807 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4807
dev_langs:
- C++
helpviewer_keywords:
- C4807
ms.assetid: 089c9f87-fd81-402e-9826-66a8ef1ef1fe
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: af604a1a045b9dbef7b3c27f9c7aabd0040aa318
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4807"></a>コンパイラの警告 (レベル 1) C4807
'operation': 'type' 型と 'type' 型の符号付きビットフィールドの混用は安全ではありません。  
  
 この警告は、1 ビットの符号付きビットフィールドと `bool` 変数を比較すると、生成されます。 1 ビットの符号付きビットフィールドには、値 -1 または 0 のみを含めることがでるため、 `bool`と比較するのは危険です。 `bool` と 1 ビットの符号なしビットフィールドは `bool` を同じであり、0 または 1 のみを保持できるため、これらを混用しても警告は生成されません。  
  
## <a name="example"></a>例  
 次の例では C4807 が生成されます。  
  
```  
// C4807.cpp  
// compile with: /W1  
typedef struct bitfield {  
   signed mybit : 1;  
} mybitfield;  
  
int main() {  
   mybitfield bf;  
   bool b = true;  
  
   // try..  
   // int b = true;  
  
   bf.mybit = -1;  
   if (b == bf.mybit) {   // C4807  
      b = false;  
   }  
}  
```