---
title: "MFC で使われているコールバック関数 | Microsoft Docs"
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
  - "vc.mfc.functions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コールバック関数"
  - "コールバック関数, MFC"
  - "関数 [C++], コールバック"
  - "MFC, コールバック関数"
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC で使われているコールバック関数
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

3 個のコールバック関数は、Microsoft Foundation Class ライブラリに表示されます。  [CDC::EnumObjects](../Topic/CDC::EnumObjects.md)に渡されるコールバック関数、[CDC::GrayString](../Topic/CDC::GrayString.md)と [CDC::SetAbortProc](../Topic/CDC::SetAbortProc.md) の説明は、このトピックに従います。  コールバック関数の一般的な使用方法では、これらのメンバー関数の解説セクションを参照してください。  例外のコールバックの境界を越えてスローすることができないため、すべてのコールバック関数は、Windows に対する戻る前に MFC 例外をフックする必要があります。  例外に関する詳細については、記事 [例外](../../mfc/exception-handling-in-mfc.md)を参照します。  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)