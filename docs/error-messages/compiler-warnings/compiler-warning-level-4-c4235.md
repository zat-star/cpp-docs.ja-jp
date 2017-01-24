---
title: "コンパイラの警告 (レベル 4) C4235 | Microsoft Docs"
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
  - "C4235"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4235"
ms.assetid: d4214799-d62c-4674-b4e2-9e201c303303
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4235
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

非標準の拡張機能が使用されています : 'キーワード' キーワードはこのアーキテクチャではサポートされていません  
  
 使用したキーワードは、サポートされていません。  
  
 この警告は、自動的にエラーになります。  この動作を変更する場合は、[warning](../../preprocessor/warning.md) を使用します。  たとえば、C4235 でレベル 2 の警告を発行させるには、  
  
```  
#pragma warning(2:4235)  
```  
  
 をソース コード ファイルに追加します。