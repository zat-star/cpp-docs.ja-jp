---
title: "Null マクロと未定義マクロ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "マクロ, null および未定義の"
  - "NMAKE プログラム, null マクロ"
  - "NMAKE プログラム, 未定義マクロ"
  - "null マクロ (NMAKE の)"
  - "未定義マクロと NMAKE"
ms.assetid: 1db4611a-1755-4328-b00f-d35365af8b6c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Null マクロと未定義マクロ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

null マクロと未定義マクロは、両方とも null 文字列に展開されます。ただし、null 文字列として定義されているマクロは、プリプロセッサ式で定義されているものと判断されます。  マクロを null 文字列として定義するには、コマンド ラインまたはコマンド ファイルで等号 \(\=\) の後に空白またはタブ以外の文字を指定せず、null 文字列または定義を二重引用符 \(" "\) で囲みます。  マクロを未定義にするには、**\!UNDEF** を使用します。詳細については、「[メイクファイルのプリプロセス ディレクティブ](../build/makefile-preprocessing-directives.md)」を参照してください。  
  
## 参照  
 [NMAKE マクロの定義](../build/defining-an-nmake-macro.md)