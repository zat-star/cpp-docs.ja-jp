---
title: "コンパイラ エラー C2129 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2129"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2129"
ms.assetid: 21a8223e-1d22-4baa-9ca1-922b7f751dd0
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2129
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

静的関数 'function' が宣言されましたが定義されていません。  
  
 定義されていない`static` 関数への前方参照が行われました。  
  
 `static` 関数は、ファイル スコープ内で定義する必要があります。  関数を別のファイル内で定義している場合は、`extern` として宣言してください。