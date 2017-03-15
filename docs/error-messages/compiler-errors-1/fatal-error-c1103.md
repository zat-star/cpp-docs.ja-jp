---
title: "致命的なエラー C1103 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1103"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1103"
ms.assetid: 9d276939-9c47-4235-9d20-76b8434f9731
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 致命的なエラー C1103
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

progid をインポート中の致命的なエラー: 'message'  
  
 コンパイラがタイプ ライブラリのインポートで問題を検出しました。  たとえば、progid を持つタイプ ライブラリを指定し、さらに `no_registry` を指定することはできません。  
  
 詳細については、「[\#import ディレクティブ](../Topic/%23import%20Directive%20\(C++\).md)」を参照してください。  
  
 次の例では C1103 エラーが生成されます。  
  
```  
// C1103.cpp #import "progid:a.b.id.1.5" no_registry auto_search   // C1103  
```