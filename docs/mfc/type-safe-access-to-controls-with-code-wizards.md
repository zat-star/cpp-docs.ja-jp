---
title: "コード ウィザードを使用した、コントロールへのタイプ セーフ アクセス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コード ウィザード"
  - "DDX (ダイアログ データ エクスチェンジ), アクセス (コントロールに)"
  - "ダイアログ ボックス コントロール, アクセス"
  - "ダイアログ ボックス, アクセス (コントロールに)"
ms.assetid: b8874393-ee48-4124-8d78-e3648a7e29b9
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# コード ウィザードを使用した、コントロールへのタイプ セーフ アクセス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DDX 機能に精通している場合は、[メンバー変数の追加](../ide/add-member-variable-wizard.md) のタイプ セーフ アクセスを作成するには、コントロールのプロパティを使用できます。  この方法は、コントロールをコード ウィザードを使用せずに作成するよりも簡単です。  
  
 コントロールの値へのアクセスを簡単にする場合は、DDX によって提供されます。  よりアクセスするコントロールの値にロジックを追加するには、ダイアログ クラスに適切なクラスのメンバー変数を追加するには、メンバー変数の追加ウィザードを使用します。  コントロールのプロパティにこのメンバー変数を追加します。  
  
 メンバー変数には値のプロパティの代わりにコントロールのプロパティを設定できます。  値のプロパティは `CString` または `int`などのコントロールから返されたデータの種類を示します。  コントロールのプロパティでは、型が `CButton` または `CEdit`などの MFC コントロール クラスの 1 つが、であるデータ メンバーを通じてコントロールに直接アクセスします。  
  
> [!NOTE]
>  指定されたコントロールの場合、望めば、得た値のプロパティで複数のメンバー変数とコントロールのプロパティで、最大で 1 個のメンバー変数を指定できます。  コントロールへの複数のオブジェクトの添付、またはそのほかのウィンドウ、メッセージ マップのあいまいさの原因となるため、コントロールへの 1 回の MFC オブジェクトのみをマップできます。  
  
 コントロール オブジェクトのメンバー関数を呼び出すには、このオブジェクトを使用する。  このような呼び出しは、ダイアログ ボックスのコントロールに影響します。  たとえば、A という変数 `m_Checkbox`を使用すると、型指定された `CButton`のチェック ボックス コントロール: Microsoft.Office.Tools.Word.Document.InnerObject  
  
 [!code-cpp[NVC_MFCControlLadenDialog#52](../mfc/codesnippet/CPP/type-safe-access-to-controls-with-code-wizards_1.cpp)]  
  
 ここでメンバー変数 `m_Checkbox` は [コード ウィザードのないコントロールへのタイプ セーフ アクセス](../mfc/type-safe-access-to-controls-without-code-wizards.md)で示したメンバー関数 `GetMyCheckbox` と同じ目的に使用されます。  チェック ボックスが自動検査チェック ボックスでない限り、ボタンがクリックされたときに、**BN\_CLICKED** コントロール通知メッセージのダイアログ クラスのハンドラーが必要です。  
  
 コントロールに関する詳細については、「[コントロール](../mfc/controls-mfc.md)」を参照してください。  
  
## 参照  
 [ダイアログ ボックスのコントロールへのタイプ セーフ アクセス](../Topic/Type-Safe%20Access%20to%20Controls%20in%20a%20Dialog%20Box.md)   
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)   
 [コード ウィザードを使用しない、コントロールへのタイプ セーフ アクセス](../mfc/type-safe-access-to-controls-without-code-wizards.md)