---
title: "コンパイラ エラー C2833 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2833
dev_langs:
- C++
helpviewer_keywords:
- C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2d3adf42ddb4df4365a45fd3ef24bccd682ac3c9
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2833"></a>コンパイラ エラー C2833
'operator 演算子' は認識されている演算子または型ではありません。  
  
 単語`operator`をオーバーライドする演算子または変換する型が続かなければなりません。  
  
 マネージ型で定義できる演算子の一覧は、次を参照してください。[ユーザー定義の演算子](../../dotnet/user-defined-operators-cpp-cli.md)です。  
  
 次の例では、C2833 が生成されます。  
  
```  
// C2833.cpp  
// compile with: /c  
class A {};  
  
void operator ::* ();   // C2833  
void operator :: ();   // OK  
```
