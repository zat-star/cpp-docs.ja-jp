---
title: "コンパイラ エラー C2865 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2865"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2865"
ms.assetid: 973eb6a0-c99a-4d25-b3e5-fe0539794d77
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2865
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数' : handle\_or\_pointer の比較が正しくありません  
  
 [Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md) 型または [\_\_gc](../Topic/__gc.md) 型への参照が等値かどうかだけを比較して、同じオブジェクトを参照 \(\=\=\) しているか、異なるオブジェクトを参照 \(\!\=\) しているかを確認できます。  
  
 .NET ランタイムではマネージ オブジェクトが常に移動され、テストの結果が変化する可能性があるため、順序付のために参照を比較できません。