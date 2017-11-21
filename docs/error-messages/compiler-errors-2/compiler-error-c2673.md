---
title: "コンパイラ エラー C2673 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2673
dev_langs: C++
helpviewer_keywords: C2673
ms.assetid: 780230c0-619b-4a78-b01d-ff5886306741
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 551801e5d13f18335d30fb1ea37ad29ca27aa777
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2673"></a>コンパイラ エラー C2673
'function': グローバル関数には、'this' ポインターはありません。  
  
 グローバル関数にアクセスしようとしました。`this`です。  
  
 次の例では、C2673 が生成されます。  
  
```  
// C2673.cpp  
int main() {  
   this = 0;   // C2673  
}  
```