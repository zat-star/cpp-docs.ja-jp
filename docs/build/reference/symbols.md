---
title: "/SYMBOLS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/symbols"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SYMBOLS dumpbin オプション"
  - "パブリック シンボル"
  - "シンボル テーブル"
  - "SYMBOLS dumpbin オプション"
  - "-SYMBOLS dumpbin オプション"
  - "シンボル, 表示 (COFF シンボル テーブルの)"
  - "シンボル, ダンプ"
ms.assetid: 34bcae90-4561-4c77-a80c-065508dec39a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /SYMBOLS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SYMBOLS  
```  
  
 このオプションは、COFF シンボル テーブルを出力します。  シンボル テーブルは、すべてのオブジェクト ファイルにあります。  イメージ ファイルの場合は、\/DEBUG を指定してリンクされている場合にのみ COFF シンボル テーブルが存在します。  
  
 \/SYMBOLS を指定したときの出力について説明します。  \/SYMBOLS の出力の意味については、winnt.h \(IMAGE\_SYMBOL と IMAGE\_AUX\_SYMBOL\) または COFF のドキュメントの追加情報も参考にしてください。  
  
 次のサンプル ダンプを例にして説明します。  
  
```  
Dump of file main.obj  
File Type: COFF OBJECT  
  
COFF    SYMBOL    TABLE  
000    00000000   DEBUG      notype      Filename      | .file  
      main.cpp  
002   000B1FDB   ABS      notype      Static      | @comp.id  
003   00000000   SECT1      notype      Static      | .drectve  
      Section length       26, #relocs   0, #linenums    0, checksum 722C964F  
005   00000000   SECT2      notype      Static      | .text  
      Section length      23, #relocs      1, #linenums    0, checksum 459FF65F, selection    1 (pick no duplicates)  
007   00000000   SECT2      notype ()   External      | _main  
008   00000000   UNDEF      notype ()   External      | ?MyDump@@YAXXZ (void __cdecl MyDump(void))  
  
String Table Size = 0x10 bytes  
  
Summary  
  
      26 .drectve  
      23 .text  
```  
  
## 解説  
 シンボル番号で始まる行の、ユーザーに関連のある情報が含まれる列について説明します。  
  
-   最初の 3 桁の数字は、シンボルのインデックス\/番号です。  
  
-   3 番目の列が SECT*x* の場合、シンボルはオブジェクト ファイルのそのセクションで定義されています。  ただし、UNDEF となっている場合は、そのオブジェクトでは定義されているのではなく、ほかのいずれかの場所で解決されている必要があります。  
  
-   5 番目の列 \(Static または External\) は、そのオブジェクト内だけで参照できるシンボル、またはパブリックなシンボル \(外部から参照できるシンボル\) のいずれかであることを示しています。  スタティック シンボルの \_sym とパブリック シンボルの \_sym はリンクされていません。これらは、\_sym という名前の関数の異なる 2 つのインスタンスです。  
  
 番号が付いた行の最後の列は、シンボル名 \(装飾形式と非装飾形式\) です。  
  
 [\/GL](../../build/reference/gl-whole-program-optimization.md) コンパイラ オプションで生成したファイルで使用できるのは、[\/HEADERS](../../build/reference/headers.md) DUMPBIN オプションだけです。  
  
## 参照  
 [DUMPBIN オプション](../../build/reference/dumpbin-options.md)