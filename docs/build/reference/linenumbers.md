---
title: "/LINENUMBERS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/linenumbers"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LINENUMBERS dumpbin オプション"
  - "行番号"
  - "LINENUMBERS dumpbin オプション"
  - "-LINENUMBERS dumpbin オプション"
ms.assetid: 1681d582-2c2f-484e-9920-109959549055
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /LINENUMBERS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LINENUMBERS  
```  
  
## 解説  
 このオプションは、COFF 行番号を出力します。  \/Zi \(プログラム データベースを使用\)、\/Z7 \(C7 互換\)、\/Zd \(行番号のみ\) のいずれかを指定してコンパイルすると、オブジェクト ファイルに行番号が付きます。  \/DEBUG \(デバッグ情報を生成する\) を指定してリンクされていると、実行可能ファイルと DLL に COFF 行番号が付きます。  
  
 [\/GL](../../build/reference/gl-whole-program-optimization.md) コンパイラ オプションで生成したファイルで使用できるのは、[\/HEADERS](../../build/reference/headers.md) DUMPBIN オプションだけです。  
  
## 参照  
 [DUMPBIN オプション](../../build/reference/dumpbin-options.md)