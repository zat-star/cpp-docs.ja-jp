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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 2fbe6bcb1850948d4484fca93f2cd511a9e2a1da
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2833"></a>コンパイラ エラー C2833
'演算子' は認識されている演算子または種類ではありません。  
  
 単語`operator`をオーバーライドする演算子または変換する型に従わなければなりません。  
  
 マネージ型で定義できる演算子の一覧は、次を参照してください。[ユーザー定義演算子](../../dotnet/user-defined-operators-cpp-cli.md)します。  
  
 次の例では、c2833 エラーが生成されます。  
  
```  
// C2833.cpp  
// compile with: /c  
class A {};  
  
void operator ::* ();   // C2833  
void operator :: ();   // OK  
```
