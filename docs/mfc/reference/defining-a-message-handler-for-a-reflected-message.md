---
title: "リフレクション メッセージ用のメッセージ ハンドラーを定義する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.defining.msg.msghandler
dev_langs:
- C++
helpviewer_keywords:
- messages, reflected
- message handling, reflected messages
ms.assetid: 5a403528-58c5-46e7-90d5-4a77f0ab9b9c
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 0033c75d351aa201a0c18e81395d764b9d45761b
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="defining-a-message-handler-for-a-reflected-message"></a>リフレクション メッセージ用のメッセージ ハンドラーの定義
新しい MFC コントロール クラスを作成した後は、そのメッセージ ハンドラーを定義できます。 リフレクション メッセージ ハンドラーは、親によってメッセージを受信する前に、独自のメッセージを処理するコントロール クラスを使用できます。 MFC を使用する[CWnd::SendMessage](../../mfc/reference/cwnd-class.md#sendmessage)を親ウィンドウに、コントロールからのメッセージを送信する関数。  
  
 (オーナー描画) を行うには、親ウィンドウに依存するのではなく、作成できますが、たとえば、この機能により、自身を再描画されるリスト ボックスを作成します。 リフレクション メッセージの詳細については、次を参照してください。[反映されたメッセージの処理](../../mfc/handling-reflected-messages.md)します。  
  
 作成する、 [ActiveX コントロール](../../mfc/activex-controls-on-the-internet.md)同じ機能を持つ ActiveX コントロールのプロジェクトを作成する必要があります。  
  
> [!NOTE]
>  リフレクション メッセージを追加することはできません (ocm _*メッセージ*) ActiveX 制御プロパティ ウィンドウを使用して以下のとおりです。 これらのメッセージを手動で追加する必要があります。  
  
### <a name="to-define-a-message-handler-for-a-reflected-message-from-the-properties-window"></a>[プロパティ] ウィンドウから反映されたメッセージのメッセージ ハンドラーを定義するには  
  
1.  リストなどのコントロール、rebar コントロール、ツールバー、またはツリー コントロールを MFC プロジェクトに追加します。  
  
2.  クラス ビューでは、コントロール クラスの名前をクリックします。  
  
3.  [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)にコントロールのクラス名が表示されます、**クラス名** ボックスの一覧です。  
  
4.  クリックして、**メッセージ**コントロールに追加できる Windows メッセージを表示するボタンをクリックします。  
  
5.  見出しが表示されるまでは、[プロパティ] ウィンドウ内のメッセージの一覧をスクロールして**反映済み**します。 または、クリックして、**カテゴリ**ボタンをクリックし、表示するビューを折りたたんで、**反映済み**見出しです。  
  
6.  リフレクションにハンドラーを定義するメッセージを選択します。 リフレクション メッセージは、等号 (=) でマークされます。  
  
7.  ハンドラーとしての推奨される名前を表示する [プロパティ] ウィンドウで、右側の列のセルをクリックして\<追加 >*HandlerName*します。 (たとえば、 **= WM_CTLCOLOR**メッセージ ハンドラーを提案\<追加 >**CtlColor**)。  
  
8.  受け入れるように推奨される名前をクリックします。 ハンドラーは、プロジェクトに追加されます。  
  
     リフレクション メッセージ ウィンドウの右側の列に追加したメッセージ ハンドラーの名前が表示されます。  
  
9. を編集またはメッセージ ハンドラーを削除するには、手順 4 ~ 7 を繰り返します。 編集または削除し、適切なタスクをクリックしてハンドラー名を含むセルをクリックします。  
  
## <a name="see-also"></a>関連項目  
 [関数へのメッセージの割り当てください。](../../mfc/reference/mapping-messages-to-functions.md)   
 [コード ウィザードによる機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [クラスの追加](../../ide/adding-a-class-visual-cpp.md)   
 [メンバー関数の追加](../../ide/adding-a-member-function-visual-cpp.md)   
 [メンバー変数の追加](../../ide/adding-a-member-variable-visual-cpp.md)   
 [仮想関数のオーバーライド](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC メッセージ ハンドラー](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [クラス各部へ](../../ide/navigating-the-class-structure-visual-cpp.md)

