---
title: "リソース コンパイラの警告 RC4005 | Microsoft Docs"
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
  - "RC4005"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC4005"
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リソース コンパイラの警告 RC4005
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'識別子' : マクロが再定義されました。  
  
 この識別子は、2 回定義されています。  コンパイラは、2 つ目のマクロ定義を使います。  
  
 この警告は、マクロをコマンド ラインとコード内の `#define` ディレクティブの両方で定義したときに発生します。  また、マクロをインクルード ファイルからインポートしたときにも発生します。  
  
 この警告を回避するには、定義の片方を削除するか、2 つ目の定義の前で `#undef` ディレクティブを使ってください。