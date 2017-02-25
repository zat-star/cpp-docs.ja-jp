---
title: "例外処理ルーチン | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.exceptions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "例外処理, ルーチン"
ms.assetid: f60548c6-850a-4e1e-a79b-a2a6a541ab62
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 例外処理ルーチン
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プログラムの実行中に予期しないイベントから回復するのに C\+\+ 例外処理関数を使用します。  
  
### Exception Handling 関数  
  
|関数|使用方法|同等の .NET Framework 関数|  
|--------|----------|---------------------------|  
|[\_set\_se\_translator](../c-runtime-library/reference/set-se-translator.md)|C\+\+ に入力された例外として Win32 例外 \(C の構造化例外など\) を処理してください。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[set\_terminate](../c-runtime-library/reference/set-terminate-crt.md)|`terminate`が呼び出される独自の終端ルーチンをインストールします。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[set\_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|`unexpected`が呼び出される独自の終了関数をインストールします。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[terminate](../c-runtime-library/reference/terminate-crt.md)|特定の状況下で例外の後に自動的に呼び出され、スローされます。  ユーザーが `set_terminate`を使用して指定する関数または `terminate` 関数呼び出し `abort`|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[unexpected](../Topic/unexpected%20\(CRT\).md)|ユーザーが `set_unexpected`を使用して指定する関数または呼び出し `terminate`。  `unexpected` 関数は現在の Microsoft C\+\+ 例外処理の実装では使用されません。|[\<caps:sentence id\="tgt30" sentenceid\="ec8332f3bf55c7bd183338eca87744ec" class\="tgtSentence"\>System::Exception クラス\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.exception.aspx)|  
  
## 参照  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)