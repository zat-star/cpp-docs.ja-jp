---
title: "コンパイラ エラー C3645 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3645
dev_langs: C++
helpviewer_keywords: C3645
ms.assetid: 346da528-ae86-4cd0-9654-f41bee26ac0d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 43bda10ee2e4f2939061d70cfcf19da950909d03
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3645"></a>コンパイラ エラー C3645
'function': _ _clrcall は、ネイティブ コードにコンパイルされた関数では使用できません  
  
 関数内のいくつかのキーワードの有無をネイティブにコンパイルする関数となります。  
  
## <a name="example"></a>例  
 次の例では、C3645 を生成します。  
  
```  
// C3645.cpp  
// compile with: /clr /c  
#pragma unmanaged   
int __clrcall dog() {}   // C3645  
```