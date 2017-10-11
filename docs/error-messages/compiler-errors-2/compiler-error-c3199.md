---
title: "コンパイラ エラー C3199 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3199
dev_langs:
- C++
helpviewer_keywords:
- C3199
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 37443adbfdf65caba83656ca70ff799834fb4eac
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3199"></a>コンパイラ エラー C3199
無効な浮動小数点プラグマの使用: 例外は precise でないモードでサポートされていません  
  
 [Float_control](../../preprocessor/float-control.md)プラグマは、下の浮動小数点例外モデルを指定に使用された、 [/fp](../../build/reference/fp-specify-floating-point-behavior.md)以外に設定**/fp: 正確な**します。  
  
 次の例では、C3199 が生成されます。  
  
```  
// C3199.cpp  
// compile with: /fp:fast  
#pragma float_control(except, on)   // C3199  
```
