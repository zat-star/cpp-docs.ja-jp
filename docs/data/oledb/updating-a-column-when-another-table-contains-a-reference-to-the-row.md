---
title: "行への参照が別のテーブルにある場合に列を更新する方法 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "行セット, 列の更新"
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 行への参照が別のテーブルにある場合に列を更新する方法
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

行のどの列に変更があったかを検出できるプロバイダーもありますが、ほとんどのプロバイダーは検出できません。  そのため、更新を試みている行への参照がある場合は、列を更新するとエラーになることがあります。  この問題を解決するには、変更する列だけを含む別のアクセサーを作成します。  そのアクセサーの番号を `SetData` に渡します。  
  
## 参照  
 [アクセサーの使用](../../data/oledb/using-accessors.md)