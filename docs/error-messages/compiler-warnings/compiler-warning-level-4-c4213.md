---
title: "コンパイラの警告 (レベル 4) C4213 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4213
dev_langs: C++
helpviewer_keywords: C4213
ms.assetid: 59fc3f61-ebd2-499e-99d7-f57bec11eda1
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: abe563bd91736c9dfb6c0efc6507763b03a329cf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4213"></a>コンパイラの警告 (レベル 4) C4213
使用される標準の拡張機能: 左辺値のキャスト  
  
 既定 Microsoft 拡張機能 (/Ze)、代入ステートメントの左側にあるキャストを行うこともできます。  
  
## <a name="example"></a>例  
  
```  
// C4213.c  
// compile with: /W4  
void *a;  
void f()  
{  
   int   i[3];  
   a = &i;  
   *(( int * )a )++ = 3;  // C4213  
}  
  
int main()  
{  
}  
```  
  
 このようなキャストは ANSI 互換では有効ではありません ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。