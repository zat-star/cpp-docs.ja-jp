---
title: "チュートリアル: MFC プロジェクトへのアニメーションの追加 | Microsoft Docs"
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
  - "アニメーション [MFC]"
  - "MFC, アニメーション"
ms.assetid: 004f832c-9fd5-4f88-9ca9-ae65dececdc2
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# チュートリアル: MFC プロジェクトへのアニメーションの追加
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このチュートリアルでは、Visual C\+\+ の Microsoft Foundation Class ライブラリ \(MFC\) プロジェクトに基本的なアニメーション オブジェクトを追加する方法について説明します。  
  
 ここでは、次の作業の手順を示します。  
  
-   MFC アプリケーションを作成する。  
  
-   メニューを追加し、アニメーションを開始および停止するコマンドを追加する。  
  
-   開始コマンドと停止コマンドのハンドラーを作成する。  
  
-   アニメーション オブジェクトをプロジェクトに追加する。  
  
-   アニメーション オブジェクトをウィンドウの中央に配置する。  
  
-   結果を確認する。  
  
 [!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]  
  
## 必須コンポーネント  
 このチュートリアルを完了するには、Visual Studio が必要です。  
  
### MFC アプリケーションを作成するには  
  
1.  **\[ファイル\]** メニューの **\[新規作成\]** をポイントし、**\[プロジェクト\]** をクリックします。  
  
2.  **\[新しいプロジェクト\]** ダイアログ ボックスで、左ペインの **\[インストールされたテンプレート\]** の下にある **\[Visual C\+\+\]** を展開し、**\[MFC\]** をクリックします。  中央のペインで、**\[MFC アプリケーション\]** をクリックします。  **\[名前\]** ボックスに、「`MFCAnimationWalkthrough`」と入力します。  \[OK\] をクリックします。  
  
3.  **\[MFC アプリケーション ウィザード\]** ダイアログ ボックスで、**\[アプリケーションの種類\]** が **\[マルチ ドキュメント\]**、**\[プロジェクト形式\]** が **\[Visual Studio\]** にそれぞれ設定され、**\[ドキュメント\/ビュー アーキテクチャ サポート\]** がオンになっていることを確認します。  \[完了\] をクリックします。  
  
### メニューを追加し、アニメーションを開始および停止するコマンドを追加するには  
  
1.  **\[表示\]** メニューの **\[その他のウィンドウ\]** をポイントし、**\[リソース ビュー\]** をクリックします。  
  
2.  **\[リソース ビュー\]** で **\[メニュー\]** フォルダーに移動し、フォルダーを開きます。  変更対象の `IDR_MFCAnimationWalTYPE` リソースをダブルクリックして開きます。  
  
3.  メニュー バー、**\[ここへ入力\]** ボックスで、Animation メニューを作成します `A&nimation` 型。  
  
4.  **\[アニメーション\]** で、**\[ここへ入力\]** ボックスの開始を作成する型 `開始 &次へ` はコマンドを転送します。  
  
5.  **\[前方に開始します。\]** で、**\[ここへ入力\]** ボックスに" `開始 &前へ`。  
  
6.  **\[Start Backward の\]** で、**\[ここへ入力\]** ボックスで停止コマンドを作成する `S&上` 型。  
  
7.  MFCAnimationWalkthrough.rc を保存して閉じます。  
  
8.  **ソリューション エクスプローラー**で、変更対象の MainFrm.cpp をダブルクリックして開きます。  `CMainFrame::OnCreate` メソッドで、`lstBasicCommands.AddTail` の複数の呼び出しが含まれているセクションを見つけます。  このセクションの直後に次のコードを追加します。  
  
    ```  
    lstBasicCommands.AddTail(ID_ANIMATION_STARTFORWARD);  
    lstBasicCommands.AddTail(ID_ANIMATION_STARTBACKWARD);  
    lstBasicCommands.AddTail(ID_ANIMATION_STOP);  
    ```  
  
9. ファイルを保存して閉じます。  
  
### 開始コマンドと停止コマンドのハンドラーを作成するには  
  
1.  **\[プロジェクト\]** メニューの **\[クラス ウィザード\]** をクリックします。  
  
2.  **MFC クラス ウィザード**で、**\[クラス名\]** の下の \[`CMFCAnimationWalkthroughView`\] を選択します。  
  
