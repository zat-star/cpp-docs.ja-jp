---
title: "-SYMBOLS |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /symbols
dev_langs: C++
helpviewer_keywords:
- symbols, dumping
- public symbols
- symbols, displaying COFF symbol table
- symbol tables
- SYMBOLS dumpbin option
- /SYMBOLS dumpbin option
- -SYMBOLS dumpbin option
ms.assetid: 34bcae90-4561-4c77-a80c-065508dec39a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fb8a1a42bf0bbb3b0bf9b907f93e1c9d0e69cf5b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="symbols"></a>/SYMBOLS
```  
/SYMBOLS  
```  
  
 このオプションは、COFF シンボル テーブルを表示します。 シンボル テーブルは、すべてのオブジェクト ファイルに存在します。 COFF シンボル テーブルは、/DEBUG にリンクされている場合にのみ、イメージ ファイルに表示されます。  
  
 /SYMBOLS の出力の説明を次に示します。 /SYMBOLS 出力の意味については、winnt.h (IMAGE_SYMBOL および IMAGE_AUX_SYMBOL) または COFF のドキュメントを参照してあります。  
  
 ダンプすると次の例を考えてみます。  
  
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
  
## <a name="remarks"></a>コメント  
 シンボル数値で始まる行について、次の説明には、ユーザーに関連する情報を持つ列がについて説明します。  
  
-   最初の 3 桁の数字は、シンボルのインデックス/数です。  
  
-   3 番目の列には、セクターが含まれている場合*x*シンボルをオブジェクト ファイルのセクションを定義します。 そのオブジェクトで定義されていませんし、別の場所を解決する必要があります UNDEF が表示されている場合。  
  
-   5 番目の列 (静的、外部) は、シンボルが、そのオブジェクト内でだけ参照可能かどうかがパブリックであるかどうかを示します (表示されている外部)。 _Sym とのスタティック シンボルは、パブリック シンボル _sym; にリンクはありません。_sym という名前の関数のうちの 2 つの異なるインスタンスになります。  
  
 番号付き行の最後の列がシンボル名は、装飾形式し、非装飾します。  
  
 のみ、 [/HEADERS](../../build/reference/headers.md) DUMPBIN オプションはにより生成されるファイルで使用できるよう、 [/GL](../../build/reference/gl-whole-program-optimization.md)コンパイラ オプション。  
  
## <a name="see-also"></a>参照  
 [DUMPBIN オプション](../../build/reference/dumpbin-options.md)