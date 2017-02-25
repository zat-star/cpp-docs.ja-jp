---
title: "式ステートメント | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "式ステートメント"
  - "ステートメント, 式"
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 式ステートメント
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

式ステートメントを使用すると、式が評価されます。  式ステートメントの結果として、制御が移動したり、イテレーションが発生したりすることはありません。  
  
 式ステートメントの構文は、次のように、単純です。  
  
## 構文  
  
```  
[expression ] ;  
```  
  
## 解説  
 式ステートメント内の式はすべて評価され、次のステートメントが実行される前にすべての副作用が完了します。  最も一般的に使用される式ステートメントは、代入と関数呼び出しです。  式は省略可能であるため、セミコロンだけを記述しても、[null](../Topic/Null%20Statement.md) ステートメントと呼ばれる空の式ステートメントと見なされます。  
  
## 参照  
 [C\+\+ ステートメントの概要](../cpp/overview-of-cpp-statements.md)