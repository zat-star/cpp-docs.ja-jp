---
title: "廃止された呼び出し規約 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__fortran"
  - "__pascal"
  - "__syscall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__fortran キーワード [C++]"
  - "__pascal キーワード [C++]"
  - "__syscall キーワード [C++]"
  - "呼び出し規約, 廃止"
  - "WINAPI"
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 廃止された呼び出し規約
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 **\_\_pascal**、**\_\_fortran**、および **\_\_syscall** の呼び出し規約はサポートされなくなりました。  サポートされる呼び出し規約および適切なリンカー オプションの 1 つを使用して、それらの機能をエミュレートできます。  
  
 WINDOWS.H は、ターゲットの適切な呼び出し規約に変換する **WINAPI** マクロをサポートするようになりました。  以前に **PASCAL** または **\_\_far \_\_pascal** を使用した場所で、**WINAPI** を使用します。  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [引数の渡し規則と名前付け規則](../Topic/Argument%20Passing%20and%20Naming%20Conventions.md)