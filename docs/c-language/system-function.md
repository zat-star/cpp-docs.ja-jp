---
title: "system 関数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "system 関数"
ms.assetid: 0786ccdc-20cd-4d96-b3d8-3230507c3066
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# system 関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 4.10.4.5 system** 関数による文字列の実行の内容とモード  
  
 **system** 関数は、コマンド ラインからではなく、C プログラムから内部オペレーティング システム コマンド、.EXE、.COM \(Windows NT の .CMD\)、または .BAT ファイルを実行します。  
  
 system 関数は、コマンド インタープリターを探します。これは通常、Windows NT オペレーティング システムでは CMD.EXE、Windows では COMMAND.COM です。  system 関数は、続いてコマンド インタープリターに引数文字列を渡します。  
  
 詳細については、「[system、\_wsystem](../c-runtime-library/reference/system-wsystem.md)」を参照してください。  
  
## 参照  
 [ライブラリ関数](../c-language/library-functions.md)