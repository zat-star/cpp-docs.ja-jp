---
title: "SDI と MDI | Microsoft Docs"
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
  - "フレーム ウィンドウ, MDI アプリケーション"
  - "フレーム ウィンドウ, SDI アプリケーション"
  - "MDI, および SDI"
  - "MFC, ウィンドウ"
  - "シングル ドキュメント インターフェイス (SDI), アプリケーション"
ms.assetid: bb7239d9-4759-4f63-bfff-44a04b48c067
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# SDI と MDI
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC はシングル ドキュメント インターフェイス \(SDI\) および Multiple\-Document Interface \(MDI\) アプリケーションの両方を使用するのは簡単です。  
  
 SDI アプリケーションは 1 個の開いているドキュメント フレーム ウィンドウを一度に割り当てます。  MDI アプリケーションでは、複数のドキュメント フレーム ウィンドウがアプリケーションの同じインスタンスで開くことができます。  MDI アプリケーションにフレーム ウィンドウ自体である複数の MDI 子ウィンドウを開くことができるウィンドウが別のドキュメントを含む各です。  アプリケーションによっては、子ウィンドウはチャート ウィンドウやスプレッドシート ウィンドウなどの別の型にすることもできます。  その場合は、メニュー バーは、異なる種類の MDI 子ウィンドウがアクティブになったときに変更できます。  
  
> [!NOTE]
>  Windows 95 の下で、アプリケーションは、オペレーティング システムが「ドキュメント中央揃え」ビューを採用しているため、一般に SDI です。  
  
 詳細については、「[ドキュメント、ビュー、およびフレームワーク](../mfc/documents-views-and-the-framework.md)」を参照してください。  
  
## 参照  
 [クラスを使用した Windows アプリケーションの作成](../Topic/Using%20the%20Classes%20to%20Write%20Applications%20for%20Windows.md)