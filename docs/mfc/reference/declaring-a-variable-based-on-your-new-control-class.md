---
title: "新しいコントロール クラスに基づいた変数を宣言する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.classes.control.variable
dev_langs:
- C++
helpviewer_keywords:
- variables, control classes
- control classes, variables
- classes [C++], declaring variables based on
ms.assetid: 5722dc38-c0eb-40bd-93da-67a808140d03
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
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: a5777019ca87616fbb7c6a0d27140b3fabbf7fde
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="declaring-a-variable-based-on-your-new-control-class"></a>新しいコントロール クラスに基づいた変数の宣言
MFC コントロール クラスを作成した後は、それに基づいて変数を宣言することができます。 で新しい変数を、コンテキストを指定するには、ダイアログ エディターを開き、編集 ダイアログ ボックスが再利用可能なコントロールを使用する必要があります。 また、ダイアログ ボックスは、関連付けられているクラスを既にが必要です。 ダイアログ エディターの使用方法の詳細については、次を参照してください。[ダイアログ エディター](../../windows/dialog-editor.md)します。  
  
### <a name="to-declare-a-variable-based-on-your-reusable-class"></a>再利用可能なクラスに基づいた変数を宣言するには  
  
1.  ダイアログ ボックスを編集している間には、ダイアログ ボックスの [コントロール] ツールバーから、新しいコントロールの基本クラスと同じ型のコントロールをドラッグします。  
  
2.  削除されたコントロールの上にマウス ポインターを置きます。  
  
3.  CTRL キーを押しながらコントロールをダブルクリックします。  
  
     [メンバー変数の追加](../../ide/add-member-variable-wizard.md) ダイアログ ボックスが表示されます。  
  
4.  **アクセス**ボックスで、コントロールの適切なアクセスを選択します。  
  
5.  クリックして、**制御変数**チェック ボックスをオンします。  
  
6.  **変数名**ボックスに、名前を入力します。  
  
7.  **カテゴリ**、クリックして**コントロール**します。  
  
8.  **コントロール ID**ボックスの一覧で、追加したコントロールを選択します。 **変数の型**適切な変数型の一覧が表示され、**コントロール型**ボックスは、正しいコントロールの種類を表示する必要があります。  
  
9. **コメント**ボックスで、コード内に表示する任意のコメントを追加します。  
  
10. **[OK]** をクリックします。  
  
## <a name="see-also"></a>関連項目  
 [関数へのメッセージの割り当てください。](../../mfc/reference/mapping-messages-to-functions.md)   
 [コード ウィザードによる機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [クラスの追加](../../ide/adding-a-class-visual-cpp.md)   
 [メンバー関数の追加](../../ide/adding-a-member-function-visual-cpp.md)   
 [メンバー変数の追加](../../ide/adding-a-member-variable-visual-cpp.md)   
 [仮想関数のオーバーライド](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC メッセージ ハンドラー](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [クラス各部へ](../../ide/navigating-the-class-structure-visual-cpp.md)

