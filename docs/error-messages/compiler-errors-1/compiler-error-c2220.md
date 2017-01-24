---
title: "コンパイラ エラー C2220 | Microsoft Docs"
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
  - "C2220"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2220"
ms.assetid: d610802c-64d7-40ad-a2a6-0ed0b6815a6c
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2220
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

warning treated as error \- no object file generated  
  
 [\/WX](../../build/reference/compiler-option-warning-level.md) を指定すると、警告はすべてエラーとして処理されます。  エラーが発生したため、オブジェクトまたは実行可能ファイルは生成されませんでした。  
  
 このエラーは、**\/WX** フラグが設定され、コンパイル中に警告が発生したときにだけ表示されます。  このエラーを解決するには、プロジェクトのすべての警告を除去する必要があります。  
  
### 解決するには、次のいずれかの手法を使用します。  
  
-   プロジェクトの警告の原因となった問題を解決します。  
  
-   警告レベルを低くしてコンパイルします。たとえば、**\/W4** の代わりに **\/W3** を使用します。  
  
-   特定の警告を無効にするか、表示されないようにするには、[warning](../../preprocessor/warning.md) プラグマを使用します。  
  
-   コンパイルに **\/WX** を使用しないでください。