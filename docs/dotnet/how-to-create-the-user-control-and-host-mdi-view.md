---
title: "方法: ユーザー コントロールを作成し、MDI ビューをホストする | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "MFC [C++], Windows フォーム コントロール"
  - "Windows フォーム [C++], MFC サポート"
ms.assetid: 625b5821-f923-4701-aca0-c1a4ceca4f63
caps.latest.revision: 25
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: ユーザー コントロールを作成し、MDI ビューをホストする
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次の手順では、.NET Framework ユーザー コントロールを作成し、そのユーザー コントロールをコントロール クラス ライブラリ \(特に Windows コントロール ライブラリ プロジェクト\) に作成し、プロジェクトをアセンブリにコンパイルする方法について説明します。  このコントロールは、[CView クラス](../Topic/CView%20Class.md)および [CWinFormsView クラス](../mfc/reference/cwinformsview-class.md)から派生したクラスを使用する MFC アプリケーションで使用できます。  
  
 Windows フォーム ユーザー コントロールの作成方法およびコントロール クラス ライブラリの作成方法については、「[方法 : 複合コントロールを作成する](../Topic/How%20to:%20Author%20Composite%20Controls.md)」を参照してください。  
  
> [!NOTE]
>  サードパーティのグリッド コントロールなどの Windows フォーム コントロールは、MFC アプリケーションでホストした場合に適切に動作しないことがあります。  この問題の推奨回避策は、Windows フォーム ユーザー コントロールを MFC アプリケーションに配置し、サードパーティのグリッド コントロールをユーザー コントロールの内部に配置することです。  
  
 「[方法: ダイアログ ボックスにユーザー コントロールおよびホストを作成する](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)」での手順のように、この手順では、WindowsFormsControlLibrary1 という名前の Windows フォーム コントロール ライブラリ プロジェクトを作成済みであることを前提とします。  
  
### MFC ホスト アプリケーションを作成するには  
  
1.  MFC アプリケーション プロジェクトを作成します。  
  
     **\[ファイル\]** メニューの **\[新規作成\]** をポイントし、**\[プロジェクト\]** をクリックします。  **\[Visual C\+\+\]** フォルダーの **\[MFC アプリケーション\]** をクリックします。  
  
     **\[名前\]** ボックスに「`MFC02`」と入力し、**\[ソリューション\]** の設定を **\[ソリューションに追加\]** に変更します。  \[OK\] をクリックします。  
  
     **MFC アプリケーション ウィザード**で、すべての既定値をそのまま使用し、**\[完了\]** をクリックします。  これにより、マルチ ドキュメント インターフェイスを持つ MFC アプリケーションが作成されます。  
  
2.  共通言語ランタイム \(CLR: Common Language Runtime\) に対するサポートをプロジェクトに構成します。  
  
     **ソリューション エクスプローラー**で、`MFC01` プロジェクトのノードを右クリックし、コンテキスト メニューの **\[プロパティ\]** をクリックします。  **\[プロパティ ページ\]** ダイアログ ボックスが表示されます。  
  
     **\[構成プロパティ\]** の **\[全般\]** を選択します。  **\[プロジェクトの既定値\]** セクションの **\[共通言語ランタイム サポート\]** を **\[共通言語ランタイム サポート \(\/clr\)\]** に設定します。  
  
     **\[構成プロパティ\]** で **\[C\/C\+\+\]** を展開し、**\[全般\]** ノードをクリックします。  **\[デバッグ情報の形式\]** を **\[プログラム データベース \(\/Zi\)\]** に設定します。  
  
     **\[コード生成\]** ノードをクリックします。  **\[簡易リビルドを行う\]** を **\[いいえ \(\/Gm\-\)\]** に設定します。  また、**\[基本ランタイム チェック\]** も **\[既定値\]** に設定します。  
  
     **\[OK\]** をクリックして変更を適用します。  
  
3.  stdafx.h に、次の行を追加します。  
  
    ```  
    #using <System.Windows.Forms.dll>  
    ```  
  
4.  .NET コントロールへの参照を追加します。  
  
     **ソリューション エクスプローラー**で、`MFC02` プロジェクトのノードを右クリックし、**\[追加\]**、**\[参照\]** の順にクリックします。  **\[プロパティ ページ\]** の **\[新しい参照の追加\]**、WindowsFormsControlLibrary1 \(**\[プロジェクト\]** タブ\) の順にクリックし、**\[OK\]** をクリックします。  これにより、参照が [\/FU](../build/reference/fu-name-forced-hash-using-file.md) コンパイラ オプションの形式で追加され、プログラムをコンパイルできるようになります。また、`MFC02` のプロジェクト ディレクトリに WindowsFormsControlLibrary1.dll がコピーされ、プログラムを実行できるようになります。  
  
5.  stdafx.h で次の行を見つけます。  
  
    ```  
    #endif // _AFX_NO_AFXCMN_SUPPORT   
    ```  
  
     その上に次の行を追加します。  
  
    ```  
    #include <afxwinforms.h>   // MFC Windows Forms support  
    ```  
  
6.  ビュー クラスを変更して、これを [CWinFormsView](../mfc/reference/cwinformsview-class.md) から継承します。  
  
     MFC02View.h で、[CView](../Topic/CView%20Class.md) を [CWinFormsView](../mfc/reference/cwinformsview-class.md) に置き換えて、次のようなコードにします。  
  
    ```  
    class CMFC02View : public CWinFormsView  
    {  
    };  
    ```  
  
     MDI アプリケーションにビューを追加する場合は、作成するビューごとに [CWinApp::AddDocTemplate](../Topic/CWinApp::AddDocTemplate.md) を呼び出す必要があります。  
  
7.  MFC02View.cpp ファイルを変更して、IMPLEMENT\_DYNCREATE マクロとメッセージ マップで CView を CWinFormsView に変更し、既存の空のコンストラクターを次に示すコンストラクターに置き換えます。  
  
    ```  
    IMPLEMENT_DYNCREATE(CMFC02View, CWinFormsView)  
  
    CMFC02View::CMFC02View(): CWinFormsView(WindowsFormsControlLibrary1::UserControl1::typeid)   
    {  
    }  
    BEGIN_MESSAGE_MAP(CMFC02View, CWinFormsView)  
    //leave existing body as is  
    END_MESSAGE_MAP()  
    ```  
  
8.  プロジェクトをビルドして実行します。  
  
     **ソリューション エクスプローラー**で、MFC02 を右クリックし、**\[スタートアップ プロジェクトに設定\]** をクリックします。  
  
     **\[ビルド\]** メニューの **\[ソリューションのビルド\]** をクリックします。  
  
     **\[デバッグ\]** メニューの **\[デバッグなしで開始\]** をクリックします。  
  
## 参照  
 [MFC ビューとしての Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)