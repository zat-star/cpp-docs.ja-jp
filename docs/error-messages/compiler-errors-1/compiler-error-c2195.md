---
title: "コンパイラ エラー C2195 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2195
dev_langs:
- C++
helpviewer_keywords:
- C2195
ms.assetid: 9f9f035c-9c51-4173-a8ea-c6f907fc5c63
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 557d4dd0ae0f25326fed227ab9ad508e2ebce30d
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2195"></a>コンパイラ エラー C2195
'identifier': データ セグメントは、  
  
 `code_seg`プラグマで使用されるセグメント名を使用して、`data_seg`プラグマ。  
  
 次の例では、C2195 が生成されます。  
  
```  
// C2195.cpp  
#pragma data_seg("MYDATA")  
#pragma code_seg("MYDATA")   // C2195  
#pragma code_seg("MYDATA2")   // OK  
```
