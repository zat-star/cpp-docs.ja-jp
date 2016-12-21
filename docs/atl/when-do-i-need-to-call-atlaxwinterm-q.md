---
title: "AtlAxWinTerm はいつ呼び出しますか? | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "AtlAxWinTerm"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AtlAxWinTerm メソッド"
ms.assetid: 0088d494-2d8d-45b4-b582-2af726bd6cbd
caps.latest.revision: 12
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AtlAxWinTerm はいつ呼び出しますか?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[AtlAxWinTerm](../Topic/AtlAxWinTerm.md) のアンバインド **"AtlAxWin80"** のウィンドウ クラス。  すべての既存のホスト ウィンドウが破棄された後に \(既にホスト ウィンドウを作成する必要がある\) この関数を呼び出す必要があります。  この関数を呼び出して、ウィンドウ クラスは、プロセスが終了すると自動的に登録が解除されます。  
  
## 参照  
 [AtlAxWinInit はいつ呼び出しますか?](../atl/when-do-i-need-to-call-atlaxwininit-q.md)   
 [コントロール コンテインメント : Q & A 集](../atl/atl-control-containment-faq.md)