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
ms.workload: cplusplus
ms.openlocfilehash: 0890b69f2980ac550d17b622b293d6f7c23e5010
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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