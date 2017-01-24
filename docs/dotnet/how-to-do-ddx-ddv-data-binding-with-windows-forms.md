---
title: "方法: Windows フォームで DDX/DDV データ バインドを実行する | Microsoft Docs"
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
  - "MFC [C++], ホスト (Windows フォーム コントロールを)"
  - "Windows フォーム [C++], MFC サポート"
ms.assetid: b2957370-cf1f-4779-94ac-228cd393686c
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: Windows フォームで DDX/DDV データ バインドを実行する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[DDX\_ManagedControl](../Topic/DDX_ManagedControl.md) は、[CWinFormsControl::CreateManagedControl](../Topic/CWinFormsControl::CreateManagedControl.md) を呼び出し、リソースのコントロール ID と一致するコントロールを作成します。  ウィザードで生成されたコードの `CWinFormsControl` コントロールに `DDX_ManagedControl` を使用する場合は、同じコントロールに対して `CreateManagedControl` を明示的に呼び出さないでください。  
  
 [CWnd::DoDataExchange](../Topic/CWnd::DoDataExchange.md) の `DDX_ManagedControl` を呼び出し、リソース ID からコントロールを作成します。  データ交換の場合は、Windows フォーム コントロールで DDX\/DDV 関数を使用する必要はありません。  代わりに、次の例のように、ダイアログ \(またはビュー\) クラスの `DoDataExchange` メソッド内のマネージ コントロールのプロパティにアクセスするコードを配置できます。  
  
 ネイティブな C\+\+ 文字列を .NET ユーザー コントロールにバインドする方法の例を次に示します。  
  
## 使用例  
 .NET ユーザー コントロールのユーザー定義の `NameText` プロパティを使用した `m_str` という MFC 文字列の DDX\/DDV データ バインディングの例を次に示します。  
  
 コントロールは、[CDialog::OnInitDialog](../Topic/CDialog::OnInitDialog.md) が最初に `CMyDlg::DoDataExchange` を呼び出したときに作成されます。そのため、`m_UserControl` を参照するコードは、`DDX_ManagedControl` 呼び出しの後に記述する必要があります。  
  
 このコードは、「[方法: ダイアログ ボックスにユーザー コントロールおよびホストを作成する](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)」で作成した MFC01 アプリケーションで実装できます。  
  
 CMFC01Dlg の宣言に、次のコードを配置します。  
  
```  
class CMFC01Dlg : public CDialog  
{  
   CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_MyControl;  
   CString m_str;  
};  
```  
  
## 使用例  
 CMFC01Dlg の実装に、次のコードを配置します。  
  
```  
void CMFC01Dlg::DoDataExchange(CDataExchange* pDX)  
{  
   CDialog::DoDataExchange(pDX);  
   DDX_ManagedControl(pDX, IDC_CTRL1, m_MyControl);  
  
   if (pDX->m_bSaveAndValidate) {  
      m_str = m_MyControl->textBox1->Text;  
   } else  
   {  
      m_MyControl->textBox1->Text = gcnew System::String(m_str);  
   }  
}  
```  
  
## 使用例  
 ここで、\[OK\] ボタンに、クリックのハンドラー メソッドを追加します。  **\[リソース ビュー\]** タブをクリックします。  \[リソース ビュー\] で、`IDD_MFC01_DIALOG` をダブルクリックします。  リソース エディターにダイアログ リソースが表示されます。  次に、\[OK\] ボタンをダブルクリックします。  
  
 次のように、ハンドラーを定義します。  
  
```  
void CMFC01Dlg::OnBnClickedOk()  
{  
   AfxMessageBox(CString(m_MyControl.GetControl()->textBox1->Text));  
   OnOK();  
}  
```  
  
## 使用例  
 BOOL CMFC01Dlg::OnInitDialog\(\) の実装に次の行を追加します。  
  
```  
m_MyControl.GetControl()->textBox1->Text = "hello";  
```  
  
 これにより、アプリケーションをビルドして実行できるようになります。  アプリケーションの終了時にテキスト ボックス内のテキストがポップアップ メッセージとして表示されることに注意してください。  
  
## 参照  
 [CWinFormsControl クラス](../mfc/reference/cwinformscontrol-class.md)   
 [DDX\_ManagedControl](../Topic/DDX_ManagedControl.md)   
 [CWnd::DoDataExchange](../Topic/CWnd::DoDataExchange.md)