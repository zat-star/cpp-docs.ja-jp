---
title: "イベント ハンドラー (Visual C) を追加する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.eventhandler.overview
dev_langs: C++
helpviewer_keywords:
- event handlers, adding
- properties [Visual Studio], MSBuild
- MSBuild, properties
ms.assetid: 050bebf0-a9e0-474b-905c-796fe5ac8fc3
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f9a5380bf335a13bbf7b2f54840c9d1160187167
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="adding-an-event-handler-visual-c"></a>イベント ハンドラーの追加 (Visual C++)
リソース エディターで、新しいイベント ハンドラーを追加または編集 ダイアログ ボックス コントロールを使用して、既存のイベント ハンドラー、[イベント ハンドラー ウィザード](../ide/event-handler-wizard.md)です。  
  
 イベントを追加すると、ダイアログ ボックスを使用して、実装するクラス、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。 ダイアログ ボックス クラス以外のクラスにイベントを追加する場合は、イベント ハンドラー ウィザードを使用します。  
  
### <a name="to-add-an-event-handler-to-a-dialog-box-control"></a>ダイアログ ボックス コントロールにイベント ハンドラーを追加するには  
  
1.  ダイアログ ボックスのリソースをダブルクリックして[リソース ビュー](../windows/resource-view-window.md)でコントロールを含むダイアログ ボックスのリソースを開く、[ダイアログ エディター](../windows/dialog-editor.md)です。  
  
2.  通知イベントを処理するコントロールを右クリックします。  
  
3.  ショートカット メニューをクリックして**イベント ハンドラーの追加**イベント ハンドラー ウィザードを表示します。  
  
4.  イベントを選択して、**メッセージの種類**ボックスで選択されたクラスに追加する、**クラス リスト**ボックス。  
  
5.  既定の名前を受け入れ、**関数ハンドラー名**ボックス、または任意の名前を指定します。  
  
6.  をクリックして**の追加と編集**をプロジェクトに、イベント ハンドラーを追加し、適切なイベント ハンドラーのコードを追加する新しい関数をテキスト エディターを開きます。  
  
     場合は、選択したメッセージの種類に選択したクラスのイベント ハンドラーは既に**の追加と編集**が使用できないと**コードを編集**は使用できます。 をクリックして**コード編集**で既存の関数のテキスト エディターを開きます。  
  
 またはからのイベント ハンドラーを追加することができます、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。 参照してください[ダイアログ ボックス コントロールのイベント ハンドラーを追加する](../windows/adding-event-handlers-for-dialog-box-controls.md)詳細についてはします。  
  
## <a name="see-also"></a>参照  
 [コード ウィザードによる機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [クラスの追加](../ide/adding-a-class-visual-cpp.md)   
 [メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md)   
 [メンバー関数の追加](../ide/adding-a-member-function-visual-cpp.md)   
 [MFC メッセージ ハンドラー](../mfc/reference/adding-an-mfc-message-handler.md)   
 [クラス各部へ](../ide/navigating-the-class-structure-visual-cpp.md)