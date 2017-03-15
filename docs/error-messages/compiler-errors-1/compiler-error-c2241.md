---
title: "コンパイラ エラー C2241 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2241"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2241"
ms.assetid: 2f4e2c2c-b95c-4afe-bbe0-4214cd39d140
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラ エラー C2241
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : メンバー アクセスは制限されています  
  
 コードが、プライベート メンバーまたはプロテクト メンバーにアクセスしようとしています。  
  
### 以下の可能性がある解決策を使って修正するには  
  
1.  メンバーのアクセス レベルを変更します。  
  
2.  アクセスする関数の `friend` としてメンバーを宣言します。