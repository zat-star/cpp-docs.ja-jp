---
title: "コンパイラ エラー C2030 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2030"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2030"
ms.assetid: 5806cead-64df-4eff-92de-52c9a3f5ee62
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C2030
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アクセシビリティが 'protected private' であるデストラクターは、'sealed' として宣言されたクラスのメンバーになることはできません  
  
 `sealed` として宣言された Windows ランタイム クラスは、protected private デストラクターを持つことはできません。  sealed 型では、パブリック仮想デストラクターとプライベート非仮想デストラクターだけが許可されています。  詳細については、「[Ref クラスと構造体](../Topic/Ref%20classes%20and%20structs%20\(C++-CX\).md)」を参照してください。  
  
 このエラーを解決するには、デストラクターのアクセシビリティを変更します。