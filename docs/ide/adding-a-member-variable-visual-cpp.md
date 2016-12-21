---
title: "メンバー変数の追加 (Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.classes.member.variable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "メンバー変数"
  - "メンバー変数, 追加"
ms.assetid: 437783bd-8eb4-4508-8b73-7380116e9d71
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# メンバー変数の追加 (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラス ビューでメンバー変数をクラスに追加できます。  メンバー変数は、[データ交換とデータ検証](../mfc/dialog-data-exchange-and-validation.md)用に指定することも、汎用目的で指定することもできます。  データ メンバー変数のウィザードは、関連する情報を読み込み、読み込んだ情報を使用してソース ファイルの適切な場所に要素を追加するようにデザインされています。  メンバー変数は、[リソース ビュー](../windows/resource-view-window.md)の[ダイアログ エディター](../mfc/dialog-editor.md)、または[クラス ビュー](http://msdn.microsoft.com/ja-jp/8d7430a9-3e33-454c-a9e1-a85e3d2db925)で追加できます。  
  
> [!NOTE]
>  ダイアログ ボックスを設計して実装する場合は、ダイアログ エディターを使用してダイアログ ボックス コントロールを追加してから、コントロールのメンバー変数を実装する方が効率的です。  
  
### メンバー変数の追加ウィザードを使用して、リソース ビューでダイアログ コントロールにメンバー変数を追加するには  
  
1.  リソース ビューで、プロジェクト ノードと \[Dialog\] ノードを展開して、プロジェクトのダイアログ ボックスの一覧を表示します。  
  
2.  メンバー変数を追加するダイアログ ボックスをダブルクリックし、ダイアログ エディターでそのダイアログ ボックスを開きます。  
  
3.  ダイアログ エディターに表示されたダイアログ ボックスで、メンバー変数を追加するコントロールを右クリックします。  
  
4.  ショートカット メニューの **\[変数の追加\]** をクリックし、[メンバー変数の追加ウィザード](../ide/add-member-variable-wizard.md)を表示します。  
  
    > [!NOTE]
    >  \[コントロール ID\] には既に既定値が表示されています。  
  
5.  ウィザードの各ボックスに情報を入力します。  詳細については、「[ダイアログ ボックス コントロールおよび変数の型](../Topic/Dialog%20Box%20Controls%20and%20Variable%20Types.md)」を参照してください。  
  
6.  \[完了\] をクリックしてプロジェクトに定義および実装コードを追加し、ウィザードを閉じます。  
  
### メンバー変数の追加ウィザードを使用して、クラス ビューでメンバー変数を追加するには  
  
1.  [クラス ビュー](http://msdn.microsoft.com/ja-jp/8d7430a9-3e33-454c-a9e1-a85e3d2db925)でプロジェクト ノードを展開して、プロジェクト内のクラスを表示します。  
  
2.  変数を追加するクラスを右クリックします。  
  
3.  ショートカット メニューの \[追加\] をクリックし、**\[変数の追加\]** をクリックしてメンバー変数の追加ウィザードを表示します。  
  
4.  ウィザードの各ボックスに情報を入力します。  詳細については、「[メンバー変数の追加ウィザード](../ide/add-member-variable-wizard.md)」を参照してください。  
  
5.  \[完了\] をクリックしてプロジェクトに定義および実装コードを追加し、ウィザードを閉じます。  
  
## 参照  
 [コード ウィザードを使用した機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [クラスの追加](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)   
 [メンバー関数の追加](../ide/adding-a-member-function-visual-cpp.md)   
 [MFC メッセージ ハンドラー](../mfc/reference/adding-an-mfc-message-handler.md)   
 [クラス各部へのジャンプ](../ide/navigating-the-class-structure-visual-cpp.md)