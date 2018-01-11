---
title: "コンパイラ エラー C2732 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2732
dev_langs: C++
helpviewer_keywords: C2732
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aeecaab0fd9faaa6a876aa57781160df6bb26502
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2732"></a>コンパイラ エラー C2732
リンケージ指定は、別の 'function' に対する指定と矛盾しています。  
  
 関数は、別のリンケージ指定子で既に宣言されています。  
  
 このエラーは、インクルード ファイルに含まれるリンケージ指定子が異なることが原因で発生する可能性があります。  
  
 このエラーを修正するには、`extern` ステートメントを変更してリンケージが一致するようにします。 具体的には、`extern "C"` ブロックの `#include` ディレクティブをラップしないでください。  
  
## <a name="example"></a>例  
 次の例では、C2732 エラーが生成されます。  
  
```  
// C2732.cpp  
extern void func( void );   // implicit C++ linkage  
extern "C" void func( void );   // C2732  
```