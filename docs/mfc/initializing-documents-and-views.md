---
title: "ドキュメントとビューの初期化 |Microsoft ドキュメント"
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
- initializing documents [MFC]
- documents [MFC], initializing
- views [MFC], initializing
- initializing objects [MFC], document objects
- initializing views [MFC]
ms.assetid: 33cb8643-8a16-478c-bc26-eccc734e3661
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f80d870f9804454dc652fdda00f34fcdb7a52062
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="initializing-documents-and-views"></a>ドキュメントとビューの初期化
ドキュメント クラスは、両方の方法をサポートする必要がありますので、2 つの異なる方法でドキュメントが作成されます。 最初に、ユーザーは、ファイルの新しいコマンドを使用して新しい空のドキュメントを作成することができます。 その場合は、オーバーライドでドキュメントの初期化、[でも実質的](../mfc/reference/cdocument-class.md#onnewdocument)クラスのメンバー関数[CDocument](../mfc/reference/cdocument-class.md)です。 第二に、ユーザーは、ファイルから内容の読み取りが新しいドキュメントを作成するのに、[ファイル] メニュー、開いているコマンドを使用できます。 その場合は、オーバーライドでドキュメントの初期化、[かまいません](../mfc/reference/cdocument-class.md#onopendocument)クラスのメンバー関数**CDocument**です。 両方の初期化が同じ場合は、両方のオーバーライドから共通のメンバー関数を呼び出すことができますか`OnOpenDocument`呼び出すことができます`OnNewDocument`をクリーンなドキュメントを初期化して開く操作を完了します。  
  
 ビューは、ドキュメントの作成後に作成されます。 ビューを初期化するために最適な時期は、ドキュメント、フレーム ウィンドウとビューを作成するために、フレームワークが完了した後です。 オーバーライドすることで、ビューを初期化することができます、[フィルターと並べ替え順序](../mfc/reference/cview-class.md#oninitialupdate)のメンバー関数[CView](../mfc/reference/cview-class.md)です。 再初期化または調整する必要がある場合は、ドキュメントの変更されるたびに、オーバーライドすることができます[OnUpdate](../mfc/reference/cview-class.md#onupdate)です。  
  
## <a name="see-also"></a>参照  
 [ドキュメントとビューの初期化と後処理](../mfc/initializing-and-cleaning-up-documents-and-views.md)

