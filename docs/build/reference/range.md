---
title: "/RANGE | Microsoft Docs"
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
  - "/RANGE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/RANGE dumpbin オプション"
  - "-RANGE dumpbin オプション"
ms.assetid: 7eeba266-32be-49cc-a350-96bdf541f98a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /RANGE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/RAWDATA や \/DISASM などの他の dumpbin オプションと共に使用された場合、dumpbin の出力を変更します。  
  
## 構文  
  
```  
/RANGE:vaMin[,vaMax]  
```  
  
## フラグ  
 **vaMin**  
 dumpbin 操作を開始する仮想アドレス。  
  
 **vaMax** \(省略可能\)  
 dumpbin 操作を終了する仮想アドレス。  このフラグを省略すると、dumpbin 操作はファイルの終わりまで行われます。  
  
## 解説  
 イメージの仮想アドレスを確認するには、イメージ \(RVA \+ Base\) のマップ ファイルを使用するか、dumpbin の **\/DISASM** オプションまたは **\/HEADERS** オプションを使用するか、Visual Studio デバッガーの逆アセンブリ ウィンドウを使用します。  
  
## 使用例  
 次の例では、**\/range** を使用して **\/disasm** オプションの表示を変更します。  この例では、開始値は 10 進数で指定され、終了値は 16 進数で指定されています。  
  
```  
dumpbin /disasm /range:4219334,0x004061CD t.exe  
```  
  
## 参照  
 [DUMPBIN オプション](../../build/reference/dumpbin-options.md)