---
title: "テクニカル ノート 6: メッセージ マップ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.messages.maps"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "メッセージ マップ [C++], Windows メッセージング"
  - "ON_COMMAND マクロ"
  - "ON_COMMAND_EX マクロ"
  - "ON_COMMAND_RANGE マクロ"
  - "ON_COMMAND_RANGE_EX マクロ"
  - "ON_CONTROL マクロ"
  - "ON_CONTROL_RANGE マクロ"
  - "ON_MESSAGE マクロ"
  - "ON_NOTIFY メッセージ"
  - "ON_NOTIFY_RANGE マクロ"
  - "ON_REGISTERED_MESSAGE マクロ"
  - "ON_UPDATE_COMMAND_UI マクロ"
  - "TN006"
  - "Windows メッセージ [C++], メッセージ マップ"
ms.assetid: af4b6794-4b40-4f1e-ad41-603c3b7409bb
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# テクニカル ノート 6: メッセージ マップ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、MFC のメッセージ マップ機能について説明します。  
  
## 問題  
 Microsoft Windows はメッセージング機能を使用して、ウィンドウ クラスの仮想関数を実装します。  含まれる多くメッセージが原因で各 Windows メッセージに別の仮想関数が指定されている場合は禁則に大きな vtable が作成されます。  
  
 システム定義の Windows メッセージの数が時間の経過とともに変化するため、アプリケーションが独自の Windows メッセージを定義できるので、メッセージ マップは既存のコードの破損インターフェイスの変更を防ぐ間接操作のレベルを提供します。  
  
## 概要  
 MFC は、ウィンドウに送信されたメッセージを処理するために、従来の Windows ベースのプログラムで使用する switch ステートメントの代わりに使用します。  メッセージのメソッドへの割り当てがメッセージ ウィンドウが受け取ったときに適切なメソッドが自動的に呼び出されるように定義できます。  このメッセージ マップ機能は仮想関数と類似するように設計されていますが、C\+\+ 仮想関数ではない追加的な利益があります。  
  
## メッセージ マップの定義  
 [DECLARE\_MESSAGE\_MAP](../Topic/DECLARE_MESSAGE_MAP.md) マクロはクラスの 3 人のメンバーを宣言します。  
  
-   `AFX_MSGMAP_ENTRY` エントリのプライベートな配列は `_messageEntries`と呼ばれます。  
  
-   `_messageEntries` の配列を指す `AFX_MSGMAP` の保護されたな構造体は `messageMap` と呼ばれます。  
  
-   `messageMap`のアドレスを返します保護されたな仮想関数は `GetMessageMap` と呼ばれます。  
  
 このマクロでは、メッセージ マップを使用して、クラスの宣言に配置する必要があります。  規則では、クラス宣言の最後にあります。  たとえば、次のようになります。  
  
```  
class CMyWnd : public CMyParentWndClass  
{  
    // my stuff...  
  
protected:  
    //{{AFX_MSG(CMyWnd)  
    afx_msg void OnPaint();  
    //}}AFX_MSG  
  
    DECLARE_MESSAGE_MAP()  
};  
```  
  
 これにより、新しいクラスを作成するときは、AppWizard で生成された形式と ClassWizard です。  \/\/と\/\/{{}}角かっこが ClassWizard に必要です。  
  
 メッセージ マップの表では、メッセージ マップ エントリに展開する一連のマクロを使用して定義されます。  テーブルは未処理のメッセージが渡される親クラスとこのメッセージ マップによって処理されるクラスを定義する [BEGIN\_MESSAGE\_MAP](../Topic/BEGIN_MESSAGE_MAP.md) のマクロは、で始まります。  テーブルは [END\_MESSAGE\_MAP](../Topic/END_MESSAGE_MAP.md) マクロ呼び出しで終了します。  
  
 この二つのマクロは、間にこのメッセージ マップに処理される各メッセージのエントリがあります。  すべての標準 Windows メッセージにそのメッセージのエントリを生成するフォーム ON\_WM\_*MESSAGE\_NAME* マクロがあります。  
  
 標準関数シグネチャは、Windows メッセージのパラメーターを展開し、タイプ セーフを実現するために定義されています。  これらのシグネチャは [CWnd](../Topic/CWnd%20Class.md)の宣言のファイル Afxwin.h で表示されることがあります。  それぞれに簡単に識別できるように `afx_msg` キーワードでマークされます。  
  
> [!NOTE]
>  ClassWizard はメッセージ マップ ハンドラー宣言で `afx_msg` キーワードを使用する必要があります。  
  
 これらの関数のシグネチャが単純な規則を使用して派生されました。  関数の名前は `"On`」から開始されます。  これは「WM\_」と削除される Windows メッセージの名前および大文字に記述されている各単語の最初の文字が続きます。  パラメーターの順序は `LOWORD` \(`lParam`\) と `HIWORD` \(`lParam`\) は、`wParam` です。  使用されていないパラメーターが渡されません。  MFC クラスでラップされるすべてのハンドルが適切な MFC オブジェクトへのポインターに変換されます。  次の例に `WM_PAINT` メッセージを処理し `CMyWnd::OnPaint` 関数を呼び出す方法を示しています。:  
  
