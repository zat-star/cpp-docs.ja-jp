---
title: "テクニカル ノート 17: ウィンドウ オブジェクトの破棄 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.objects"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "破棄 (ウィンドウを)"
  - "PostNcDestroy メソッド"
  - "TN017"
ms.assetid: 5bf208a5-5683-439b-92a1-547c5ded26cd
caps.latest.revision: 15
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# テクニカル ノート 17: ウィンドウ オブジェクトの破棄
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは [CWnd::PostNcDestroy](../Topic/CWnd::PostNcDestroy.md) のメソッドの使用について説明します。  `CWnd`のカスタマイズされた割り当て\-派生オブジェクトを実行する場合は、このメソッドを使用します。  ここでは、`delete` の演算子の代わりに、C \+\+.ウィンドウ オブジェクトを破棄するために [CWnd::DestroyWindow](../Topic/CWnd::DestroyWindow.md) 理由を使用する方法を示しています。  
  
 このトピックで説明するガイドラインに従うと、クリーンアップいくつかの問題があります。  これらの問題を忘れると、削除を\/自由な C\+\+ のメモリ `HWND`s などのシステム リソースを解放されていない、またはあまり多くの時間オブジェクトを解放するなどの問題が発生する可能性があります。  
  
## 問題  
 各ウィンドウ オブジェクト \(`CWnd`から派生したクラスのオブジェクト\) は、どちらの C\+\+. C\+\+ オブジェクトと `HWND`を表します。  C\+\+ オブジェクトはアプリケーション ヒープに割り当てられ、`HWND`s はウィンドウ マネージャーによってシステム リソースに割り当てられます。  ウィンドウ オブジェクトを破棄するいくつかの方法があるため、システム リソースまたはメモリ リークを防ぐ規則のセットを指定する必要があります。  これらの規則は、オブジェクト、およびウィンドウ ハンドルが 1 回以上破棄されることを防ぐ。  
  
## Windows の破棄  
 次は、ウィンドウ オブジェクトを破棄する 2 とおりの方法で許可された:  
  
-   `CWnd::DestroyWindow` または Windows API `DestroyWindow`を呼び出す。  
  
-   `delete` の演算子を使用して明示的に削除します。  
  
 最初のケースが膨大に共通です。  ここでは、コードが `DestroyWindow` を直接呼出さなくても適用されます。  ユーザーが直接フレーム ウィンドウを閉じると、この操作は `WM_CLOSE` メッセージを生成し、このメッセージに対する既定の応答が親ウィンドウが破棄されるときに、すべての子の `DestroyWindow` を `DestroyWindow.`、Windows を呼び出します。  
  
 2 番目の場合、ウィンドウ オブジェクト `delete` の演算子の使用は、ほとんどの場合です。  次に `delete` を使用するケースが適切な選択です。  
  
## CWnd::PostNcDestroy の自動クリーンアップ  
 システムがウィンドウを破棄すると、ウィンドウに送信された最後の Windows メッセージが `WM_NCDESTROY`です。  このメッセージの既定の `CWnd` ハンドラーは [CWnd::OnNcDestroy](../Topic/CWnd::OnNcDestroy.md)です。  `OnNcDestroy` は C\+\+ オブジェクトから `HWND` をデタッチし、仮想関数 `PostNcDestroy`を呼び出します。  このクラスは C\+\+ オブジェクトを削除するには、この関数をオーバーライドします。  
  
 `CWnd::PostNcDestroy` の既定の実装はスタック フレームに割り当てられているか、またはそのほかのオブジェクトに埋め込まれているウィンドウ オブジェクトに適した何もしません。  これにより、他のオブジェクトを持たないヒープに割り当てられたように設計されたウィンドウ オブジェクトには適切ではありません。  つまり、他の C\+\+ オブジェクトに埋め込まれないウィンドウ オブジェクトには適切ではありません。  
  
 `delete this`を実行 `PostNcDestroy` ヒープのメソッドのオーバーライドでだけが割り当てられるようにデザインされているクラスです。  このステートメントは C\+\+ オブジェクトに関連付けられているメモリを解放します。  `m_hWnd` が NULL 以外の場合は、既定の `CWnd` のデストラクターが `DestroyWindow` を呼び出しますが、これは無限再帰のハンドルがクリーンアップのフェーズでデタッチし、null である可能性があります。  
  
