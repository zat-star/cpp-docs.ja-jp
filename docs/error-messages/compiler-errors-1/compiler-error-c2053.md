---
title: "コンパイラ エラー C2053 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2053
dev_langs:
- C++
helpviewer_keywords:
- C2053
ms.assetid: 13324c85-13a8-4996-bd42-a31bfe7ff80f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 491d457447cc9ae6e5f0b66fa915e0aad45b85b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2053"></a>コンパイラ エラー C2053
'identifier': ワイド文字列が一致しません  
  
 ワイド文字列は、互換性のない型に割り当てられます。  
  
 次の例では、C2053 が生成されます。  
  
```  
// C2053.c  
int main() {  
   char array[] = L"Rika";   // C2053  
}  
```