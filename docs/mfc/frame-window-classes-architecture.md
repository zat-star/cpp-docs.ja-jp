---
title: "フレーム ウィンドウ クラス (アーキテクチャ) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.frame
dev_langs: C++
helpviewer_keywords: frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f1caf8e4b93e18675b810ced962df6e8adcf521a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="frame-window-classes-architecture"></a>フレーム ウィンドウ クラス (アーキテクチャ)
ドキュメント/ビュー アーキテクチャでは、フレーム ウィンドウは、ビュー ウィンドウを持つウィンドウです。 サポート コントロール バーが割り当てられています。  
  
 マルチ ドキュメント インターフェイス (MDI) アプリケーションでは、メイン ウィンドウはから派生`CMDIFrameWnd`です。 直接ドキュメントのフレームが含まれる、`CMDIChildWnd`オブジェクト。 `CMDIChildWnd`オブジェクトでは、ドキュメントのビューに含めることです。  
  
 派生したメイン ウィンドウで、シングル ドキュメント インターフェイス (SDI) アプリケーションで、 `CFrameWnd`、現在のドキュメントのビューが含まれています。  
  
 [CFrameWnd](../mfc/reference/cframewnd-class.md)  
 SDI アプリケーションのメイン フレーム ウィンドウの基本クラス。 またの基本クラスの他のすべてのフレーム ウィンドウ クラス。  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
 MDI アプリケーションのメイン フレーム ウィンドウの基本クラス。  
  
 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
 MDI アプリケーションのドキュメント フレーム ウィンドウの基底クラス。  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 サーバー ドキュメントを一括で編集するときに、ビューのフレーム ウィンドウを提供します。  
  
## <a name="see-also"></a>参照  
 [クラスの概要](../mfc/class-library-overview.md)