> [!NOTE]
>  システムは、通常、Windows の `WM_NCDESTROY` メッセージを処理し、`HWND` と C\+\+ のウィンドウ オブジェクトがアタッチされなく後 `CWnd::PostNcDestroy` を呼び出します。  システムは、エラーが発生 [CWnd::Create](../Topic/CWnd::Create.md) のほとんどの呼び出しの実装の `CWnd::PostNcDestroy` を呼び出します。  自動クリーンアップの規則は、このトピックの後半で説明します。  
  
## 自動クリーンアップ クラス  
 次のクラスは、クリーンアップのようには設計されていません。  これらは、他の C\+\+ オブジェクトで、スタックに正常に埋め込まれます:  
  
-   すべての標準のコントロール \(`CStatic`、`CEdit`、`CListBox`など\)。  
  
-   `CWnd` \(たとえば、カスタム コントロール\) から直接派生される子ウィンドウ。  
  
-   分割ウィンドウ \(`CSplitterWnd`\)。  
  
-   既定のコントロール バー \(`CControlBar`から派生されるクラスは、コントロール バー オブジェクトの自動削除を有効にするための [テクニカル ノート 31](../mfc/tn031-control-bars.md) を参照します\)。  
  
-   スタック フレームのモーダル ダイアログ用に設計されたダイアログ`CDialog` \(\)。  
  
-   すべての標準ダイアログ ボックスが `CFindReplaceDialog`を除く\)。  
  
-   ClassWizard で作成された既定ダイアログ。  
  
 次のクラスは、クリーンアップ用に設計されています。  これらはヒープで一般に個別に割り当てられています:  
  
-   メイン フレーム ウィンドウ `CFrameWnd` \(から直接的または間接的に派生される\)。  
  
-   ビュー ウィンドウ \(`CView`から直接的または間接的に派生される\)。  
  
 これらの規則を中断する場合は、派生クラスで `PostNcDestroy` のメソッドをオーバーライドする必要があります。  クラスに自動クリーンアップを追加するには、基本クラスを呼び出して `delete this`をします。  クラスから自動クリーンアップを削除するには、直接基本クラスの `PostNcDestroy` のメソッドの代わりに `CWnd::PostNcDestroy` を直接呼び出します。  
  
 自動クリーンアップの動作を変更する最も一般的な用途は、ヒープに割り当てることができるモードレス ダイアログ ボックスを作成します。  
  
## いつ削除を呼び出します。  
 これはウィンドウ オブジェクトを破棄するに `DestroyWindow` を C\+\+ のメソッドまたはグローバル `DestroyWindow` API を呼び出すことをお勧めします。  
  
 MDI 子ウィンドウを破棄するには、グローバルな `DestroyWindow` API を呼び出さないでください。  仮想メソッド `CWnd::DestroyWindow` を代わりに使用する必要があります。  
  
 自動クリーンアップを実行 `delete` の演算子を使用すると、C\+\+ ウィンドウ オブジェクトに VTBL が派生クラスを適切に示す `CWnd::~CWnd` のデストラクターの `DestroyWindow` を呼び出そうとすると、メモリ リークが発生することがあります。  これは、システムが呼び出すと破棄の適切なメソッドが見つけることができないためです。  `delete` の代わりに `DestroyWindow` を使用してこれらの問題を回避できます。  これがないエラーになるため、デバッグ モードでコンパイルはリスクがある場合、次の警告を生成します。  
  
```  
Warning: calling DestroyWindow in CWnd::~CWnd  
   OnDestroy or PostNcDestroy in derived class will not be called  
```  
  
 自動クリーンアップを実行する C\+\+ ウィンドウ オブジェクトの場合、`DestroyWindow`を呼び出す必要があります。  `delete` の演算子を直接使用している場合は、MFC の診断メモリ アロケーターは 2 回メモリを解放することが通知されます。  2 回以上の出現が `PostNcDestroy`の自動クリーンアップの実装の `delete this` に明示的な呼び出しと間接呼び出しです。  
  
 非自動クリーンアップ オブジェクトの `DestroyWindow` を呼び出した後、C\+\+ オブジェクトが存在します `m_hWnd`、が null です。  自動クリーンアップ オブジェクトの `DestroyWindow` を呼び出した後、C\+\+ オブジェクトは、`PostNcDestroy`の自動クリーンアップの実装の C\+\+ delete 演算子によって解放されます。  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)