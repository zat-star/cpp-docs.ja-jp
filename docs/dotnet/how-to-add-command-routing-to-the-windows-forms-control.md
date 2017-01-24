---
title: "方法: Windows フォーム コントロールにコマンド ルーティングを追加する | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コマンド ルーティング [C++] であり、Windows フォーム コントロールに追加します。"
  - "ルーティング コマンドを Windows フォーム コントロール [C++]"
ms.assetid: bf138ece-b463-442a-b0a0-de7063a760c0
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: Windows フォーム コントロールにコマンド ルーティングを追加する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CWinFormsView](../mfc/reference/cwinformsview-class.md) を MFC のコマンド (フレームのメニュー項目やツール バー ボタンなど) を処理できるようにするユーザー コントロールにコマンドおよび更新コマンド UI メッセージをルーティングします。  
  
 ユーザー コントロールを使用して [ICommandTarget::Initialize](../Topic/ICommandTarget::Initialize.md) 内のコマンド ソース オブジェクトへの参照を格納する `m_CmdSrc`, 、次の例のように、します。 `ICommandTarget` を使用するには、mfcmifc80.dll への参照を追加する必要があります。  
  
 `CWinFormsView` は、共通の MFC ビューの通知をマネージ ユーザー コントロールに転送することによって処理します。 これらの通知を含める、 [OnInitialUpdate](../Topic/IView::OnInitialUpdate.md), 、[OnUpdate](../Topic/IView::OnUpdate.md) と [OnActivateView](../Topic/IView::OnActivateView.md) のメソッド、 [IView インターフェイス](../Topic/IView%20Interface.md)します。  
  
 このトピックでは、終了したものと [する方法: ダイアログ ボックスでユーザー コントロールおよびホストを作成](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) と [する方法: ユーザー コントロールおよびホスト MDI ビューを作成](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)します。  
  
### <a name="to-create-the-mfc-host-application"></a>MFC ホスト アプリケーションを作成するには  
  
1.  作成した Windows フォーム コントロール ライブラリを開く [方法: ダイアログ ボックスでユーザー コントロールおよびホストを作成する](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)です。  
  
2.  プロジェクト ノードを右クリックして行うことができる mfcmifc80.dll への参照を追加 **ソリューション エクスプ ローラー**, [ **追加**, 、**参照**, 、Microsoft Visual Studio 10.0 10.0\VC\atlmfc\lib をクリックしています。  
  
3.  UserControl1.Designer.cs を開いて、次の using ステートメントを追加します。  
  
    ```  
    using Microsoft.VisualC.MFC;  
    ```  
  
4.  また、UserControl1.Designer.cs の次の行を変更します。  
  
    ```  
    partial class UserControl1  
    ```  
  
     変更後は次のようになります。  
  
    ```  
    partial class UserControl1 : System.Windows.Forms.UserControl, ICommandTarget  
    ```  
  
5.  `UserControl1` のクラス定義の最初の行として次の行を追加します。  
  
    ```  
    private ICommandSource m_CmdSrc;  
    ```  
  
6.  次のメソッドの定義を `UserControl1` に追加します (次の手順で、MFC コントロールの ID を作成します)。  
  
    ```  
    public void Initialize (ICommandSource cmdSrc)  
    {  
       m_CmdSrc = cmdSrc;  
       // need ID of control in MFC dialog and callback function   
       m_CmdSrc.AddCommandHandler(32771, new CommandHandler (singleMenuHandler));  
    }  
  
    private void singleMenuHandler (uint cmdUI)  
    {  
       // User command handler code  
       System.Windows.Forms.MessageBox.Show("Custom menu option was clicked.");  
    }  
    ```  
  
7.  作成した MFC アプリケーションを開いて [方法: ユーザー コントロールおよびホスト MDI ビューを作成](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)します。  
  
8.  `singleMenuHandler` を呼び出すメニュー オプションを追加します。  
  
     移動 **リソース ビュー** (Ctrl + Shift + E)、展開、 **メニュー** フォルダー、およびダブルクリック **[idr_mfc02type]**します。 これにより、メニュー エディターが表示されます。  
  
     下部のメニュー オプションを追加、 **ビュー** メニュー。 メニュー オプションの ID を確認、 **プロパティ** ウィンドウです。 ファイルを保存します。  
  
      **ソリューション エクスプ ローラー**, Resource.h ファイルを開き、追加したメニュー オプションの ID 値をコピーして最初のパラメーターとしてその値を貼り付けます、 `m_CmdSrc.AddCommandHandler` c# プロジェクトの呼び出す `Initialize` メソッド (交換 `32771` 必要な場合)。  
  
9. プロジェクトをビルドして実行します。  
  
     **[ビルド]** メニューの **[ソリューションのビルド]**をクリックします。  
  
      **デバッグ** ] メニューのをクリックして **デバッグなしで開始**します。  
  
     追加したメニュー オプションを選択します。 .dll 内のメソッドが呼び出されます。  
  
## <a name="see-also"></a>「  
 [MFC ビューとして Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)   
 [ICommandSource インターフェイス](../mfc/reference/icommandsource-interface.md)   
 [関数のインターフェイス](../mfc/reference/icommandtarget-interface.md)   
 [CommandHandler](../Topic/CommandHandler%20Delegate.md)