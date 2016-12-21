---
title: "include() | Microsoft Docs"
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
  - "include()"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "include() 属性"
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# include()
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 固有の仕様**  
  
 自動除外を無効にします。  
  
## 構文  
  
```  
include("Name1"[,"Name2", ...])  
```  
  
#### パラメーター  
 `Name1`  
 強制的に含まれる最初の項目。  
  
 `Name2`  
 強制的に含める 2 番目の項目 \(必要な場合\)。  
  
## 解説  
 タイプ ライブラリは、システム ヘッダーまたはその他のタイプ ライブラリで定義された項目の定義を含むことがあります。  `#import` は、そのような項目を自動的に除外して多重定義エラーを回避します。  [コンパイラの警告 \(レベル 3\) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md) で示されているように、項目が除外されていて、これらの項目が存在していない場合、この属性を使用して自動除外を無効にできます。  この属性は、任意の数の引数を受け取ることができます。各引数は、含まれるタイプ ライブラリ項目の名前です。  
  
 **END C\+\+ 固有の仕様**  
  
## 参照  
 [\#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import ディレクティブ](../Topic/%23import%20Directive%20\(C++\).md)