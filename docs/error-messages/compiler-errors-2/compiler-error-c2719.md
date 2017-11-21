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
ms.openlocfilehash: f7e6707dfd5666cb8852e3bbf59cf7a81dd24766
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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