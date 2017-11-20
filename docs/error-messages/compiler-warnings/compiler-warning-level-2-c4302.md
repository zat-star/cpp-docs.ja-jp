---
title: "コンパイラの警告 (レベル 2) C4302 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4302
dev_langs: C++
helpviewer_keywords: C4302
ms.assetid: f5e1c939-e134-4cca-ba1e-9b15a81549ae
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: afb3c41a0bd97753daf2be042ab1b699fd5cc6d8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-2-c4302"></a>コンパイラの警告 (レベル 2) C4302
'conversion': 切り捨てから 'type 1' を 'type 2'  
  
 大きい型から小さい型への変換が検出されました。 情報が失われる可能性があります。  
  
 既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。  
  
 次の例では、C4302 が生成されます。  
  
```  
// C4302.cpp  
// compile with: /W2  
#pragma warning(default : 4302)  
int main() {  
   int i;  
   char c = (char) &i;     // C4302  
   short s = (short) &i;   // C4302  
}  
```