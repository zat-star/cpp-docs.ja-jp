---
title: "致命的なエラー C1900 | Microsoft Docs"
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
  - "C1900"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1900"
ms.assetid: 3aaa583b-4c1a-45de-aa34-527d806f2cb5
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 致命的なエラー C1900
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'tool1' の Version 'number1' と 'tool2' の Version 'number2' が一致しません。  
  
 コンパイラのさまざまなパスで実行されたツールが一致しません。  ***number1*** と ***number2*** はファイルの日付を示します。  たとえば、パス 1 ではコンパイラ フロントエンドが \(c1.dll\) を実行し、パス 2 ではコンパイラ バックエンドが \(c2.dll\) を実行します。  ファイルの日付が一致する必要があります。  
  
 この問題を解決するには、Visual Studio のすべての更新プログラムが適用されたことを確認します。  問題が解決しない場合は、Windows のコントロール パネルの **\[プログラムと機能\]** を使用して修復するか、または Visual Studio を再インストールします。