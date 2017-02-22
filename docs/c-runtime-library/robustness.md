---
title: "保全性 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.runtime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "保全性 [CRT]"
ms.assetid: 7f1a87f8-eff9-4b76-ae9b-d133d3de6adf
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# 保全性
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プログラムの信頼性を向上させるには、次の C ランタイム ライブラリ関数を使用します。  
  
### ランタイムの信頼性関数  
  
|関数|用途|同等の .NET Framework 関数|  
|--------|--------|---------------------------|  
|[\_set\_new\_handler](../Topic/_set_new_handler.md)|`new` 演算子がメモリの割り当てに失敗した場合は、独自のエラー処理機構に制御を移します。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_set\_se\_translator](../c-runtime-library/reference/set-se-translator.md)|Win32 例外 \(C 構造化例外\) を C\+\+ 型指定例外として処理します。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[set\_terminate](../c-runtime-library/reference/set-terminate-crt.md)|[terminate](../c-runtime-library/reference/terminate-crt.md) によって呼び出される独自の終了関数をインストールします。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[set\_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|[unexpected](../Topic/unexpected%20\(CRT\).md) によって呼び出される独自の終了関数をインストールします。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
  
## 参照  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)   
 [SetUnhandledExceptionFilter](http://msdn.microsoft.com/library/windows/desktop/ms680634.aspx)