---
title: "CL ファイル名の構文 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe コンパイラ, ファイル名構文"
  - "拡張, 指定 (コンパイラに)"
  - "ファイル名 [C++]"
  - "ファイル名 [C++], CL コンパイラ"
  - "パス, CL コンパイラのファイル名構文"
  - "構文, コンパイラ ファイル名"
ms.assetid: 3ca72586-75be-4477-b323-a1be232e80d4
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# CL ファイル名の構文
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CL は、名前が FAT、HPFS、NTFS のいずれかの名前付け規則に従っているファイルを受け入れます。  いずれのファイル名にも、完全なパスまたは相対パスを含めることができます。  完全なパスには、ドライブ名と 1 つ以上のディレクトリ名が含まれます。  CL は、円記号 \(\\\) またはスラッシュ \(\/\) で区切られたファイル名を受け入れます。  スペースが含まれるファイル名は、二重引用符文字で囲む必要があります。  相対パスではドライブ名を省略し、CL ではドライブが現在のドライブであると想定します。  パスを指定しない場合は、CL は、ファイルが現在のディレクトリにあると想定します。  
  
 ファイル名拡張子によって、ファイルの処理方法が決定されます。  拡張子が .c、.cxx、.cpp である、C および C\+\+ ファイルはコンパイルされます。  .obj ファイル、ライブラリ \(.lib\)、モジュール定義 \(.def\) ファイルなどのその他のファイルは、処理されずにリンカーに渡されます。  
  
## 参照  
 [コンパイラ コマンド ラインの構文](../../build/reference/compiler-command-line-syntax.md)