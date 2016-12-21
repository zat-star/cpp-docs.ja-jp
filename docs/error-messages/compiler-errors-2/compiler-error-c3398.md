---
title: "コンパイラ エラー C3398 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3398"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3398"
ms.assetid: 26f8c8a4-526f-415b-8047-155c5cd4f180
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3398
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator': 'function\_signature' から 'function\_pointer' に変換できません。 ソース式は関数シンボルでなければなりません  
  
 **\/clr** を使用してコンパイルするときに、[\_\_clrcall](../../cpp/clrcall.md) 呼び出し規則が指定されていないと、コンパイラは各関数に対して、ネイティブ エントリ ポイントとマネージ エントリ ポイントという 2 つのエントリ ポイント \(アドレス\) を生成します。  
  
 既定では、コンパイラはネイティブ エントリ ポイントを返しますが、場合によっては、マネージ エントリ ポイントが必要な場合があります \(たとえば、`__clrcall` 関数ポインターにアドレスを 割り当てる場合など\)。 割り当てでコンパイラが確実にマネージ エントリ ポイントを選択するためには、右辺を関数シンボルにする必要があります。