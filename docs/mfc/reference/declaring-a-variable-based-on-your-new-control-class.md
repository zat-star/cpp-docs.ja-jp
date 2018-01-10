---
title: "新しいコントロール クラスに基づいた変数の宣言 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.classes.control.variable
dev_langs: C++
helpviewer_keywords:
- variables [MFC], control classes
- control classes [MFC], variables
- classes [MFC], declaring variables based on
ms.assetid: 5722dc38-c0eb-40bd-93da-67a808140d03
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5aa98f815d9f9322c11d4256c13c0c7a42b4ab66
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="declaring-a-variable-based-on-your-new-control-class"></a>新しいコントロール クラスに基づいた変数の宣言
MFC コントロール クラスを作成した後は、それに基づく変数を宣言することができます。 新しい変数のコンテキストを提供するには、は、ダイアログ エディターを開き、編集 ダイアログ ボックスが再利用可能なコントロールを使用する必要があります。 また、ダイアログ ボックスは、関連付けられているクラスを既にが必要です。 ダイアログ エディターの使用方法の詳細については、次を参照してください。[ダイアログ エディター](../../windows/dialog-editor.md)です。  
  
### <a name="to-declare-a-variable-based-on-your-reusable-class"></a>再利用可能なクラスに基づいた変数を宣言するには  
  
1.  ダイアログ ボックスを編集している間には、ダイアログ ボックスにコントロールのツールバーから、新しいコントロールの基底クラスと同じ型のコントロールをドラッグします。  
  
2.  破棄されたコントロールの上にマウス ポインターを置きます。  
  
3.  CTRL キーを押しながら、コントロールをダブルクリックします。  
  
     [メンバー変数の追加](../../ide/add-member-variable-wizard.md) ダイアログ ボックスが表示されます。  
  
4.  **アクセス**ボックスで、コントロールの適切なアクセスを選択します。  
  
5.  クリックして、**制御変数**チェック ボックスをオンします。  
  
6.  **変数名**ボックスで、名前を入力します。  
  
7.  **カテゴリ**をクリックして**コントロール**です。  
  
8.  **コントロール ID**一覧で、追加したコントロールを選択します。 **変数型**一覧は、適切な変数型を表示する必要があります、**コントロール型**ボックスは、正しいコントロール型を表示する必要があります。  
  
9. **コメント**ボックスで、コード内に表示する任意のコメントを追加します。  
  
10. **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [関数へのメッセージの割り当てください。](../../mfc/reference/mapping-messages-to-functions.md)   
 [コード ウィザードによる機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [クラスの追加](../../ide/adding-a-class-visual-cpp.md)   
 [メンバー関数の追加](../../ide/adding-a-member-function-visual-cpp.md)   
 [メンバー変数の追加](../../ide/adding-a-member-variable-visual-cpp.md)   
 [仮想関数のオーバーライド](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC メッセージ ハンドラー](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [クラス各部へ](../../ide/navigating-the-class-structure-visual-cpp.md)
