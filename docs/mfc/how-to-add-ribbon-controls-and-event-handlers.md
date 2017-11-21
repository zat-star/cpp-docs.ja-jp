---
title: "方法: リボン コントロールとイベント ハンドラーを追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- event handlers [MFC], adding
- ribbon controls [MFC], adding
ms.assetid: b31f25bc-ede7-49c3-9e3c-dffe4e174a69
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7623a254e26cd7f1d09d7906fb4a9b192f46183e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-add-ribbon-controls-and-event-handlers"></a>方法: リボン コントロールとイベント ハンドラーを追加する
リボン コントロールは、ボタンやコンボ ボックス、パネルに追加するなどの要素です。 パネルは、関連するコントロールのグループを表示するリボン バーの領域です。  
  
 このトピックでは、リボン デザイナーを開く、ボタンの追加"Hello World"を表示するイベントをリンクします。  
  
### <a name="to-open-the-ribbon-designer"></a>リボン デザイナーを開く  
  
1.  Visual Studio での**ビュー**  メニューのをクリックして**リソース ビュー**です。  
  
2.  **リソース ビュー**、デザイン画面に表示するリボン リソースをダブルクリックします。  
  
### <a name="to-add-a-button-and-an-event-handler"></a>ボタンと、イベント ハンドラーを追加するには  
  
1.  **ツールバー**、 をクリックして**ボタン**パネルをデザイン画面にドラッグします。  
  
2.  ボタンを右クリックし、をクリックして**イベント ハンドラーの追加**です。  
  
3.  **イベント ハンドラー ウィザード**、既定の設定を確認し、クリックして**の追加し、編集**です。 詳細については、次を参照してください。[イベント ハンドラー ウィザード](../ide/event-handler-wizard.md)です。  
  
4.  コード エディターで、ハンドラー関数に次のコードを追加します。  
  
 ```  
    MessageBox((LPCTSTR)L"Hello World");

 ```  
  
## <a name="see-also"></a>関連項目  
 [RibbonGadgets サンプル: リボン ガジェット アプリケーション](../visual-cpp-samples.md)   
 [リボン デザイナー (MFC)](../mfc/ribbon-designer-mfc.md)

