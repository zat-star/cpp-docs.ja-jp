---
title: "チュートリアル : 新しい MFC シェル コントロールの使用 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "シェル コントロール (MFC)"
ms.assetid: f0015caa-199d-4aaf-9501-5a239fce9095
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# チュートリアル : 新しい MFC シェル コントロールの使用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このチュートリアルでは、ファイル エクスプローラーのような外観のアプリケーションを作成します。  ここでは、2 つのペインのあるウィンドウを作成します。  左ペインにある [CMFCShellTreeCtrl](../mfc/reference/cmfcshelltreectrl-class.md) オブジェクトには、デスクトップが階層構造で表示されます。  右ペインにある [CMFCShellListCtrl](../mfc/reference/cmfcshelllistctrl-class.md) には、左ペインで選択されたフォルダー内のファイルが表示されます。  
  
## 必須コンポーネント  
 このチュートリアルは、読者が**全般的な開発設定**を使用することを指定して [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] のセットアップを完了していることを前提としています。  別の開発設定を使用している場合は、このチュートリアルで使用する一部の [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] ウィンドウが既定で表示されないことがあります。  
  
### MFC アプリケーション ウィザードを使用して新しい MFC アプリケーションを作成するには  
  
1.  **MFC アプリケーション ウィザード**を使用して、新しい MFC アプリケーションを作成します。  このウィザードを実行するには、**\[ファイル\]** メニューの **\[新規作成\]** をポイントし、**\[プロジェクト\]** をクリックします。  **\[新しいプロジェクト\]** ダイアログ ボックスが表示されます。  
  
2.  **\[新しいプロジェクト\]** ダイアログ ボックスの **\[プロジェクトの種類\]** ペインで、**\[Visual C\+\+\]** ノードを展開し、**\[MFC\]** をクリックします。  次に、**\[テンプレート\]** ペインで **\[MFC アプリケーション\]** をクリックします。  プロジェクトの名前 \(`MFCShellControls` など\) を入力し、**\[OK\]** をクリックします。  **MFC アプリケーション ウィザード**が表示されます。  
  
3.  **\[MFC アプリケーション ウィザード\]** ダイアログ ボックスで、**\[次へ\]** をクリックします。  **\[アプリケーションの種類\]** ペインが表示されます。  
  
4.  **\[アプリケーションの種類\]** ペインの **\[アプリケーションの種類\]** で、**\[タブ付きドキュメント\]** をオフにします。  次に、**\[シングル ドキュメント\]** を選択し、**\[ドキュメント\/ビュー アーキテクチャのサポート\]** を選択します。  **\[プロジェクト形式\]** で、**\[Visual Studio\]** を選択し、**\[視覚スタイルと色\]** ボックスの一覧の **\[Office 2007 \(青のテーマ\)\]** をクリックします。  その他のオプションはそのままにします。  **\[次へ\]** をクリックして、**\[複合ドキュメント サポート\]** ペインを表示します。  
  
5.  **\[複合ドキュメント サポート\]** ペインで、**\[なし\]** をクリックします。  **\[次へ\]** をクリックして、**\[ドキュメントテンプレート文字列\]** ペインを表示します。  
  
6.  **\[ドキュメントテンプレート文字列\]** ペインでは何も変更しません。  **\[次へ\]** をクリックして、**\[データベース サポート\]** ペインを表示します。  
  
7.  このアプリケーションではデータベースを使用しないため、**\[データベース サポート\]** ペインで **\[なし\]** を選択します。  **\[次へ\]** をクリックして、**\[ユーザー インターフェイス機能\]** ペインを表示します。  
  
8.  **\[ユーザー インターフェイス機能\]** ペインで、**\[メニュー バーとツール バーを使用する\]** が選択されていることを確認します。  その他のオプションはそのままにします。  **\[次へ\]** をクリックして、**\[高度な機能\]** ペインを表示します。  
  
9. **\[高度な機能\]** ペインの **\[高度な機能\]** で、**\[ActiveX コントロール\]** と **\[コモン コントロール マニフェスト\]** のみを選択します。  **\[高度なフレーム ペイン\]** で、**\[ナビゲーション ウィンドウ\]** のみを選択します。  これにより、ウィンドウの左側に、`CMFCShellTreeCtrl` が埋め込まれた状態でナビゲーション ウィンドウが作成されます。  **\[次へ\]** をクリックして、**\[生成されたクラス\]** ペインを表示します。  
  
