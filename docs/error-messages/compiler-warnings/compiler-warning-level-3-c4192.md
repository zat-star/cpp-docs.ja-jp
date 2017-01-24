---
title: "コンパイラの警告 (レベル 3) C4192 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4192"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4192"
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 3) C4192
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'name' を自動的に除外し、タイプ ライブラリ 'library' をインポートします。  
  
 ライブラリの `#import` に含まれている項目 *name* は、Win32 システム ヘッダーでも定義されています。  タイプ ライブラリの制限事項により、**IUnknown** または GUID などの名前は、タイプ ライブラリで定義され、システム ヘッダーの定義と重複することがあります。  `#import` は、これらの重複項目を検出し、それらを .tlh および .tli ヘッダー ファイルに取り込まないようにします。  
  
 この動作をオーバーライドするには、`#import` 属性 [no\_auto\_exclude](../../preprocessor/no-auto-exclude.md) および [include\(\)](../../preprocessor/include-parens.md) を使用します。