3.  **\[コマンド\]** タブで、**\[オブジェクト ID\]** ボックスの \[`ID_ANIMATION_STARTFORWARD`\] を選択し、**\[メッセージ\]** ボックスの \[`COMMAND`\] を選択します。  **\[ハンドラーの追加\]** をクリックします。  
  
4.  **\[メンバー関数の追加\]** ダイアログ ボックスで、**\[OK\]** をクリックします。  
  
5.  **\[オブジェクト ID\]** ボックスの \[`ID_ANIMATION_STARTBACKWARD`\] を選択し、**\[メッセージ\]** ボックスの \[`COMMAND`\] を選択します。  **\[ハンドラーの追加\]** をクリックします。  
  
6.  **\[メンバー関数の追加\]** ダイアログ ボックスで、**\[OK\]** をクリックします。  
  
7.  **\[オブジェクト ID\]** ボックスの \[`ID_ANIMATION_STOP`\] を選択し、**\[メッセージ\]** ボックスの \[`COMMAND`\] を選択します。  **\[ハンドラーの追加\]** をクリックし、**\[OK\]** をクリックします。  
  
8.  **\[メンバー関数の追加\]** ダイアログ ボックスで、**\[OK\]** をクリックします。  
  
9. **MFC クラス ウィザード**で **\[OK\]** をクリックします。  
  
10. MFCAnimationWalkthroughView.cpp を保存します。保存すると、このファイルがエディターで開かれますが、これを閉じないようにしてください。  
  
### アニメーション オブジェクトをプロジェクトに追加するには  
  
1.  ソリューション エクスプローラーで、変更対象の MFCAnimationWalkthroughView.h をダブルクリックして開きます。  `CMFCAnimationWalkthroughView` クラスの定義の直前に次のコードを追加して、カスタム アニメーション コントローラーを作成します。このコントローラーで、アニメーション オブジェクトとのスケジュールの競合を処理します。  
  
    ```  
    class CCustomAnimationController : public CAnimationController  
    {  
    public:  
        CCustomAnimationController()  
        {  
        }  
  
        virtual BOOL OnHasPriorityTrim(CAnimationGroup* pGroupScheduled, CAnimationGroup* pGroupNew, UI_ANIMATION_PRIORITY_EFFECT priorityEffect)  
        {  
            return TRUE;  
        }  
    };  
    ```  
  
2.  `CMFCAnimationWalkthroughView` クラスの末尾に、次のコードを追加します。  
  
    ```  
    CCustomAnimationController m_animationController;  
    CAnimationColor m_animationColor;   
    CAnimationRect m_animationRect;  
    ```  
  
3.  `DECLARE_MESSAGE_MAP()` コード行の後に、次のコードを追加します。  
  
    ```  
    void Animate(BOOL bDirection);  
    ```  
  
4.  ファイルを保存して閉じます。  
  
5.  MFCAnimationWalkthroughView.cpp で、ファイルの先頭にある `#include` ステートメントの後のクラス メソッドの前に、次のコードを追加します。  
  
    ```  
    static int nAnimationGroup = 0;  
    static int nInfoAreaHeight = 40;  
    ```  
  
6.  `CMFCAnimationWalkthroughView` のコンストラクターの末尾に、次のコードを追加します。  
  
    ```  
    m_animationController.EnableAnimationTimerEventHandler();  
    m_animationController.EnablePriorityComparisonHandler(UI_ANIMATION_PHT_TRIM);  
  
    m_animationColor = RGB(255, 255, 255);  
    m_animationRect = CRect(0, 0, 0, 0);  
  
    m_animationColor.SetID(-1, nAnimationGroup);  
    m_animationRect.SetID(-1, nAnimationGroup);  
  
    m_animationController.AddAnimationObject(&m_animationColor);  
    m_animationController.AddAnimationObject(&m_animationRect);  
    ```  
  
7.  `CAnimationWalthroughView::PreCreateWindow` メソッドを見つけ、このメソッドを次のコードで置き換えます。  
  
    ```  
    BOOL CMFCAnimationWalkthroughView::PreCreateWindow(CREATESTRUCT& cs)  
    {  
        // TODO: Modify the Window class or styles here by modifying  
        //  the CREATESTRUCT cs  
  
        m_animationController.SetRelatedWnd(this);  
        return CView::PreCreateWindow(cs);  
    }  
    ```  
  
