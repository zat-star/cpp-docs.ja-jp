---
title: "コンパイラの警告 C4936 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4936
dev_langs:
- C++
helpviewer_keywords:
- C4936
ms.assetid: 6676de35-bf1b-4d0b-a70f-b5734130336c
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a4342c749c5db4d66f206209a146ad7d7aef7041
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4936"></a>コンパイラの警告 C4936
この __declspec は、/clr または /clr:pure でコンパイルされるときのみサポートされます  
  
 **/Clr: 純粋な**コンパイラ オプションは Visual Studio 2015 で推奨されなくなりました。  
  
 `__declspec` 修飾子が使用されましたが、この `__declspec` 修飾子は、いずれかの [/clr](../../build/reference/clr-common-language-runtime-compilation.md) オプションでコンパイルされた場合にのみ有効です。  
  
 詳細については、「 [appdomain](../../cpp/appdomain.md) 」および「 [process](../../cpp/process.md)」を参照してください。  
  
 C4936 は、常にエラーとして表示されます。  [warning](../../preprocessor/warning.md) プラグマを使用して、C4936 を無効にすることができます。  
  
 次の例では C4936 が生成されます。  
  
```  
// C4936.cpp  
// compile with: /c  
// #pragma warning (disable : 4936)  
__declspec(process) int i;   // C4936  
__declspec(appdomain) int j;   // C4936  
```
