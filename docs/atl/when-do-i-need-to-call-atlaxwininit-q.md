---
title: "AtlAxWinInit はいつ呼び出しますか? | Microsoft Docs"
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
  - "AtlAxWinInit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AtlAxWinInit メソッド"
ms.assetid: 080b9cfe-d85a-4439-a9e9-ab3966ebaa8e
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AtlAxWinInit はいつ呼び出しますか?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[AtlAxWinInit](../Topic/AtlAxWinInit.md) \(いくつかのカスタム ウィンドウ メッセージ\) と **"AtlAxWin80"** のウィンドウ クラスを登録して、ホスト ウィンドウを作成する前にこの関数を呼び出す必要があります。  ただし、これらを使用する \(クラス\) と、ホスト API、この関数を呼び出すため、この関数を明示的に呼び出すする必要はありません。  この関数を複数回呼び出すことに悪影響がありません。  詳細については、[ATL のコントロール ホスト API は何ですか。](../atl/what-is-the-atl-control-hosting-api-q.md)を参照してください。  
  
## 参照  
 [AtlAxWinTerm はいつ呼び出しますか?](../atl/when-do-i-need-to-call-atlaxwinterm-q.md)   
 [コントロール コンテインメント : Q & A 集](../atl/atl-control-containment-faq.md)