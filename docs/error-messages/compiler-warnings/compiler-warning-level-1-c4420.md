---
title: "コンパイラの警告 (レベル 1) C4420 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4420"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4420"
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 1) C4420
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator' : 演算子は使用できません、'operator' を代わりに使用します ; ランタイム チェックは中途終了される可能性があります。  
  
 この警告が表示されるのは、[\/RTCv](../../build/reference/rtc-run-time-error-checks.md) \(ベクターの new\/delete チェック\) を使用していて、ベクター形式が見つからない場合です。  この場合は、非ベクター形式が使用されます。  
  
 \/RTCv を正常に動作させるには、ベクター構文が使用された場合に、コンパイラが常にベクター形式の [new](../../cpp/new-operator-cpp.md)\/[delete](../../cpp/delete-operator-cpp.md) を呼び出す必要があります。