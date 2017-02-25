---
title: "コンパイラの警告 C4335 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4335"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4335"
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# コンパイラの警告 C4335
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mac ファイル形式が検出されました: ソース ファイルを DOS または UNIX 形式に変換してください  
  
 ソース ファイルの 1 行目の行の終了文字が、UNIX 形式 \('\\n'\) または DOS 形式 \('\\r\\n'\) ではなく Macintosh 形式 \('\\r'\) でした。  
  
 この警告は、常にエラーとして発行されます。この警告を無効にする方法については、[warning](../../preprocessor/warning.md) プラグマを参照してください。また、この警告は、コンパイル単位ごとに 1 回だけ表示されます。  したがって、Macintosh 形式のファイルを指定する `#include` ディレクティブが複数ある場合でも、C4335 が表示されるのは 1 回だけです。  
  
 Macintosh 形式のファイルは、たとえば Visual Studio で **\[ファイル\]** メニューの **\[保存オプションの詳細設定\]** を使用すると生成されます。  
  
## 使用例  
 次の例では C4335 エラーが生成されます。  
  
```  
// C4335 expected  
#include "c4335.h"   // assume both include files are in Macintosh format  
#include "c4335_2.h"  
```