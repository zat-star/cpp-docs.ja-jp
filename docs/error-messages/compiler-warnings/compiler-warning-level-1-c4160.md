---
title: "コンパイラの警告 (レベル 1) C4160 | Microsoft Docs"
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
  - "C4160"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4160"
ms.assetid: a9610cb7-cac4-4a74-8b4e-049030ebb92b
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4160
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\#pragma**   
 ***pragma* \(pop,...\): 以前にプッシュされた次の識別子が見つかりません: '**   
 ***identifier* '**  
  
 ソース コードのプラグマ ステートメントで、プッシュされていない識別子のポップを試みています。 この警告を回避するには、ポップされている識別子が正しくプッシュされていることを確認してください。  
  
 次の例では、C4160 エラーが生成されます。  
  
```  
// C4160.cpp // compile with: /W1 #pragma pack(push) #pragma pack(pop, id)   // C4160 // use identifier when pushing to resolve the warning // #pragma pack(push, id) int main() { }  
```