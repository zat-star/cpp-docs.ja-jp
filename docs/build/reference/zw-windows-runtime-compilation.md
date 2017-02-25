---
title: "/ZW (Windows ランタイムのコンパイル) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.CompileAsWinRT"
  - "/zw"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ZW"
  - "/ZW コンパイラ オプション"
  - "Windows ランタイム コンパイラ オプション"
  - "-ZW"
  - "-ZW コンパイラ オプション"
ms.assetid: 0fe362b0-9526-498b-96e0-00d7a965a248
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# /ZW (Windows ランタイムのコンパイル)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリケーションの作成で [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] \([!INCLUDE[cppwrt_short](../Token/cppwrt_short_md.md)]\) をサポートするためのソース コードをコンパイルします。  
  
 **\/ZW** を使用してコンパイルする場合、**\/EHsc** も必ず指定します。  
  
## 構文  
  
```cpp  
/ZW /EHsc /ZW:nostdlib /EHsc  
```  
  
## 引数  
 nostdlib  
 Platform.winmd、Windows.Foundation.winmd、および他の既定の Windows メタデータ \(.winmd\) ファイルがコンパイルで自動に含まれていないことを示します。  その代わりに、[\/FU \(Name Forced \#using File\)](../../build/reference/fu-name-forced-hash-using-file.md) コンパイラ オプションを使って Windows メタデータ ファイルを明示的に指定する必要があります。  
  
## 解説  
 **\/ZW** オプションを指定する場合、コンパイラは次の機能をサポートします。  
  
-   [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] で実行するためにアプリケーションが必要とするメタデータ ファイル、名前空間、データ型、および関数。  
  
-   [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] オブジェクトの自動参照カウント、および参照カウントがゼロになった場合のオブジェクトの自動破棄。  
  
 Incremental Linker は **\/ZW** オプションの使用により .obj ファイルに含まれる Windows メタデータはサポートされないため、[\/Gm \(簡易リビルドの有効化\)](../../build/reference/gm-enable-minimal-rebuild.md) オプションは **\/ZW** と互換性がありません。  
  
 詳細については、「[Visual C\+\+ の言語リファレンス](../Topic/Visual%20C++%20Language%20Reference%20\(C++-CX\).md)」を参照してください。  
  
## 必要条件  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)