---
title: "方法: Windows フォーム コントロールのプロパティとメソッドを呼び出す | Microsoft Docs"
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
  - "呼び出し (メソッド), Windows フォーム コントロール"
  - "呼び出し (プロパティの)"
  - "呼び出し (プロパティの), Windows フォーム コントロール"
  - "メソッド呼び出し, Windows フォーム"
  - "Windows フォーム コントロール [C++], メソッド"
  - "Windows フォーム コントロール [C++], プロパティ"
ms.assetid: 6e647d8a-fdaa-4aa1-b3fe-04f15cff8eb3
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: Windows フォーム コントロールのプロパティとメソッドを呼び出す
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CWinFormsView::GetControl](../Topic/CWinFormsView::GetControl.md) は、`WindowsControlLibrary1::UserControl1` へのポインターではなく、<xref:System.Windows.Forms.Control?displayProperty=fullName> へのポインターを返すため、ユーザー コントロール型のメンバーを追加し、[IView::OnInitialUpdate](../Topic/IView::OnInitialUpdate.md) で初期化することをお勧めします。  これにより、`m_ViewControl` を使用してメソッドおよびプロパティを呼び出すことができます。  
  
 このトピックは、前の手順の「[方法: ダイアログ ボックスにユーザー コントロールおよびホストを作成する](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)」および「[方法: ユーザー コントロールを作成し、MDI ビューをホストする](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)」を完了していることを前提としています。  
  
### MFC ホスト アプリケーションを作成するには  
  
1.  「[方法: ユーザー コントロールを作成し、MDI ビューをホストする](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)」で作成した MFC アプリケーションを開きます。  
  
2.  MFC02View.h で、`CMFC02View` クラス宣言のパブリック オーバーライド セクションに次の行を追加します。  
  
     `gcroot<WindowsFormsControlLibrary1::UserControl1 ^> m_ViewControl;`  
  
3.  OnInitialupdate のオーバーライドを追加します。  
  
     **\[プロパティ\]** ウィンドウを表示します \(F4 キーを押します\)。  **クラス ビュー**を表示し \(Ctrl キーと Shift キーを押しながら C キーを押し\)、CMFC02View クラスを選択します。  **\[プロパティ\]** ウィンドウで、オーバーライドのアイコンを選択します。  OnInitialUpdate が表示されるまで一覧を下にスクロールします。  ドロップダウン リストをクリックすると、\<追加\>します。  MFC02View.cpp で次のように OnInitialUpdate 関数の本体があることを確認する:  
  
    ```  
    CWinFormsView::OnInitialUpdate();  
    m_ViewControl = safe_cast<WindowsFormsControlLibrary1::UserControl1 ^>(this->GetControl());  
    m_ViewControl->textBox1->Text = gcnew System::String("hi");  
    ```  
  
4.  プロジェクトをビルドして実行します。  
  
     **\[ビルド\]** メニューの **\[ソリューションのビルド\]** をクリックします。  
  
     **\[デバッグ\]** メニューの **\[デバッグなしで開始\]** をクリックします。  
  
     これによってテキスト ボックスが初期化されます。  
  
## 参照  
 [MFC ビューとしての Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)