```  
BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)  
    //{{AFX_MSG_MAP(CMyWnd)  
    ON_WM_PAINT()  
    //}}AFX_MSG_MAP  
END_MESSAGE_MAP()  
```  
  
 メッセージ マップ表に、関数やクラス定義のスコープ外で定義されている必要があります。  これは、extern 「C」ブロックに配置する必要があります。  
  
> [!NOTE]
>  ClassWizard は\/\/と\/\/{{}}コメントかっこの間で発生するメッセージ マップ エントリを変更します。  
  
## ユーザー定義のな Windows メッセージ  
 ユーザー定義メッセージをメッセージ マップに [ON\_MESSAGE](../Topic/ON_MESSAGE.md) マクロを使用して含まれている可能性があります。  このマクロは、フォームのメッセージ番号とメソッドを、T:  
  
```  
    // inside the class declaration  
    afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);  
  
    #define WM_MYMESSAGE (WM_USER + 100)  
  
BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)  
    ON_MESSAGE(WM_MYMESSAGE, OnMyMessage)  
END_MESSAGE_MAP()  
```  
  
 この例では、ユーザー定義メッセージの `WM_USER` 標準ベースから派生される Windows メッセージ ID を持つカスタム メッセージのハンドラーを作成します。  次の例に示します。このハンドラーを呼び出す方法を示しています。:  
  
```  
CWnd* pWnd = ...;  
pWnd->SendMessage(WM_MYMESSAGE);  
```  
  
 この手法を使用したユーザー定義メッセージの範囲は 0x7fff に範囲 `WM_USER` にする必要があります。  
  
> [!NOTE]
>  ClassWizard は ClassWizard のユーザー インターフェイスの `ON_MESSAGE` のハンドラー ルーチンをサポートしません。  Visual C\+\+ エディターから手動で入力する必要があります。  ClassWizard はこれらのエントリを解析し、他のメッセージ マップ エントリと同様に、参照することができます。  
  
## 登録された Windows メッセージ  
 [RegisterWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms644947) 関数がシステム全体で一意であることが保証されている新しいウィンドウ メッセージを定義するために使用されます。  マクロ `ON_REGISTERED_MESSAGE` がそれらのメッセージを処理するために使用されます。  このマクロは、登録されているウィンドウ メッセージ ID を含む `UINT NEAR` 変数の名前を受け入れます。  次に例を示します。  
  
```  
class CMyWnd : public CMyParentWndClass  
{  
public:  
    CMyWnd();  
  
    //{{AFX_MSG(CMyWnd)  
    afx_msg LRESULT OnFind(WPARAM wParam, LPARAM lParam);  
    //}}AFX_MSG  
  
    DECLARE_MESSAGE_MAP()  
};  
  
static UINT NEAR WM_FIND = RegisterWindowMessage("COMMDLG_FIND");  
  
BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)  
    //{{AFX_MSG_MAP(CMyWnd)  
    ON_REGISTERED_MESSAGE(WM_FIND, OnFind)  
    //}}AFX_MSG_MAP  
END_MESSAGE_MAP()  
```  
  
 登録された Windows メッセージ ID の変数 \(この例で WM\_FIND\) は `ON_REGISTERED_MESSAGE` が実装される方法に `NEAR` の変数である必要があります。  
  
 この手法を使用したユーザー定義メッセージの範囲は範囲に 0xC000 0xFFFF にあります。  
  
> [!NOTE]
>  ClassWizard は ClassWizard のユーザー インターフェイスの `ON_REGISTERED_MESSAGE` のハンドラー ルーチンをサポートしません。  テキスト エディターから手動で入力する必要があります。  ClassWizard はこれらのエントリを解析し、他のメッセージ マップ エントリと同様に、参照することができます。  
  
## コマンド メッセージ  
 メニュー コマンドとアクセラレータのメッセージが `ON_COMMAND` マクロのメッセージ マップで処理されます。  このマクロは、コマンド ID とメソッドを受け取ります。  指定したコマンド ID を持つ `wParam` がある `WM_COMMAND` 特定のメッセージをメッセージ マップ エントリに指定されたメソッドによって処理されます。  コマンド ハンドラーのメンバー関数では、パラメーターおよびサービスの `void`を受け取りません。  マクロに次のフォームがあります:  
  
