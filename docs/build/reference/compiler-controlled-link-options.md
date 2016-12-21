---
title: "コンパイラで制御される LINK オプション | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "link"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe コンパイラ [C++], 制御 (リンカーを)"
  - "cl.exe コンパイラ [C++], 機能 (リンクを制御する)"
  - "LINK ツール [C++], コンパイラで制御されるオプション"
  - "リンカー [C++], CL コンパイラの制御"
  - "リンク [C++], 影響 (CL の機能による)"
ms.assetid: e4c03896-c99c-4599-8502-e0f4bebe69d0
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラで制御される LINK オプション
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/c オプションが指定されていないと、CL コンパイラは自動的に LINK を呼び出します。  CL のコマンド ライン オプションと引数でも、リンカーを制御できます。  次の表は、リンクを制御する CL の機能をまとめたものです。  
  
|CL の指定|LINK に対する処理|  
|------------|-----------------|  
|拡張子 .c、.cxx、.cpp、または .def を除くすべてのファイル名|LINK への入力としてファイル名を渡します。|  
|*filename*.def|\/DEF:*filename*.def という形で渡します。|  
|\/F`number`|\/STACK:`number` という形で渡します。|  
|\/Fd*filename*|\/PDB:*filename* という形で渡します。|  
|\/Fe*filename*|\/OUT:*filename* という形で渡します。|  
|\/Fm*filename*|\/MAP:*filename* という形で渡します。|  
|\/Gy|パッケージ化された関数 \(COMDAT\) を作成し、関数レベルのリンクを有効にします。|  
|\/LD|\/DLL を渡します。|  
|\/LDd|\/DLL を渡します。|  
|\/link|コマンド ラインの残りの部分を LINK に渡します。|  
|\/MD または \/MT|.obj ファイルに既定のライブラリ名を書き込みます。|  
|\/MDd または \/MTd|.obj ファイルに既定のライブラリ名を書き込みます。  シンボル **\_DEBUG** を定義します。|  
|\/nologo|Passes \/NOLOGO|  
|\/Zd|Passes \/DEBUG|  
|\/Zi または \/Z7|Passes \/DEBUG|  
|\/Zl|.obj ファイルから既定のライブラリ名を省きます。|  
  
 詳細については、「[コンパイラ オプション](../../build/reference/compiler-options.md)」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)