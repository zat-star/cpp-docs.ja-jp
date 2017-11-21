---
title: "ダイアログ コントロールのメンバー変数の定義 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- member variables, defining for controls
- variables, dialog box control member variables
- controls [C++], member variables
- Dialog editor, defining member variables for controls
ms.assetid: 84347c63-c33c-4b04-91f5-6d008c45ba58
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f81b0d124db2a28b8d38c1a79d7569d8e46742b3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="defining-member-variables-for-dialog-controls"></a>ダイアログ コントロールのメンバー変数の定義
ボタン以外のダイアログ ボックス コントロールのメンバー変数を定義するには、次の手順を使用できます。  
  
> [!NOTE]
>  この記事に該当するのは、MFC プロジェクト内のダイアログ コントロールだけです。 ATL プロジェクトを使用する必要があります、**新しい Windows メッセージおよびイベント ハンドラー**  ダイアログ ボックス。  
  
### <a name="to-define-a-member-variable-for-a-non-button-dialog-box-control"></a>ボタン以外のダイアログ ボックス コントロールのメンバー変数を定義するには  
  
1.  [ダイアログ エディター](../windows/dialog-editor.md)コントロールを選択します。  
  
2.  キーを押しているときに、 **CTRL**キー、ダイアログ ボックス コントロールをダブルクリックします。  
  
     [メンバー変数の追加ウィザード](../ide/add-member-variable-wizard.md)が表示されます。  
  
3.  適切な情報を入力して、**メンバー変数の追加**ウィザード。 詳細については、次を参照してください。[ダイアログ データ エクス チェンジ](../mfc/dialog-data-exchange.md)です。  
  
4.  をクリックして**OK**ダイアログ エディターに戻ります。  
  
    > [!TIP]
    >  ダイアログ ボックス コントロールから既存のハンドラーにジャンプするには、コントロールをダブルクリックします。  
  

  
 使用することも、**メンバー変数**] タブの [ **MFC クラス ウィザード**を指定したクラスの新しいメンバー変数を追加し、既に定義されているものを表示します。  
  
 要件  
  
 MFC  
  
## <a name="see-also"></a>関連項目  
 [関数へのメッセージの割り当てください。](../mfc/reference/mapping-messages-to-functions.md)   
 [コード ウィザードによる機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [MFC クラス ウィザード](../mfc/reference/mfc-class-wizard.md)   
 [クラスの追加](../ide/adding-a-class-visual-cpp.md)   
 [メンバー関数の追加](../ide/adding-a-member-function-visual-cpp.md)   
 [メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md)   
 [仮想関数のオーバーライド](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC メッセージ ハンドラー](../mfc/reference/adding-an-mfc-message-handler.md)

