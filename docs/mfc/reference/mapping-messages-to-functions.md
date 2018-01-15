---
title: "関数へのメッセージの割り当て |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.mapping.msg.function
dev_langs: C++
helpviewer_keywords:
- Windows messages [MFC], adding message handlers
- message maps [MFC], mapping messages to functions
ms.assetid: a7727a62-f638-4b20-b7f5-131f47200d6a
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ad36b249e601e15e25f32ef1ef7e6d5a28874cf1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="mapping-messages-to-functions"></a>関数へのメッセージの割り当て
プロパティ ウィンドウでは、アプリケーションのリソースによって生成されたメッセージをメッセージ ハンドラー (MFC のユーザー インターフェイス クラスのメンバー関数) をバインドします。 使用する[MFC メッセージ マップ](../../mfc/messages-and-commands-in-the-framework.md)バインドを作成します。  
  
 クラス ビューを使用して、framework のクラスのいずれかから派生する新しいクラスを作成するときに、自動的に機能とクラス ヘッダー (.h) と実装 (.cpp) でファイルを指定することです。  
  
> [!NOTE]
>  メッセージを処理しないする新しいクラスを追加するには、テキスト エディターで直接、クラスを作成します。  
  
### <a name="to-define-or-remove-a-message-handler-using-the-properties-window"></a>定義または [プロパティ] ウィンドウを使用してメッセージ ハンドラーを削除します。  
  
1.  クラス ビューでは、クラスをクリックします。  
  
2.  [プロパティ] ウィンドウ、**メッセージ**ボタンをクリックします。  
  
    > [!NOTE]
    >  **メッセージ**クラス ビュー、または、ソース ウィンドウ内をクリックすると、いずれかのクラス名を選択すると、ボタンは使用できます。  
  
     プロジェクトには、メッセージのハンドラーがある、メッセージの横にある右の列に、ハンドラーの名前が表示されます。  
  
3.  プロパティ ウィンドウに、ハンドラーの名前を表示するには、右側の列のセルをクリックしてハンドラー、メッセージがない場合は、\<追加 >*HandlerName*です。 (たとえば、`WM_TIMER`メッセージ ハンドラーを提案\<追加 >`OnTimer`)。  
  
4.  関数のスタブ コードを追加する推奨される名前をクリックします。  
  
5.  メッセージ ハンドラーを編集するには、クラス ビューでメッセージをダブルクリックし、[ソース] ウィンドウでコードを編集します。  
  
 メッセージ ハンドラーを削除するには、右側の列のハンドラをダブルクリックしを選択\<削除 >*HandlerName*です。 関数のコードをコメント アウトします。  
  
## <a name="see-also"></a>参照  
 [MFC メッセージ ハンドラー](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [コード ウィザードによる機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [クラスの追加](../../ide/adding-a-class-visual-cpp.md)   
 [メンバー関数の追加](../../ide/adding-a-member-function-visual-cpp.md)   
 [メンバー変数の追加](../../ide/adding-a-member-variable-visual-cpp.md)   
 [仮想関数のオーバーライド](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [ダイアログ ボックス コントロールのイベント ハンドラーの追加](../../windows/adding-event-handlers-for-dialog-box-controls.md)   
 [クラス各部へ](../../ide/navigating-the-class-structure-visual-cpp.md)
