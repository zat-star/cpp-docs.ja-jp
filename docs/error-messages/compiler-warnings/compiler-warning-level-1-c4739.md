---
title: "コンパイラの警告 (レベル 1) C4739 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4739
dev_langs: C++
helpviewer_keywords: C4739
ms.assetid: 600873b3-7c85-4cd4-944e-cd8e01bfcbb0
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d11002afb2eac0c7f9c6971bca3610463eed0d55
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4739"></a>コンパイラの警告 (レベル 1) C4739
変数 'var' への参照はそのストレージ領域を超えています  
  
 変数に代入された値が、変数のサイズを超えています。 変数のメモリ位置を超えるメモリが書き込まれるため、データ損失が発生する可能性があります。  
  
 この警告を解決するには、その値を格納できるサイズの変数にのみ値を割り当てます。  
  
 次の例では C4739 が生成されます。  
  
```  
// C4739.cpp  
// compile with: /RTCs /Zi /W1 /c  
char *pc;  
int main() {  
   char c;  
   *(int *)&c = 1;   // C4739  
  
   // OK  
   *(char *)&c = 1;  
}  
```