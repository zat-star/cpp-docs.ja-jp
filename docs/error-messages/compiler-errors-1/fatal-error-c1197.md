---
title: "致命的なエラー C1197 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1197
dev_langs: C++
helpviewer_keywords: C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1658e55a9298df703051b856bb9b10dd02d8cc68
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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