---
title: "コンパイラの警告 (レベル 4) C4559 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4559
dev_langs: C++
helpviewer_keywords: C4559
ms.assetid: ed542f60-454d-45cb-85da-987ede61b1ab
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 046a3186554603d4a33b2eec78084dd76ec64e40
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4559"></a>コンパイラの警告 (レベル 4) C4559
'function': 再定義されています。関数の向上 __declspec(modifier)  
  
 2 つ目の定義または宣言は、_ _ を追加し、関数が再定義または再宣言**declspec**修飾子 (***修飾子***)。 これは、情報提供の警告です。 この警告を解決するには、いずれかの定義を削除します。  
  
 次の例では、C4559 が生成されます。  
  
```  
// C4559.cpp  
// compile with: /W4 /LD  
void f();  
__declspec(noalias) void f();   // C4559  
```