10. **\[生成されたクラス\]** ペインでは何も変更しません。  **\[完了\]** をクリックして、新しい MFC プロジェクトを作成します。  
  
11. アプリケーションをビルドして実行することにより、アプリケーションが正常に作成されたことを確認します。  アプリケーションをビルドするには、**\[ビルド\]** メニューの **\[ソリューションのビルド\]** をクリックします。  アプリケーションが正常にビルドされたら、**\[デバッグ\]** メニューの **\[デバッグ開始\]** をクリックして、アプリケーションを実行します。  
  
     標準メニュー バー、標準ツール バー、標準ステータス バー、およびウィンドウの左側に**フォルダー** ビューと**予定表**ビューのある Outlook バーを備えたアプリケーションが自動的に作成されます。  
  
### シェル リスト コントロールをドキュメント ビューに追加するには  
  
1.  ここでは、ウィザードによって作成されたビューに `CMFCShellListCtrl` のインスタンスを追加します。  **ソリューション エクスプローラー**で MFCShellControlsView.h ファイルをダブルクリックしてビューのヘッダー ファイルを開きます。  
  
     ヘッダー ファイルの先頭部分にある `#pragma once` ディレクティブを探します。  その直後に、次のコードを追加して、`CMFCShellListCtrl` のヘッダー ファイルをインクルードします。  
  
    ```  
    #include <afxShellListCtrl.h>  
    ```  
  
     次に、`CMFCShellListCtrl` 型のメンバー変数を追加します。  最初に、ヘッダー ファイルで次のコメントを探します。  
  
    ```  
    // Generated message map functions  
    ```  
  
     そのコメントの直前に、次のコードを追加します。  
  
    ```  
    private:  
        CMFCShellListCtrl m_wndList;  
    ```  
  
2.  **MFC アプリケーション ウィザード**によって既に `CMainFrame` クラスに `CMFCShellTreeCtrl` オブジェクトが作成されていますが、これはプロテクト メンバーです。  後で、このオブジェクトにアクセスします。  したがって、ここでアクセサーを作成します。  **ソリューション エクスプローラー**で MainFrm.h ヘッダー ファイルをダブルクリックして開きます。  次のコメントを探します。  
  
    ```  
    // Attributes  
    ```  
  
     この直後に、次のメソッド宣言を追加します。  
  
    ```  
    public:  
        CMFCShellTreeCtrl& GetShellTreeCtrl();  
    ```  
  
     次に、**ソリューション エクスプローラー**で MainFrm.cpp ソース ファイルをダブルクリックして開きます。  このファイルの末尾に、次のメソッド定義を追加します。  
  
    ```  
    CMFCShellTreeCtrl& CMainFrame::GetShellTreeCtrl()  
    {  
        return m_wndTree;  
    }  
    ```  
  
3.  **WM\_CREATE** Windows メッセージを処理するように `CMFCShellControlsView` クラスを更新します。  MFCShellControlsView.h ヘッダー ファイルを開き、次のコード行をクリックします。  
  
    ```  
    class CMFCShellControlsView : public CView  
    ```  
  
     次に、**\[プロパティ\]** ウィンドウで **\[メッセージ\]** アイコンをクリックします。  スクロール ダウンして **WM\_CREATE** メッセージを探します。  **WM\_CREATE** の横のドロップダウン リストで、**\[\<追加\>\> OnCreate\]** をクリックします。  これにより、メッセージ ハンドラーが作成され、MFC メッセージ マップが自動的に更新されます。  
  
     `OnCreate` メソッドで、独自の `CMFCShellListCtrl` オブジェクトを作成します。  MFCShellControlsView.cpp ソース ファイルで `OnCreate` メソッド定義を探し、その実装を次のコードに置き換えます。  
  
    ```  
    int CMFCShellControlsView::OnCreate(LPCREATESTRUCT lpCreateStruct)  
    {  
        if (CView::OnCreate(lpCreateStruct) == -1)  
            return -1;  
  
        CRect rectDummy (0, 0, 0, 0);  
        m_wndList.Create(WS_CHILD | WS_VISIBLE | LVS_REPORT,  
            rectDummy, this, 1);  
  
        return 0;  
    }  
    ```  
  
