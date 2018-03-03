---
title: "SDI と MDI |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], SDI applications
- frame windows [MFC], MDI applications
- MFC, windows
- single document interface (SDI) [MFC], applications
- MDI [MFC], vs. SDI
ms.assetid: bb7239d9-4759-4f63-bfff-44a04b48c067
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7109651bc250f83d8ee7e162b647ef54dd5308d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="sdi-and-mdi"></a>SDI と MDI
MFC では、シングル ドキュメント インターフェイス (SDI) とマルチ ドキュメント インターフェイス (MDI) アプリケーションの両方を簡単に処理します。  
  
 SDI アプリケーションは、一度に 1 つだけ開いているドキュメント フレーム ウィンドウを許可します。 MDI アプリケーションには、複数のドキュメントのフレーム ウィンドウをアプリケーションの同じインスタンスで開くことができるようにします。 MDI アプリケーションでは、個別のドキュメントに含まれる各ウィンドウ内、複数の MDI フレーム ウィンドウ自体は、子ウィンドウを開くがします。 一部のアプリケーションで、グラフ ウィンドウやスプレッドシート ウィンドウなどのさまざまな種類の子ウィンドウができます。 その場合は、さまざまな種類の MDI 子ウィンドウがアクティブ化すると、メニュー バーは変更できます。  
  
> [!NOTE]
>  Windows 95 以降では、アプリケーションは通常、SDI、オペレーティング システムは、「ドキュメント中心」ビューを採用しているためです。  
  
 詳細については、次を参照してください。[ドキュメント、ビュー、およびフレームワーク](../mfc/documents-views-and-the-framework.md)です。  
  
## <a name="see-also"></a>参照  
 [クラスを使用した Windows アプリケーションの作成](../mfc/using-the-classes-to-write-applications-for-windows.md)
