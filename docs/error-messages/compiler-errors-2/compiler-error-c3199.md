---
title: "コンパイラ エラー C3199 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3199
dev_langs: C++
helpviewer_keywords: C3199
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1f32d42123a64d14ee04a6af7cdebd79ad19b809
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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