8.  `CAnimationWalkthroughView::OnDraw` メソッドを見つけ、このメソッドを次のコードで置き換えます。  
  
    ```  
    void CMFCAnimationWalkthroughView::OnDraw(CDC* pDC)  
    {  
        CMFCAnimationWalkthroughDoc* pDoc = GetDocument();  
        ASSERT_VALID(pDoc);  
        if (!pDoc)  
            return;  
  
        // TODO: add draw code for native data here  
        CMemDC dcMem(*pDC, this);  
        CDC& dc = dcMem.GetDC();  
  
        CRect rect;  
        GetClientRect(rect);  
  
        dc.FillSolidRect(rect, GetSysColor(COLOR_WINDOW));  
  
        CString strRGB;  
        strRGB.Format(_T("Fill Color is: %d; %d; %d"), GetRValue(m_animationColor), GetGValue(m_animationColor), GetBValue(m_animationColor));  
  
        dc.DrawText(strRGB, rect, DT_CENTER);  
        rect.top += nInfoAreaHeight;  
  
        CBrush br;  
  
        br.CreateSolidBrush(m_animationColor);  
        CBrush* pBrushOld = dc.SelectObject(&br);  
  
        dc.Rectangle((CRect)m_animationRect);  
        dc.SelectObject(pBrushOld);  
    }  
    ```  
  
9. ファイルの末尾に、次のコードを追加します。  
  
    ```  
    void CMFCAnimationWalkthroughView::Animate(BOOL bDirection)  
    {  
        static UI_ANIMATION_SECONDS duration = 3;  
        static DOUBLE dblSpeed = 35.;  
        static BYTE nStartColor = 50;  
        static BYTE nEndColor = 255;  
  
        BYTE nRedColorFinal = bDirection ? nStartColor : nEndColor;  
        BYTE nGreenColorFinal = bDirection ? nStartColor : nEndColor;  
        BYTE nBlueColorFinal = bDirection ? nStartColor : nEndColor;  
  
        CLinearTransition* pRedTransition = new CLinearTransition(duration, (DOUBLE)nRedColorFinal);  
        CSmoothStopTransition* pGreenTransition = new CSmoothStopTransition(duration, (DOUBLE)nGreenColorFinal);  
        CLinearTransitionFromSpeed* pBlueTransition = new CLinearTransitionFromSpeed(dblSpeed, (DOUBLE)nBlueColorFinal);  
  
        m_animationColor.AddTransition(pRedTransition, pGreenTransition, pBlueTransition);  
  
        CRect rectClient;  
        GetClientRect(rectClient);  
        rectClient.top += nInfoAreaHeight;  
  
        int nLeftFinal = bDirection ? rectClient.left : rectClient.CenterPoint().x;  
        int nTopFinal = bDirection ? rectClient.top : rectClient.CenterPoint().y;  
        int nRightFinal = bDirection ? rectClient.right : rectClient.CenterPoint().x;  
        int nBottomFinal = bDirection ? rectClient.bottom : rectClient.CenterPoint().y;  
  
        CLinearTransition* pLeftTransition = new CLinearTransition(duration, nLeftFinal);  
        CLinearTransition* pTopTransition = new CLinearTransition(duration, nTopFinal);  
        CLinearTransition* pRightTransition = new CLinearTransition(duration, nRightFinal);  
        CLinearTransition* pBottomTransition = new CLinearTransition(duration, nBottomFinal);  
  
        m_animationRect.AddTransition(pLeftTransition, pTopTransition, pRightTransition, pBottomTransition);  
  
        CBaseKeyFrame* pKeyframeStart = CAnimationController::GetKeyframeStoryboardStart();  
        CKeyFrame* pKeyFrameEnd = m_animationController.CreateKeyframe(nAnimationGroup, pBlueTransition);  
  
        pLeftTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);  
        pTopTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);  
        pRightTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);  
        pBottomTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);  
  
        m_animationController.AnimateGroup(nAnimationGroup);  
    }  
    ```  
  
10. **\[プロジェクト\]** メニューの **\[クラス ウィザード\]** をクリックします。  
  
11. **MFC クラス ウィザード**で、**\[クラス名\]** の下の \[`CMFCAnimationWalkthroughView`\] を選択します。  
  
