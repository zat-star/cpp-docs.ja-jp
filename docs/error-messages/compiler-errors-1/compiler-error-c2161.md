---
title: "コンパイラ エラー C2161 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2161
dev_langs: C++
helpviewer_keywords: C2161
ms.assetid: d6798821-13bb-4e60-924f-85f7bf955387
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 11298c107aa927e62e4bc84f2d709c6f46c54c98
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2161"></a>コンパイラ エラー C2161
マクロ定義がトークン連結演算子 (##) で終わっています。  
  
 マクロ定義がトークン連結演算子 (##) で終わっています。  
  
 次の例では C2161 が生成されます。  
  
```  
// C2161.cpp  
// compile with: /c  
#define mac(a,b) a   // OK  
#define mac(a,b) a##   // C2161  
```