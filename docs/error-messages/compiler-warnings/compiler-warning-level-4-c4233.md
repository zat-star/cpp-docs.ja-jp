---
title: "コンパイラの警告 (レベル 4) C4233 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4233"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4233"
ms.assetid: 9aa51fc6-8ef3-43b5-bafb-c9333cf60de3
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 4) C4233
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

非標準の拡張機能が使用されています : 'keyword' キーワードは C ではなく、C\+\+ でのみサポートされます。  
  
 コードは C\+\+ ではなく C としてコンパイルされています。さらに、コードで C\+\+ でだけ有効なキーワードを使用しています。  ソース ファイルの拡張子が .c の場合や、コマンド ラインのオプションで [\/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) を使用した場合は、C としてコンパイルされます。  
  
 この警告は、自動的にエラーになります。  この動作を変更する場合は、[warning](../../preprocessor/warning.md) を使用します。  たとえば、C4233 でレベル 4 の警告を発行させるには、  
  
```  
#pragma warning(2:4233)  
```  
  
 をソース コード ファイルに追加します。