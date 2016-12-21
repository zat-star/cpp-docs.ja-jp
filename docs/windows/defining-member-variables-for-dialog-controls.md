---
title: "Defining Member Variables for Dialog Controls | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "member variables, defining for controls"
  - "variables, dialog box control member variables"
  - "controls [C++], member variables"
  - "Dialog editor, defining member variables for controls"
ms.assetid: 84347c63-c33c-4b04-91f5-6d008c45ba58
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Defining Member Variables for Dialog Controls
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ボタン以外のダイアログ ボックス コントロールのメンバー変数を定義するには、次の手順を使用できます。  
  
> [!NOTE]
>  この記事に該当するのは、MFC プロジェクト内のダイアログ コントロールだけです。  ATL プロジェクトでは、**\[Windows メッセージおよびイベント ハンドラーの新規作成\]** ダイアログ ボックスを使用する必要があります。  
  
### ボタン以外のダイアログ ボックス コントロールのメンバー変数を定義するには  
  
1.  [ダイアログ エディター](../mfc/dialog-editor.md)でコントロールを選択します。  
  
2.  **Ctrl** キーを押しながらダイアログ ボックス コントロールをダブルクリックします。  
  
     [メンバー変数の追加ウィザード](../ide/add-member-variable-wizard.md)が表示されます。  
  
3.  **メンバー変数の追加**ウィザードに、適切な情報を入力します。  詳細については、「[ダイアログ データ エクスチェンジ](../mfc/dialog-data-exchange.md)」を参照してください。  
  
4.  **\[OK\]** をクリックして、ダイアログ エディターに戻ります。  
  
    > [!TIP]
    >  ダイアログ ボックス コントロールから既存のハンドラーにジャンプするには、コントロールをダブルクリックします。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。 マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的リソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 **MFC クラス ウィザード**の **\[メンバー変数\]** タブを使用すると、指定したクラスに新しいメンバー変数を追加したり、定義済みのメンバー変数を表示したりすることもできます。  
  
 必要条件  
  
 MFC  
  
## 参照  
 [関数へのメッセージの割り当て](../Topic/Mapping%20Messages%20to%20Functions.md)   
 [コード ウィザードを使用した機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [MFC クラス ウィザード](../mfc/reference/mfc-class-wizard.md)   
 [クラスの追加](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)   
 [メンバー関数の追加](../ide/adding-a-member-function-visual-cpp.md)   
 [メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md)   
 [仮想関数のオーバーライド](../Topic/Overriding%20a%20Virtual%20Function%20\(Visual%20C++\).md)   
 [MFC メッセージ ハンドラー](../mfc/reference/adding-an-mfc-message-handler.md)