---
title: "方法: ダイアログ ボックスにユーザー コントロールおよびホストを作成する | Microsoft Docs"
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
ms.assetid: 03a53032-2f03-4fa2-b567-031615a26011
caps.latest.revision: 29
caps.handback.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: ダイアログ ボックスにユーザー コントロールおよびホストを作成する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

この記事の手順では、ダイアログ ベースの \([CDialog クラス](../mfc/reference/cdialog-class.md)\) MFC \(Microsoft Foundation Class\) プロジェクトの作成を想定していますが、既存の MFC ダイアログ ボックスに Windows フォーム コントロールのサポートを追加することもできます。  
  
### .NET ユーザー コントロールを作成するには  
  
1.  `WindowsFormsControlLibrary1` という名前の新しい Visual C\# Windows フォーム コントロール ライブラリ プロジェクトを作成します。  
  
     **\[ファイル\]** メニューの **\[新規作成\]** をポイントし、**\[プロジェクト\]** をクリックします。  **Visual C\#** フォルダーの **\[Windows フォーム コントロール ライブラリ\]** をクリックします。  
  
     **\[OK\]** をクリックして、`WindowsFormsControlLibrary1` という既定のプロジェクト名をそのまま使用します。  
  
     既定では、.NET コントロールの名前は `UserControl1` です。  
  
2.  `UserControl1` に子コントロールを追加します。  
  
     **ツールボックス**の **\[すべての Windows フォーム\]** の一覧を開きます。  **Button** コントロールを `UserControl1` のデザイン サーフェイスにドラッグします。  
  
     また、**TextBox** コントロールも追加します。  
  
3.  **ソリューション エクスプローラー**で **UserControl1.Designer.cs** をダブルクリックして開き、編集します  TextBox および Button の説明を `private` から `public` に変更します。  
  
4.  プロジェクトをビルドします。  
  
     **\[ビルド\]** メニューの **\[ソリューションのビルド\]** をクリックします。  
  
### MFC ホスト アプリケーションを作成するには  
  
1.  MFC アプリケーション プロジェクトを作成します。  
  
     **\[ファイル\]** メニューの **\[新規作成\]** をポイントし、**\[プロジェクト\]** をクリックします。  **\[Visual C\+\+\]** フォルダーの **\[MFC アプリケーション\]** をクリックします。  
  
     **\[名前\]** ボックスに「`MFC01`」と入力します。  ソリューションの設定を **\[ソリューションに追加\]** に変更します。  \[OK\] をクリックします。  
  
     **MFC アプリケーション ウィザード**で、\[アプリケーションの種類\] として **\[ダイアログ ベース\]** を選択します。  残りの既定の設定を受け入れて、**\[完了\]** をクリックします。  これにより、MFC ダイアログ ボックスを伴った MFC アプリケーションが作成されます。  
  
2.  MFC ダイアログ ボックスに Placeholder コントロールを追加します。  
  
     **\[表示\]** メニューの **\[リソース ビュー\]** をクリックします。  **\[リソース ビュー\]** で **Dialog** フォルダーを展開し、`IDD_MFC01_DIALOG` をダブルクリックします。  **リソース エディター**にダイアログ リソースが表示されます。  
  
     **ツールボックス**の **\[ダイアログ エディター\]** の一覧を開きます。  **Static Text** コントロールをダイアログ リソースにドラッグします。  **Static Text** コントロールは、.NET Windows フォーム コントロールのプレースホルダーとして機能します。  コントロールのサイズが Windows フォーム コントロールとほぼ同じサイズになるように調整します。  
  
     **\[プロパティ\]** ウィンドウで **Static Text** コントロールの **ID** を `IDC_CTRL1` に変更し、**TabStop** プロパティを **True** に変更します。  
  
