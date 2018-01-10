---
title: "コンパイラ エラー C3895 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3895
dev_langs: C++
helpviewer_keywords: C3895
ms.assetid: 771b9fe5-d6d4-4297-bf57-e2f857722155
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9343a7d6f85864de809aea5d83965e65e9f5b70b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3895"></a>コンパイラ エラー C3895
'var': 型のデータ メンバーを 'volatile' にすることはできません  
  
 特定の種類の例については、データ メンバー[リテラル](../../windows/literal-cpp-component-extensions.md)または[initonly](../../dotnet/initonly-cpp-cli.md)、することはできません[揮発性](../../cpp/volatile-cpp.md)です。  
  
 次の例では、C3895 が生成されます。  
  
```  
// C3895.cpp  
// compile with: /clr  
ref struct Y1 {  
   initonly  
   volatile int data_var2;   // C3895  
};  
```