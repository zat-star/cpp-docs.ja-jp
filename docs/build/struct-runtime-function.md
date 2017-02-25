---
title: "構造体 RUNTIME_FUNCTION | Microsoft Docs"
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
ms.assetid: 84386527-d3aa-41c5-871d-78e3e1913704
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 構造体 RUNTIME_FUNCTION
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

テーブルベースの例外処理を行う場合、スタック領域の割り当てや別の関数 \(非リーフ関数など\) の呼び出しを実行するすべての関数用のテーブル エントリが必要となります。  関数テーブル エントリの形式は次のとおりです。  
  
|||  
|-|-|  
|ULONG|関数の開始アドレス|  
|ULONG|関数の終了アドレス|  
|ULONG|アンワインド情報のアドレス|  
  
 RUNTIME\_FUNCTION 構造体は、メモリに DWORD でアライメントされる必要があります。  すべてのアドレスは、イメージからの相対アドレス、つまり、関数テーブル エントリを含むイメージの開始アドレスからの 32 ビットのオフセット アドレスです。  これらのエントリは並べ替えられ、PE32\+ イメージの .pdata セクションに配置されます。  動的に生成された関数 \[JIT コンパイラ\] の場合、これらの関数をサポートするランタイムは、この情報をオペレーティング システムに提供するために RtlInstallFunctionTableCallback または RtlAddFunctionTable を使用する必要があります。  この処理に失敗すると、例外処理およびプロセスのデバッグに対する信頼性が失われます。  
  
## 参照  
 [例外処理とデバッガー サポートのためのアンワインド データ](../build/unwind-data-for-exception-handling-debugger-support.md)