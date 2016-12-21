---
title: "ホスト ウィンドウを再利用できますか? | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ホスト ウィンドウ"
ms.assetid: bcd08ab1-cfcf-49e3-b4e8-ac134d141005
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ホスト ウィンドウを再利用できますか?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ホスト ウィンドウの再利用はお勧めできません。  コードの保全性を保証するには、ホスト ウィンドウの有効期間として 1 つのコントロールの有効期間を設定する必要があります。  
  
## 参照  
 [コントロール コンテインメント : Q & A 集](../atl/atl-control-containment-faq.md)