```  
ON_COMMAND(id, memberFxn)  
```  
  
 コマンド更新メッセージは同じ機構を通じてルーティングされますが、`ON_UPDATE_COMMAND_UI` マクロを使用します。  更新コマンド ハンドラーのメンバー関数は [CCmdUI](../Topic/CCmdUI%20Class.md) オブジェクトが単一のパラメーター、ポインター、およびメッセージの `void`を受け取ります。  マクロにフォームがあります。  
  
```  
ON_UPDATE_COMMAND_UI(id, memberFxn)  
```  
  
 上級ユーザーはコマンド メッセージ ハンドラー拡張子フォームである `ON_COMMAND_EX` マクロを使用できます。  マクロは `ON_COMMAND` 機能のスーパーセットが用意されています。  拡張コマンド ハンドラーのメンバー関数は、コマンド ID を含む受け取り、`BOOL`を返します。単一のパラメーターを、`UINT`。  戻り値は、コマンドが処理されたことを示す `TRUE` 必要があります。  それ以外のルーティングは他のコマンド ターゲット オブジェクトに従います。  
  
 これらのフォームの例:  
  
-   内部 Resource.h \(通常は Visual C\+\+ で生成\)  
  
    ```  
    #define    ID_MYCMD      100  
    #define    ID_COMPLEX    101  
    ```  
  
-   クラス宣言の中  
  
    ```  
    afx_msg void OnMyCommand();  
    afx_msg void OnUpdateMyCommand(CCmdUI* pCmdUI);  
    afx_msg BOOL OnComplexCommand(UINT nID);  
    ```  
  
-   メッセージ マップ定義内  
  
    ```  
    ON_COMMAND(ID_MYCMD, OnMyCommand)  
    ON_UPDATE_COMMAND_UI(ID_MYCMD, OnUpdateMyCommand)  
    ON_COMMAND_EX(ID_MYCMD, OnComplexCommand)  
    ```  
  
-   実装ファイル  
  
    ```  
    void CMyClass::OnMyCommand()  
    {  
        // handle the command  
    }  
  
    void CMyClass::OnUpdateMyCommand(CCmdUI* pCmdUI)  
    {  
        // set the UI state with pCmdUI  
    }  
  
    BOOL CMyClass::OnComplexCommand(UINT nID)  
    {  
        // handle the command  
        return TRUE;  
    }  
    ```  
  
 上級ユーザーは一つのコマンド ハンドラーを使用して、コマンドの範囲を処理する: [ON\_COMMAND\_RANGE](../Topic/ON_COMMAND_RANGE.md) または `ON_COMMAND_RANGE_EX`。  これらのマクロの詳細については、製品のドキュメントを参照してください。  
  
> [!NOTE]
>  ClassWizard は `ON_COMMAND` と `ON_UPDATE_COMMAND_UI` ハンドラーの作成をサポートしていますが、`ON_COMMAND_EX` または `ON_COMMAND_RANGE` ハンドラーの作成をサポートしていません。  ただし、クラス ウィザードは、解析し、4 個のコマンド ハンドラーのバリアントをすべて表示することを許可します。  
  
## コントロール通知メッセージ  
 子コントロールからウィンドウに送信されるメッセージをメッセージ マップ エントリで情報の余分なビットがあります: コントロールの ID  メッセージ マップ エントリに指定されたメッセージ ハンドラーは、次の条件が true である場合のみ呼び出されます:  
  
-   コントロール通知コード \(`lParam`の上位ワード\) は、BN\_CLICKED など、メッセージ マップ エントリに指定された通知コードと一致します。  
  
-   コントロール ID \(`wParam`\) は、メッセージ マップのエントリで指定したコントロール ID と一致します。  
  
 カスタム コントロール通知メッセージがカスタム通知コードのメッセージ マップのエントリを定義するために [ON\_CONTROL](../Topic/ON_CONTROL.md) マクロを使用する場合があります。  このマクロにフォームがあります。  
  
```  
ON_CONTROL(wNotificationCode, id, memberFxn)  
```  
  
 同じハンドラーを持つコントロールの範囲のコントロールの特定の通知を処理するには、高度な用途向けに [ON\_CONTROL\_RANGE](../Topic/ON_CONTROL_RANGE.md) を使用できます。  
  
> [!NOTE]
>  ClassWizard はユーザー インターフェイスの `ON_CONTROL` または `ON_CONTROL_RANGE` ハンドラーの作成をサポートしていません。  手動でテキスト エディターで入力する必要があります。  ClassWizard はこれらのエントリを解析し、他のメッセージ マップ エントリと同様に、参照することができます。  
  
 Windows コモン コントロールは複雑なコントロール通知により強力な [WM\_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) を使用します。  MFC のこのバージョンに `ON_NOTIFY` と `ON_NOTIFY_RANGE` マクロを使用してこの新しいメッセージの直接サポートがあります。  これらのマクロの詳細については、製品のドキュメントを参照してください。  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)