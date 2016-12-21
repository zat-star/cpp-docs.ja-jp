---
title: "コンパイラの警告 (レベル 3) C4622 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4622"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4622"
ms.assetid: d3c879f0-4492-4f4b-b26d-230993f3a933
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 3) C4622
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

オブジェクト ファイル 'file' でデバッグ情報はプリコンパイル済みヘッダーを作成したときに上書きされました  
  
 指定されたファイルの CodeView 情報が、\(プリコンパイル済みヘッダーを使用する\) [\/Yu](../../build/reference/yu-use-precompiled-header-file.md) オプションを指定してコンパイルしたときに失われました。  
  
 プリコンパイル済みヘッダー ファイルを作成または使用する場合は、\([\/Fo](../../build/reference/fo-object-file-name.md) を使用して\) オブジェクト ファイルの名前を変更し、新しいオブジェクト ファイルを使用してリンクします。