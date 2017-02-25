---
title: "リフレクション メッセージ用のメッセージ ハンドラーの定義 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.defining.msg.msghandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "メッセージ処理, リフレクション メッセージ"
  - "メッセージ, リフレクション"
ms.assetid: 5a403528-58c5-46e7-90d5-4a77f0ab9b9c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# リフレクション メッセージ用のメッセージ ハンドラーの定義
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

新しい MFC コントロール クラスを作成したら、そのクラスのメッセージ ハンドラーを定義できます。  リフレクション メッセージ ハンドラーを設定すると、メッセージを親が受信する前に、コントロール クラス自身でメッセージを処理できます。  MFC の [CWnd::SendMessage](../Topic/CWnd::SendMessage.md) 関数を使用して、コントロールから親ウィンドウにメッセージを送信できます。  
  
 たとえば、この機能を使用すると、自身を再描画するリスト ボックスを作成できるため、親ウィンドウで描画する \(オーナー描画\) 必要がありません。  リフレクション メッセージの詳細については、「[反映されたメッセージの処理方法](../../mfc/handling-reflected-messages.md)」を参照してください。  
  
 同じ機能を持つ [ActiveX コントロール](../../mfc/activex-controls-on-the-internet.md)を作成するには、ActiveX コントロール用のプロジェクトを作成する必要があります。  
  
> [!NOTE]
>  以下で説明するように、\[プロパティ\] ウィンドウを使用して ActiveX コントロール用のリフレクション メッセージ \(OCM\_*Message*\) を追加することはできません。  メッセージは手動で追加する必要があります。  
  
### \[プロパティ\] ウィンドウでリフレクション メッセージのメッセージ ハンドラーを定義するには  
  
1.  リスト コントロール、rebar コントロール、ツール バー コントロール、ツリー コントロールなどのコントロールを MFC プロジェクトに追加します。  
  
2.  クラス ビューで、コントロール クラスの名前をクリックします。  
  
3.  [&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)の **\[クラス名\]** ボックスの一覧に、コントロール クラスの名前が表示されます。  
  
4.  \[メッセージ\] をクリックして、コントロールに追加できる Windows メッセージを表示します。  
  
5.  \[プロパティ\] ウィンドウのメッセージの一覧を下にスクロールして、見出し \[反映済み\] を表示します。  または、**\[カテゴリ\]** をクリックしてビューを縮小し、見出し \[反映済み\] を表示します。  
  
6.  ハンドラーを定義するリフレクション メッセージを選択します。  リフレクション メッセージに等号 \(\=\) が付けられます。  
  
7.  addHandlerName\>としてハンドラーの名前を表示するには、プロパティ ウィンドウの右の列のセルを \<クリックします。\(たとえば、**\=WM\_CTLCOLOR** のメッセージ ハンドラーが追加 \<されます**CtlColor**を\>提案します。  
  
8.  使用する名前をクリックします。  プロジェクトにハンドラーが追加されます。  
  
     追加したメッセージ ハンドラーの名前が、リフレクション メッセージ ウィンドウの右の列に表示されます。  
  
9. メッセージ ハンドラーを編集または削除するには、手順 4. ～ 7. を繰り返します。  編集または削除するハンドラー名を含むセルをクリックし、適切なタスクをクリックしてください。  
  
## 参照  
 [関数へのメッセージの割り当て](../Topic/Mapping%20Messages%20to%20Functions.md)   
 [コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [クラスの追加](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)   
 [メンバー関数の追加](../../ide/adding-a-member-function-visual-cpp.md)   
 [メンバー変数の追加](../../ide/adding-a-member-variable-visual-cpp.md)   
 [仮想関数のオーバーライド](../Topic/Overriding%20a%20Virtual%20Function%20\(Visual%20C++\).md)   
 [MFC メッセージ ハンドラー](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [クラス各部へのジャンプ](../../ide/navigating-the-class-structure-visual-cpp.md)