4.  **WM\_SIZE** メッセージについて、前の手順を繰り返します。  これにより、ユーザーがアプリケーション ウィンドウのサイズを変更するたびにアプリケーションのビューが再描画されるようになります。  `OnSize` メソッドの定義を次のコードに置き換えます。  
  
    ```  
    void CMFCShellControlsView::OnSize(UINT nType, int cx, int cy)  
    {  
        CView::OnSize(nType, cx, cy);  
        m_wndList.SetWindowPos(NULL, -1, -1, cx, cy,  
            SWP_NOMOVE | SWP_NOZORDER | SWP_NOACTIVATE);  
    }  
    ```  
  
5.  最後に、[CMFCShellTreeCtrl::SetRelatedList](../Topic/CMFCShellTreeCtrl::SetRelatedList.md) メソッドを使用して、`CMFCShellTreeCtrl` オブジェクトと `CMFCShellListCtrl` オブジェクトを関連付けます。  このメソッドを呼び出すと、`CMFCShellTreeCtrl` で選択された項目の内容が自動的に `CMFCShellListCtrl` に表示されます。  これは、[CView::OnActivateView](../Topic/CView::OnActivateView.md) からオーバーライドした `OnActivateView` メソッドで行います。  
  
     MFCShellControlsView.h ヘッダー ファイルの `CMFCShellControlsView` クラス宣言に、次のメソッド宣言を追加します。  
  
    ```  
    protected:  
        virtual void OnActivateView(BOOL bActivate,  
            CView* pActivateView,  
            CView* pDeactiveView);  
    ```  
  
     次に、このメソッドの定義を MFCShellControlsView.cpp ソース ファイルに追加します。  
  
    ```  
    void CMFCShellControlsView::OnActivateView(BOOL bActivate,  
        CView* pActivateView,  
        CView* pDeactiveView)   
    {  
        if (bActivate && AfxGetMainWnd() != NULL)  
        {  
            ((CMainFrame*)AfxGetMainWnd())->GetShellTreeCtrl().SetRelatedList(&m_wndList);  
        }  
  
        CView::OnActivateView(bActivate, pActivateView, pDeactiveView);  
    }  
    ```  
  
     `CMainFrame` クラスのメソッドを呼び出すため、MFCShellControlsView.cpp ソース ファイルの先頭部分に次の `#include` ディレクティブを追加する必要があります。  
  
    ```  
    #include "MainFrm.h"  
    ```  
  
6.  アプリケーションをビルドして実行することにより、アプリケーションが正常に作成されたことを確認します。  アプリケーションをビルドするには、**\[ビルド\]** メニューの **\[ソリューションのビルド\]** をクリックします。  アプリケーションが正常にビルドされたら、**\[デバッグ\]** メニューの **\[デバッグ開始\]** をクリックして、アプリケーションを実行します。  
  
     `CMFCShellTreeCtrl` で選択されている項目の詳細が、ビュー ペインに表示されるようになりました。  `CMFCShellTreeCtrl` でノードをクリックすると、`CMFCShellListCtrl` が自動的に更新されます。  また、`CMFCShellListCtrl` でフォルダーをダブルクリックすると、`CMFCShellTreeCtrl` が自動的に更新されます。  
  
     ツリー コントロールまたはリスト コントロールの任意の項目を右クリックします。  ファイル エクスプローラーを使用している場合と同じようなコンテキスト メニューが表示されます。  
  
## 次の手順  
  
-   ウィザードによって、**フォルダー** ペインと**予定表**ペインのある Outlook バーが作成されました。  エクスプローラー ウィンドウには、おそらく**予定表**ペインは必要ありません。  したがって、このペインを削除します。  
  
-   `CMFCShellListCtrl` では、**大きいアイコン**、**小さいアイコン**、**リスト**、**詳細**などのさまざまなモードでファイルを表示できます。  アプリケーションを更新して、この機能を実装します。  ヒントについては、「[Visual C\+\+ のサンプル](../top/visual-cpp-samples.md)」を参照してください。  
  
## 参照  
 [チュートリアル](../mfc/walkthroughs-mfc.md)