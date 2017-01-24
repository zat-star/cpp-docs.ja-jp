---
title: "チュートリアル: MFC プロジェクトへの D2D オブジェクトの追加 | Microsoft Docs"
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
  - "D2D [MFC]"
  - "MFC, D2D"
ms.assetid: dda36c33-c231-4da6-a62f-72d69a12b6dd
caps.latest.revision: 20
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# チュートリアル: MFC プロジェクトへの D2D オブジェクトの追加
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このチュートリアルでは、基本的な Direct2D \(D2D\) オブジェクトを Visual C\+\+ の Microsoft Foundation Class ライブラリ \(MFC\) プロジェクトに追加し、グラデーション背景に "Hello, world" と出力するアプリケーションに、このプロジェクトをビルドする方法について説明します。  
  
 ここでは、次の作業の手順を示します。  
  
-   MFC アプリケーションを作成する。  
  
-   純色ブラシと線形グラデーション ブラシを作成する。  
  
-   ウィンドウのサイズを変更したときに適切に変更されるようにグラデーション ブラシを変更する。  
  
-   D2D 描画ハンドラーを実装する。  
  
-   結果を確認する。  
  
 [!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]  
  
## 必須コンポーネント  
 このチュートリアルを完了するには、Visual Studio が必要です。  
  
### MFC アプリケーションを作成するには  
  
1.  **\[ファイル\]** メニューの **\[新規作成\]** をポイントし、**\[プロジェクト\]** をクリックします。  
  
2.  **\[新しいプロジェクト\]** ダイアログ ボックスで、左ペインの **\[インストールされたテンプレート\]** の下にある **\[Visual C\+\+\]** を展開し、**\[MFC\]** をクリックします。  中央のペインで、**\[MFC アプリケーション\]** をクリックします。  **\[名前\]** ボックスに、「`MFCD2DWalkthrough`」と入力します。  \[OK\] をクリックします。  
  
3.  **MFC アプリケーション ウィザード**で、どの設定も変更せずに **\[完了\]** をクリックします。  
  
### 純色ブラシと線形グラデーション ブラシを作成するには  
  
1.  **ソリューション エクスプローラー**で、**\[MFCD2DWalkthrough\]** プロジェクトの **\[ヘッダー ファイル\]** フォルダーにある MFCD2DWalkthroughView.h を開きます。  `CMFCD2DWalkthroughView` クラスに次のコードを追加して、3 つのデータ変数を作成します。  
  
    ```  
    CD2DTextFormat* m_pTextFormat;  
    CD2DSolidColorBrush* m_pBlackBrush;  
    CD2DLinearGradientBrush* m_pLinearGradientBrush;  
    ```  
  
     ファイルを保存して閉じます。  
  
2.  **\[ソース ファイル\]** フォルダーの MFCD2DWalkthroughView.cpp を開きます。  `CMFCD2DWalkthroughView` クラスのコンストラクターに、次のコードを追加します。  
  
    ```  
    // Enable D2D support for this window:  
    EnableD2DSupport();  
  
    // Initialize D2D resources:  
    m_pBlackBrush = new CD2DSolidColorBrush(GetRenderTarget(), D2D1::ColorF(D2D1::ColorF::Black));  
  
    m_pTextFormat = new CD2DTextFormat(GetRenderTarget(), _T("Verdana"), 50);  
    m_pTextFormat->Get()->SetTextAlignment(DWRITE_TEXT_ALIGNMENT_CENTER);  
    m_pTextFormat->Get()->SetParagraphAlignment(DWRITE_PARAGRAPH_ALIGNMENT_CENTER);  
  
    D2D1_GRADIENT_STOP gradientStops[2];  
  
    gradientStops[0].color = D2D1::ColorF(D2D1::ColorF::White);  
    gradientStops[0].position = 0.f;  
    gradientStops[1].color = D2D1::ColorF(D2D1::ColorF::Indigo);  
    gradientStops[1].position = 1.f;  
  
    m_pLinearGradientBrush = new CD2DLinearGradientBrush(GetRenderTarget(),   
        gradientStops, ARRAYSIZE(gradientStops),  
        D2D1::LinearGradientBrushProperties(D2D1::Point2F(0, 0), D2D1::Point2F(0, 0)));  
    ```  
  
     ファイルを保存して閉じます。  
  
### ウィンドウのサイズを変更したときに適切に変更されるようにグラデーション ブラシを変更するには  
  
1.  **\[プロジェクト\]** メニューの **\[クラス ウィザード\]** をクリックします。  
  
2.  **MFC クラス ウィザード**で、**\[クラス名\]** の下の \[`CMFCD2DWalkthroughView`\] を選択します。  
  
3.  **\[メッセージ\]** タブで、**\[メッセージ\]** ボックスの \[`WM_SIZE`\] を選択し、**\[ハンドラーの追加\]** をクリックします。  この操作により、`OnSize` メッセージ ハンドラーが `CMFCD2DWalkthroughView` クラスに追加されます。  
  
4.  **\[既存のハンドラー\]** ボックスの `OnSize` を選択します。  **\[コードの編集\]** をクリックして、`CMFCD2DWalkthroughView::OnSize` メソッドを表示します。  メソッドの末尾に次のコードを追加します。  
  
    ```  
    m_pLinearGradientBrush->SetEndPoint(CPoint(cx, cy));  
    ```  
  
     ファイルを保存して閉じます。  
  
### D2D 描画ハンドラーを実装するには  
  
1.  **\[プロジェクト\]** メニューの **\[クラス ウィザード\]** をクリックします。  
  
2.  **MFC クラス ウィザード**で、**\[クラス名\]** の下の \[`CMFCD2DWalkthroughView`\] を選択します。  
  
3.  **\[メッセージ\]** タブの **\[カスタム メッセージの追加\]** をクリックします。  
  
4.  **\[カスタム メッセージの追加\]** ダイアログ ボックスで、**\[カスタム Windows メッセージ\]** ボックスに「`AFX_WM_DRAW2D`」と入力します。  **\[メッセージ ハンドラー名\]** ボックスに、「`OnDraw2D`」と入力します。  **\[登録済みメッセージ\]** を選択し、**\[OK\]** をクリックします。  この操作により、`AFX_WM_DRAW2D` メッセージのメッセージ ハンドラーが `CMFCD2DWalkthroughView` クラスに追加されます。  
  
5.  **\[既存のハンドラー\]** ボックスの `OnDraw2D` を選択します。  **\[コードの編集\]** をクリックして、`CMFCD2DWalkthroughView::OnDraw2D` メソッドを表示します。  `CMFCD2DWalkthroughView::OnDrawD2D` メソッドに次のコードを使用します。  
  
    ```  
    afx_msg LRESULT CMFCD2DWalkthroughView::OnDraw2D(WPARAM wParam, LPARAM lParam)  
    {  
        CHwndRenderTarget* pRenderTarget = (CHwndRenderTarget*)lParam;  
        ASSERT_VALID(pRenderTarget);  
  
        CRect rect;  
        GetClientRect(rect);  
  
        pRenderTarget->FillRectangle(rect, m_pLinearGradientBrush);  
        pRenderTarget->DrawText(_T("Hello, World!"), rect, m_pBlackBrush, m_pTextFormat);  
  
        return TRUE;  
    }  
    ```  
  
     ファイルを保存して閉じます。  
  
### 結果を確認するには  
  
1.  アプリケーションをビルドして実行します。  ウィンドウのサイズを変更すると、グラデーションの四角形が変更されます。四角形の中央に "Hello World\!" と表示されます。  
  
## 参照  
 [チュートリアル](../mfc/walkthroughs-mfc.md)