---
title: "Adding Event Handlers for Dialog Box Controls | Microsoft Docs"
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
helpviewer_keywords: 
  - "Dialog editor, adding event handlers to controls"
  - "controls [C++], event handlers"
  - "dialog box controls, events"
  - "event handlers, for dialog box controls"
ms.assetid: f9c70f24-ea6f-44df-82eb-78a2deaee769
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Adding Event Handlers for Dialog Box Controls
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

既にクラスに関連付けられているプロジェクトのダイアログ ボックスの場合は、イベント ハンドラーの作成時にいくつかのショートカットを利用できます。  既定のコントロール通知イベントまたは適用可能な Windows メッセージに対するハンドラーをすばやく作成できます。  
  
#### 既定のコントロール通知イベントのハンドラーを作成するには  
  
1.  コントロールをダブルクリックします。  テキスト エディターが表示されます。  
  
2.  テキスト エディターで、コントロール通知ハンドラーのコードを追加します。  
  
#### 適用可能な Windows メッセージのハンドラーを作成するには  
  
1.  通知イベントの処理に使用するコントロールをクリックします。  
  
2.  [&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)の \[イベント コントロール\] ボタンをクリックし、コントロールに関連付けられている共通の Windows イベントの一覧を表示します。  たとえば、\[バージョン情報\] ダイアログ ボックスの標準の \[OK\] ボタンは、以下の通知イベントを表示します。  
  
     **BN\_CLICKED**  
  
     **BN\_DOUBLECLICKED**  
  
     **BN\_KILLFOCUS**  
  
     **BN\_SETFOCUS**  
  
    > [!NOTE]
    >  または、ダイアログ ボックスを選択し、\[イベント コントロール\] ボタンをクリックすると、ダイアログ ボックスのすべてのコントロールに共通する Windows イベントの一覧が表示されます。  
  
3.  \[プロパティ\] ウィンドウで、処理するイベントの右側の列をクリックし、表示された通知イベント名を選択します。たとえば、**OnBnClickedOK** は **BN\_CLICKED** を処理します。  
  
    > [!NOTE]
    >  既定のイベント ハンドラー名を選択するのではなく、イベント ハンドラーの名前を独自に決めることもできます。  
  
     イベントを選択すると、テキスト エディターが開き、選択したイベント ハンドラーのコードが表示されます。  たとえば、既定の **OnBnClickedOK** の場合は、次のコードが追加されます。  
  
    ```  
    void CAboutDlg::OnBnClickedOk(void)  
    {  
       // TODO: Add your control notification handler code here  
    }  
    ```  
  
 ダイアログ ボックスを実装するクラス以外のクラスにイベント ハンドラーを追加するには、[イベント ハンドラー ウィザード](../ide/event-handler-wizard.md)を使用します。  詳細については、「[イベント ハンドラーの追加](../ide/adding-an-event-handler-visual-cpp.md)」を参照してください。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
### 要件  
 Win32  
  
## 参照  
 [Default Control Events](../Topic/Default%20Control%20Events.md)   
 [Defining Member Variables for Dialog Controls](../mfc/defining-member-variables-for-dialog-controls.md)   
 [ダイアログ ボックス コントロールおよび変数の型](../Topic/Dialog%20Box%20Controls%20and%20Variable%20Types.md)   
 [クラスの追加](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)   
 [メンバー関数の追加](../ide/adding-a-member-function-visual-cpp.md)   
 [メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md)   
 [仮想関数のオーバーライド](../Topic/Overriding%20a%20Virtual%20Function%20\(Visual%20C++\).md)   
 [MFC メッセージ ハンドラー](../mfc/reference/adding-an-mfc-message-handler.md)