---
title: "ドキュメント ビューの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- documents [MFC], creating
- views [MFC], and frame windows
- views [MFC], creating
- tables [MFC]
- MFC, views
- document/view architecture [MFC], creating document/view
- object creators
- MFC, documents
- tables [MFC], objects each MFC object creates
ms.assetid: bda14f41-ed50-439d-af9e-591174e7dd64
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e98f6e4b1b9ecd5848c2701043aa9b0b7dcea7d4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="documentview-creation"></a>ドキュメントおよびビューの作成
フレームワークの実装を提供する、`New`と**開く**コマンド (など) を使って、**ファイル**メニュー。 新しいドキュメントおよび関連するビューとフレーム ウィンドウの作成は、アプリケーション オブジェクト、ドキュメント テンプレート、新しく作成されたドキュメント、および新しく作成されたフレーム ウィンドウの連係です。 次の表では、どのオブジェクトの作成内容をまとめたものです。  
  
### <a name="object-creators"></a>オブジェクトの作成内容  
  
|Creator|作成します。|  
|-------------|-------------|  
|Application オブジェクト|ドキュメント テンプレート|  
|ドキュメント テンプレート|ドキュメント|  
|ドキュメント テンプレート|フレーム ウィンドウ|  
|フレーム ウィンドウ|表示|  
  
## <a name="see-also"></a>関連項目  
 [ドキュメント テンプレートとドキュメント/ビューの作成手順](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [ドキュメント テンプレートの作成](../mfc/document-template-creation.md)   
 [MFC オブジェクト間の関係](../mfc/relationships-among-mfc-objects.md)   
 [新しいドキュメント、ウィンドウ、ビューの作成](../mfc/creating-new-documents-windows-and-views.md)