12. **\[メッセージ\]** タブで、**\[メッセージ\]** ボックスの \[`WM_ERASEBKGND`\] を選択し、**\[ハンドラーの追加\]** をクリックして、**\[OK\]** をクリックします。  
  
13. MFCAnimationWalkthroughView.cpp で、アニメーション オブジェクトが再描画されたときのちらつきを減らすために、`OnEraseBkgnd` の実装を次のコードで置き換えます。  
  
    ```  
    BOOL CMFCAnimationWalkthroughView::OnEraseBkgnd(CDC* /*pDC*/)  
    {  
        return TRUE;  
    }  
    ```  
  
14. `CMFCAnimationWalkthroughView::OnAnimationStartforward`、`CMFCAnimationWalkthroughView::OnAnimationStartbackward`、および `CMFCAnimationWalkthroughView::OnAnimationStop` の各実装を次のコードで置き換えます。  
  
    ```  
    void CMFCAnimationWalkthroughView::OnAnimationStartforward()  
    {  
        Animate(TRUE);  
    }  
  
    void CMFCAnimationWalkthroughView::OnAnimationStartbackward()  
    {  
        Animate(FALSE);  
    }  
  
    void CMFCAnimationWalkthroughView::OnAnimationStop()  
    {  
        IUIAnimationManager* pManager = m_animationController.GetUIAnimationManager();  
        if (pManager != NULL)  
        {  
            pManager->AbandonAllStoryboards();  
        }  
    }  
  
    ```  
  
15. ファイルを保存して閉じます。  
  
### アニメーション オブジェクトをウィンドウの中央に配置するには  
  
1.  **ソリューション エクスプローラー**で、変更対象の MFCAnimationWalkthroughView.h をダブルクリックして開きます。  `CMFCAnimationWalkthroughView` クラスの末尾にある `m_animationRect` の定義の直後に、次のコードを追加します。  
  
    ```  
    BOOL m_bCurrentDirection;  
    ```  
  
2.  ファイルを保存して閉じます。  
  
3.  **\[プロジェクト\]** メニューの **\[クラス ウィザード\]** をクリックします。  
  
4.  **MFC クラス ウィザード**で、**\[クラス名\]** の下の \[`CMFCAnimationWalkthroughView`\] を選択します。  
  
5.  **\[メッセージ\]** タブで、**\[メッセージ\]** ボックスの \[`WM_SIZE`\] を選択し、**\[ハンドラーの追加\]** をクリックして、**\[OK\]** をクリックします。  
  
6.  MFCAnimationWalkthroughView.cpp で、`CMFCAnimationWalkthroughView::OnSize` のコードを次のコードで置き換えます。  
  
    ```  
    void CMFCAnimationWalkthroughView::OnSize(UINT nType, int cx, int cy)  
    {  
        CView::OnSize(nType, cx, cy);  
  
        CRect rect;  
        GetClientRect(rect);  
        rect.top += nInfoAreaHeight;  
  
        CRect rectAnim = m_animationRect;  
        m_animationRect = CRect(CPoint(rect.CenterPoint().x - rectAnim.Width() / 2,   
                                rect.CenterPoint().y - rectAnim.Height() / 2),   
                                rectAnim.Size());  
  
        if (m_animationController.IsAnimationInProgress())  
        {  
            Animate(m_bCurrentDirection);  
        }  
    }  
    ```  
  
7.  `CMFCAnimationWalkthroughView` のコンストラクターの先頭に、次のコードを追加します。  
  
    ```  
    m_bCurrentDirection = TRUE;  
    ```  
  
8.  `CMFCAnimationWalkthroughView::Animate` メソッドの先頭に、次のコードを追加します。  
  
    ```  
    m_bCurrentDirection = bDirection;  
    ```  
  
9. ファイルを保存して閉じます。  
  
### 結果を確認するには  
  
1.  アプリケーションをビルドして実行します。  **\[Animation\]** メニューの **\[Start Forward\]** をクリックします。  四角形が表示された後、中央の領域が塗りつぶされます。  **\[Start Backward\]** をクリックするとアニメーションが逆転再生され、**\[Stop\]** をクリックするとアニメーションが停止します。  アニメーションの進行に伴って四角形の塗りつぶしの色が変化し、現在の色がアニメーション ウィンドウの上部に表示されます。  
  
## 参照  
 [チュートリアル](../mfc/walkthroughs-mfc.md)