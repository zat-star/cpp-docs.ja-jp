---
title: "フレーム ウィンドウ クラス (アーキテクチャ) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.frame"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "フレーム ウィンドウ クラス, ドキュメント/ビュー アーキテクチャ"
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# フレーム ウィンドウ クラス (アーキテクチャ)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ドキュメント\/ビュー アーキテクチャでは、フレーム ウィンドウでビュー ウィンドウを含むウィンドウです。  また、付随するコントロール バーを持つことができます。  
  
 マルチ ドキュメント インターフェイス \(MDI\) アプリケーションでは、メイン ウィンドウが `CMDIFrameWnd`から派生されます。  これは間接的に `CMDIChildWnd` オブジェクトである文書のフレームが含まれています。  `CMDIChildWnd` は、含まれているドキュメントのビューがあります。  
  
 シングル ドキュメント インターフェイス \(SDI \(SDI\) アプリケーションのメイン ウィンドウ、`CFrameWnd`からの派生は、現在のドキュメントのビューが含まれます。  
  
 [CFrameWnd](../mfc/reference/cframewnd-class.md)  
 SDI アプリケーションのメイン フレーム ウィンドウの基本クラスです。  他のすべてのフレーム ウィンドウ クラスの基本クラスです。  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
 MDI アプリケーションのメイン フレーム ウィンドウの基本クラスです。  
  
 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
 MDI アプリケーションのドキュメント フレーム ウィンドウの基本クラスです。  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 サーバー ドキュメントが編集されているビューにフレーム ウィンドウを指定します。  
  
## 参照  
 [クラスの概要](../mfc/class-library-overview.md)