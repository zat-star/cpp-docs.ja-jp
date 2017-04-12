---
title: "コンパイラの警告 C4936 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 58d702067c186eeeea94768a03836b64577961ca
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-c4936"></a>コンパイラの警告 C4936
この __declspec は、/clr または /clr:pure でコンパイルされるときのみサポートされます  
  
 **/Clr: 純粋な**コンパイラ オプションは Visual Studio 2015 で使用されなくなりました。  
  
 A`__declspec`されたが、修飾子が使用されて`__declspec`修飾子は有効なは、いずれかでコンパイルした場合のみ、 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)オプション。  
  
 詳細については、次を参照してください。 [appdomain](../../cpp/appdomain.md)と[プロセス](../../cpp/process.md)します。  
  
 C4936 は、常にエラーとして表示されます。  C4936 で無効にすることができます、[警告](../../preprocessor/warning.md)プラグマです。  
  
 次の例では C4936 が生成されます。  
  
```  
// C4936.cpp  
// compile with: /c  
// #pragma warning (disable : 4936)  
__declspec(process) int i;   // C4936  
__declspec(appdomain) int j;   // C4936  
```
