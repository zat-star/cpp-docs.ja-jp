---
title: "致命的なエラー C1197 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1197
dev_langs:
- C++
helpviewer_keywords:
- C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d0eb3ab152e9299d47210a6d2c1eb58e3f92a925
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1197"></a>致命的なエラー C1197
プログラムは、'mscorlib.dll_2' を既に参照しました 'mscorlib.dll_1' を参照することはできません。  
  
 コンパイラは、共通言語ランタイムのバージョンに一致します。  ただし、しようとしましたが、以前のバージョンから共通言語ランタイムのファイルのバージョンを参照します。  
  
 このエラーを解決するには、Visual C のバージョンに付属している共通言語ランタイムのバージョンからの参照ファイルのみを使ってコンパイルします。  
  
## <a name="example"></a>例  
 次の例では、C1197 が生成されます。  
  
```  
// C1197.cpp  
// compile with: /clr /c  
// processor: x86  
#using "C:\Windows\Microsoft.NET\Framework\v1.1.4322\mscorlib.dll"   // C1197  
// try the following line instead  
// #using "mscorlib.dll"  
```
