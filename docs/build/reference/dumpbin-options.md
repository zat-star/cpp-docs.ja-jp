---
title: "DUMPBIN オプション | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "dumpbin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DUMPBIN プログラム、オプション"
ms.assetid: 563b696e-7599-4480-94b9-014776289ec8
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# DUMPBIN オプション
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

オプションを指定するには、オプション指定子の \- \(ダッシュ\) または \/ \(スラッシュ\) の後ろにオプション名を入力します。  オプション名の省略形は使用できません。  引数を取るオプションの場合は、: \(コロン\) の後ろに引数を指定します。  1 つのオプションの指定には、スペースやタブは挿入できません。  複数のオプションを指定する場合は、各オプションを 1 つ以上のスペースまたはタブで区切ります。  オプション名、およびその引数として指定するキーワードやファイル名では、大文字と小文字は区別されません。  大半のオプションはバイナリ ファイルにも適用できますが、特定の種類のファイルにしか指定できないオプションもあります。  特に指定されていない限り、DUMPBIN は標準出力に情報を出力します。  ファイルに出力するには、[\/OUT](../../build/reference/out-dumpbin.md) オプションを指定します。  
  
 DUMPBIN には、次のオプションがあります。  
  
-   [\/ALL](../../build/reference/all.md)  
  
-   [\/ARCHIVEMEMBERS](../Topic/-ARCHIVEMEMBERS.md)  
  
-   [\/CLRHEADER](../../build/reference/clrheader.md)  
  
-   [\/DEPENDENTS](../Topic/-DEPENDENTS.md)  
  
-   [\/DIRECTIVES](../../build/reference/directives.md)  
  
-   [\/DISASM](../../build/reference/disasm.md)  
  
-   [\/ERRORREPORT \(dumpbin.exe\)](../../build/reference/errorreport-dumpbin-exe.md)  
  
-   [\/EXPORTS](../../build/reference/dash-exports.md)  
  
-   [\/FPO](../../build/reference/fpo.md)  
  
-   [\/HEADERS](../../build/reference/headers.md)  
  
-   [\/IMPORTS](../../build/reference/imports-dumpbin.md)  
  
-   [\/LINENUMBERS](../../build/reference/linenumbers.md)  
  
-   [\/LINKERMEMBER](../../build/reference/linkermember.md)  
  
-   [\/LOADCONFIG](../../build/reference/loadconfig.md)  
  
-   [\/OUT](../../build/reference/out-dumpbin.md)  
  
-   [\/PDATA](../../build/reference/pdata.md)  
  
-   [\/PDBPATH](../../build/reference/pdbpath.md)  
  
-   [\/RANGE](../../build/reference/range.md)  
  
-   [\/RAWDATA](../../build/reference/rawdata.md)  
  
-   [\/RELOCATIONS](../../build/reference/relocations.md)  
  
-   [\/SECTION](../../build/reference/section-dumpbin.md)  
  
-   [\/SUMMARY](../Topic/-SUMMARY.md)  
  
-   [\/SYMBOLS](../../build/reference/symbols.md)  
  
-   [\/TLS](../../build/reference/tls.md)  
  
## 参照  
 [C と C\+\+ のビルド ツール](../Topic/C-C++%20Build%20Tools.md)   
 [DUMPBIN リファレンス](../../build/reference/dumpbin-reference.md)