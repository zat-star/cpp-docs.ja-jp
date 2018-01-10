---
title: "コンパイラ エラー C2719 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2719
dev_langs: C++
helpviewer_keywords: C2719
ms.assetid: ea6236d3-8286-45cc-9478-c84ad3dd3c8e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 554a8c2655e82e7d793966738474338aab934168
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2719"></a>コンパイラ エラー C2719
'parameter': __declspec(align('#')) の仮引数はアラインされません。  
  
 [整列](../../cpp/align-cpp.md)`__declspec`修飾子は関数のパラメーターでは許可されません。 関数パラメーターのアラインメントは、呼び出し規則によって制御されます。 詳細については、次を参照してください。[呼び出し規約](../../cpp/calling-conventions.md)です。  
  
 次の例は C2719 を生成し、その修正方法を示しています。  
  
```  
// C2719.cpp  
void func(int __declspec(align(32)) i);   // C2719  
// try the following line instead  
// void func(int i);  
```