3.  共通言語ランタイム \(CLR: Common Language Runtime\) に対するサポートをプロジェクトに構成します。  
  
     **ソリューション エクスプローラー**で \[MFC01\] プロジェクト ノードを右クリックし、**\[プロパティ\]** をクリックします。  
  
     **\[プロパティ ページ\]** ダイアログ ボックスで、**\[構成プロパティ\]** の下の **\[全般\]** を選択します。  **\[プロジェクトの既定値\]** セクションの **\[共通言語ランタイム サポート\]** を **\[共通言語ランタイム サポート \(\/clr\)\]** に設定します。  
  
     **\[構成プロパティ\]** の下で、**\[C\/C\+\+\]** を展開し、**\[全般\]** ノードを選択します。  **\[デバッグ情報の形式\]** を **\[プログラム データベース \(\/Zi\)\]** に設定します。  
  
     **\[コード生成\]** ノードをクリックします。  **\[簡易リビルドを行う\]** を **\[いいえ \(\/Gm\-\)\]** に設定します。  また、**\[基本ランタイム チェック\]** も **\[既定値\]** に設定します。  
  
     **\[OK\]** をクリックして変更を適用します。  
  
4.  .NET コントロールへの参照を追加します。  
  
     **ソリューション エクスプローラー**で \[MFC01\] プロジェクト ノードを右クリックし、**\[追加\]**、**\[参照\]** の順にクリックします。  **\[プロパティ ページ\]** の **\[新しい参照の追加\]** をクリックし、**WindowsFormsControlLibrary1** \(**\[プロジェクト\]** タブの下\) をクリックして **\[OK\]** をクリックします。  これにより、プログラムをコンパイルするために、[\/FU](../build/reference/fu-name-forced-hash-using-file.md) コンパイラ オプションの形式で参照が追加されます。  また、プログラムを実行するために、WindowsFormsControlLibrary1.dll が \\MFC01\\ プロジェクト フォルダーにコピーされます。  
  
5.  Stdafx.h で次の行を見つけます。  
  
    ```  
    #endif // _AFX_NO_AFXCMN_SUPPORT   
    ```  
  
     その上に次の行を追加します。  
  
    ```  
    #include <afxwinforms.h>   // MFC Windows Forms support  
    ```  
  
6.  マネージ コントロールを作成するためのコードを追加します。  
  
     最初に、マネージ コントロールを宣言します。  MFC01Dlg.h でダイアログ クラスの宣言に移動し、Protected のスコープにユーザー コントロールのデータ メンバーを次のように追加します。  
  
    ```  
    class CMFC01Dlg : public CDialog  
    {  
       // ...  
       // Data member for the .NET User Control:  
       CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_ctrl1;  
    ```  
  
     次に、マネージ コントロールの実装を提供します。  MFC01Dlg.cpp の、MFC アプリケーション ウィザードによって生成された `CMFC01Dlg::DoDataExchange` のダイアログ オーバーライド \(同一ファイルの `CAboutDlg::DoDataExchange` ではなく\) に次のコードを追加して、マネージ コントロールを作成し、静的なプレースホルダー IDC\_CTRL1 に関連付けます。  
  
    ```  
    void CMFC01Dlg::DoDataExchange(CDataExchange* pDX)  
    {  
       CDialog::DoDataExchange(pDX);  
       DDX_ManagedControl(pDX, IDC_CTRL1, m_ctrl1);  
    }  
    ```  
  
7.  プロジェクトをビルドして実行します。  
  
     **ソリューション エクスプローラー**で、**\[MFC01\]** を右クリックし、**\[スタートアップ プロジェクトに設定\]** をクリックします。  
  
     **\[ビルド\]** メニューの **\[ソリューションのビルド\]** をクリックします。  
  
     **\[デバッグ\]** メニューの **\[デバッグなしで開始\]** をクリックします。  MFC ダイアログ ボックスに Windows フォーム コントロールが表示されます。  
  
## 参照  
 [MFC ダイアログ ボックスにおける Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)