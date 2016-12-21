---
title: "マルチスレッド: ワーカー スレッドの生成 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "バックグラウンド タスク [C++]"
  - "マルチスレッド処理 [C++], ワーカー スレッド"
  - "スレッド処理 [C++], 作成 (スレッドを)"
  - "スレッド処理 [C++], ユーザー入力不要"
  - "スレッド処理 [C++], ワーカー スレッド"
  - "スレッド処理 [MFC], ワーカー スレッド"
  - "ワーカー スレッド [C++]"
ms.assetid: 670adbfe-041c-4450-a3ed-be14aab15234
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# マルチスレッド: ワーカー スレッドの生成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ワーカー スレッドでは、主にバックグラウンド タスクを処理します。アプリケーション処理の中で、ユーザーがその終了を待つ必要がない処理はバックグラウンド タスクにできます。  再計算やバックグラウンド印刷などはワーカー スレッドの良い例です。  このトピックでは、ワーカー スレッドの作成手順について詳しく説明します。  ここでは、次の内容について説明します。  
  
-   [スレッドの起動](#_core_starting_the_thread)  
  
-   [制御関数の実装](#_core_implementing_the_controlling_function)  
  
-   [例](#_core_controlling_function_example)  
  
 ワーカー スレッドの作成は比較的簡単な作業です。  スレッドを実行するために必要な手順は、\(1\) 制御関数の作成、\(2\) スレッドの起動の 2 つだけです。  [CWinThread](../mfc/reference/cwinthread-class.md) からクラスを派生する必要はありません。  `CWinThread` の専用の派生クラスが必要な場合は派生できますが、通常、単純なワーカー スレッドを実行する場合は必要ありません。  `CWinThread` をそのまま使用できます。  
  
##  <a name="_core_starting_the_thread"></a> スレッドの起動  
 `AfxBeginThread` には、2 つのオーバーロード バージョンがあります。1 つはワーカー スレッドのみを作成でき、もう 1 つは、ユーザー インターフェイス スレッドとワーカー スレッドの両方を作成できます。  1 つ目のオーバーロードを使用してワーカー スレッドの実行を開始するには、[AfxBeginThread](../Topic/AfxBeginThread.md) を呼び出して、次の情報を渡します。  
  
-   制御関数のアドレス。  
  
-   制御関数に渡すパラメーター。  
  
-   \(省略可\) スレッドの優先順位。  既定の優先順位は normal です。  優先順位の詳細については、[!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] の「[SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277)」を参照してください。  
  
-   \(省略可\) スレッドのスタック サイズ。  既定値は、このスレッドを生成するスレッドのスタックと同じサイズです。  
  
-   \(省略可\) スレッドを作成するときに一時停止状態にするには **CREATE\_SUSPENDED** を渡します。  既定値 0 では、スレッドを通常どおり起動します。  
  
-   \(省略可\) セキュリティ属性。  既定では親スレッドと同じ値になります。  このセキュリティ情報の形式の詳細については、[!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] の「[SECURITY\_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)」を参照してください。  
  
 `AfxBeginThread` 関数は、`CWinThread` オブジェクトを生成、初期化、および起動し、生成した CWinThread オブジェクトのアドレスを返します。このアドレスは後でプログラムから参照できます。  なんらかの原因でスレッド生成に失敗すると、スレッド生成処理全体をチェックし、すべてのオブジェクトを確実に解放します。  
  
##  <a name="_core_implementing_the_controlling_function"></a> 制御関数の実装  
 制御関数によってスレッドを定義します。  この関数に入ると、スレッドが起動され、この関数が終了すると、スレッドも終了します。  次に、この関数のプロトタイプを示します。  
  
```  
UINT MyControllingFunction( LPVOID pParam );  
```  
  
 パラメーターは単一の値です。  関数がこのパラメーターで受け取る値は、スレッド オブジェクトを生成したときにコンストラクターに渡した値です。  制御関数のデザインしだいで、この値の解釈が異なります。  スカラー値として解釈させることも、複数のパラメーターを含めた構造体へのポインターとして解釈させることもできます。また、値を無視することもできます。  パラメーターで構造体を参照すると、構造体を使って呼び出し元からスレッドに値を渡すだけでなく、スレッドから呼び出し元に値を渡すこともできます。  このようにスレッドから構造体を使って呼び出し元に値を渡すときは、スレッドから呼び出し元に対して戻り値の送出が整ったことを通知します。  このようなワーカー スレッドから呼び出し元への通信については、「[マルチスレッド : プログラミングのヒント](../parallel/multithreading-programming-tips.md)」を参照してください。  
  
 制御関数は終了時に、終了理由を示す **UINT** 型の値を返します。  通常は 0 が成功を、その他の値はエラーの種類を示します。  戻り値の仕様は純粋に実装に依存します。  たとえば、オブジェクトの使用数を管理するスレッドでは、現在の情報を返すことができます。  アプリケーションでこの値を取得する方法については、「[マルチスレッド : スレッドの終了](../parallel/multithreading-terminating-threads.md)」を参照してください。  
  
 MFC ライブラリで作成されたマルチスレッド プログラムで実行できることには、いくつかの制約があります。  これらの制約、およびスレッドの使用上のヒントについては、「[マルチスレッド : プログラミングのヒント](../parallel/multithreading-programming-tips.md)」を参照してください。  
  
##  <a name="_core_controlling_function_example"></a> 制御関数の例  
 制御関数を定義し、プログラムの別の部分からこの関数を使用する方法の例を次に示します。  
  
```  
UINT MyThreadProc( LPVOID pParam )  
{  
    CMyObject* pObject = (CMyObject*)pParam;  
  
    if (pObject == NULL ||  
        !pObject->IsKindOf(RUNTIME_CLASS(CMyObject)))  
    return 1;   // if pObject is not valid  
  
    // do something with 'pObject'  
  
    return 0;   // thread completed successfully  
}  
  
// inside a different function in the program  
.  
.  
.  
pNewObject = new CMyObject;  
AfxBeginThread(MyThreadProc, pNewObject);  
.  
.  
.  
```  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [マルチスレッド : ユーザー インターフェイス スレッドの生成](../parallel/multithreading-creating-user-interface-threads.md)  
  
## 参照  
 [C\+\+ と MFC を使用するマルチスレッド](../parallel/multithreading-with-cpp-and-mfc.md)