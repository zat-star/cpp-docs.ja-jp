---
title: "_emit 疑似命令 | Microsoft Docs"
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
  - "_emit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_emit 疑似命令"
  - "バイト定義 (インライン アセンブリ)"
ms.assetid: 004c48f3-364c-4e82-9a51-e326f9cc7b2b
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _emit 疑似命令
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 **\_emit** の擬似指示が期限内のテキスト区分の現在の職位で 1 件のバイトを定義します。  **\_emit** の擬似ついては MASM の [DB](../../assembler/masm/db.md) の指令に似ています。  
  
 次のコード片はにバイト 0x4A、0x43 と 0x4B を設定します:  
  
```  
#define randasm __asm _emit 0x4A __asm _emit 0x43 __asm _emit 0x4B  
 .  
 .  
 .  
__asm {  
     randasm  
     }  
```  
  
> [!CAUTION]
>  `_emit` が登録を変更すると、注文をコンパイル最適化のアプリケーションが生成された場合は、コンパイラは、登録が影響を受けるかを決定することはできません。  たとえば、`_emit` が **rax** の登録を変更する指示を生成し、コンパイラに **rax** が変更された場合は知りません。  コンパイラにインラインなアセンブラー コードを実行した後で、そのレジスターの値に関する間違った前提条件を行う場合があります。  したがって、それらのアプリケーションは、実行するときに予測不可能な動作は次のことがあります。  
  
 **END Microsoft 固有**  
  
## 参照  
 [\_\_asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)