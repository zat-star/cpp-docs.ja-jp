---
title: "no_implementation | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "no_implementation"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "no_implementation 属性"
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# no_implementation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 固有の仕様**  
  
 ラッパー メンバー関数の実装を含む .tli ヘッダーの生成を抑制します。  
  
## 構文  
  
```  
no_implementation  
```  
  
## 解説  
 この属性を指定すると、タイプ ライブラリの項目の公開が宣言され、.tlh ヘッダーが生成されます。`#include` ステートメントによって .tli ヘッダー ファイルは取り込まれません。  
  
 この属性は、[implementation\_only](../preprocessor/implementation-only.md) と組み合わせて使用します。  
  
 **END C\+\+ 固有の仕様**  
  
## 参照  
 [\#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import ディレクティブ](../Topic/%23import%20Directive%20\(C++\).md)