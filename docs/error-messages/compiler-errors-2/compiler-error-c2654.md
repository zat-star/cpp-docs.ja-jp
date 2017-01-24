---
title: "コンパイラ エラー C2654 | Microsoft Docs"
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
  - "C2654"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2654"
ms.assetid: ca7de1bd-576b-40bf-96fc-a91984827d20
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2654
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : メンバー関数の外でメンバーがアクセスされています。  
  
 宣言内でメンバーにアクセスしています。  メンバー データにアクセスできるのは、メンバー関数からだけです。  
  
 このエラーは、宣言で変数を初期化しようとしたときに発生する場合があります。  宣言内での変数の初期化にはコンストラクターを使用してください。