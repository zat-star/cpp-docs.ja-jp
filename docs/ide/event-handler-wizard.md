---
title: "イベント ハンドラー ウィザード |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.eventhandler.overview
dev_langs:
- C++
helpviewer_keywords:
- Event Handler Wizard [C++]
ms.assetid: af8e1835-94b1-4d9a-b353-c519e011d3a1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3ccb80add8a98b9251a7ccbb5c85bf98b610a22e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="event-handler-wizard"></a>イベント ハンドラー ウィザード
このウィザードでは、任意のクラスにダイアログ ボックス コントロールのイベント ハンドラーを追加します。 イベント ハンドラーを追加する場合、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、ダイアログ ボックスを実装するクラスにのみ追加することができます。 参照してください[ダイアログ ボックス コントロールのイベント ハンドラーを追加する](../windows/adding-event-handlers-for-dialog-box-controls.md)詳細についてはします。  
  
 **コマンド名**  
 イベント ハンドラーが追加対象となる、選択したコントロールを識別します。 このボックスは使用できません。  
  
 **メッセージの種類**  
 選択したコントロールの現在の使用可能なメッセージ ハンドラーの一覧を表示します。  
  
 **関数ハンドラー名**  
 イベントを処理する追加の関数の名前を表示します。 既定では、名前はメッセージの種類と、コマンドを先頭に"On"が付いたに基づいています。 たとえば、ボタンと呼ばれる`IDC_BUTTON1`、メッセージの種類`BN_CLICKED`関数ハンドラーの名前を表示`OnBnClickedButton1`です。  
  
 **クラスの一覧**  
 イベント ハンドラーを追加することができます、使用可能なクラスを表示します。 選択されているダイアログ ボックスのクラスは、赤で表示されます。  
  
 **ハンドラーの説明**  
 選択した項目の説明を**メッセージの種類**ボックス。 このボックスは使用できません。  
  
 **追加し、編集**  
 選択したクラスまたはオブジェクト をメッセージ ハンドラーを追加し、コントロール通知ハンドラー コードを追加できるようにし、新しい関数をテキスト エディターで開きます。  
  
 **コードを編集します。**  
 テキスト エディターで、選択した既存の関数が開き、追加またはコントロール通知ハンドラー コードを編集することができます。  
  
## <a name="see-also"></a>参照  
 [イベント ハンドラーを追加します。](../ide/adding-an-event-handler-visual-cpp.md)