---
title: "コンパイラ エラー C3200 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3200
dev_langs:
- C++
helpviewer_keywords:
- C3200
ms.assetid: 44bb5e77-f0ec-421c-a732-b9ee7c0a3529
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 315567b6a50584bca413f5b381f23e28b6329928
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3200"></a>コンパイラ エラー C3200
'template': テンプレート パラメーター 'parameter' に対する無効なテンプレート引数には、クラス テンプレートが必要です。  
  
 クラス テンプレートに無効な引数が渡されます。 クラス テンプレートは、パラメーターとしてテンプレートを受け付けます。 次の例では、呼び出す`Y<int, int> aY`C3200 が生成されます。 最初のパラメーターをテンプレートをなどある必要があります`Y<X, int> aY`です。  
  
```  
// C3200.cpp  
template<typename T>  
class X  
{  
};  
  
template<template<typename U> class T1, typename T2>  
class Y  
{  
};  
  
int main()  
{  
   Y<int, int> y;   // C3200  
}  
```