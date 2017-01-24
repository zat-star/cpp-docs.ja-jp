---
title: "チュートリアル: エージェント ベースのアプリケーションの作成 | Microsoft Docs"
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
  - "非同期エージェント、作成"
  - "agent クラス、例"
ms.assetid: 730f42ce-6d58-4753-b948-fd9c9ef2ce6c
caps.latest.revision: 24
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# チュートリアル: エージェント ベースのアプリケーションの作成
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ここでは、基本的なエージェント ベースのアプリケーションの作成方法について説明します。  このチュートリアルでは、テキスト ファイルから非同期的にデータを読み取るエージェントを作成できます。  このアプリケーションでは、Adler\-32 チェックサム アルゴリズムを使用して、そのファイルの内容のチェックサムを計算します。  
  
## 必須コンポーネント  
 このチュートリアルを完了するには、次のトピックを理解する必要があります。  
  
-   [非同期エージェント](../../parallel/concrt/asynchronous-agents.md)  
  
-   [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [メッセージ パッシング関数](../../parallel/concrt/message-passing-functions.md)  
  
-   [同期データ構造](../Topic/Synchronization%20Data%20Structures.md)  
  
##  <a name="top"></a> セクション  
 このチュートリアルでは、次のタスクを実行する方法を示します。  
  
-   [コンソール アプリケーションの作成](#createApplication)  
  
-   [file\_reader クラスの作成](#createAgentClass)  
  
-   [アプリケーションでの file\_reader クラスの使用](#useAgentClass)  
  
##  <a name="createApplication"></a> コンソール アプリケーションの作成  
 ここでは、プログラムで使用されるヘッダー ファイルを参照する Visual C\+\+ コンソール アプリケーションの作成方法について説明します。  
  
#### Win32 コンソール アプリケーション ウィザードを使用して Visual C\+\+ アプリケーションを作成するには  
  
1.  **\[ファイル\]** メニューの **\[新規作成\]** をクリックし、**\[プロジェクト\]** をクリックして **\[新しいプロジェクト\]** ダイアログ ボックスを表示します。  
  
2.  **\[新しいプロジェクト\]** ダイアログ ボックスで、**\[プロジェクトの種類\]** ペインの **\[Visual C\+\+\]** ノードをクリックし、**\[テンプレート\]** ペインの **\[Win32 コンソール アプリケーション\]** をクリックします。  プロジェクトの名前 \(`BasicAgent` など\) を入力し、**\[OK\]** をクリックして、**Win32 コンソール アプリケーション ウィザード**を表示します。  
  
3.  **\[Win32 コンソール アプリケーション ウィザード\]** ダイアログ ボックスで、**\[完了\]** をクリックします。  
  
4.  stdafx.h に、次のコードを追加します。  
  
     [!code-cpp[concrt-basic-agent#1](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_1.h)]  
  
     agents.h ヘッダー ファイルには、[concurrency::agent](../../parallel/concrt/reference/agent-class.md) クラスの機能が含まれています。  
  
5.  アプリケーションをビルドして実行することにより、アプリケーションが正常に作成されたことを確認します。  ソリューションをビルドするには、**\[ビルド\]** メニューの **\[ソリューションのビルド\]** をクリックします。  アプリケーションが正常にビルドされたら、**\[デバッグ\]** メニューの **\[デバッグ開始\]** をクリックして、アプリケーションを実行します。  
  
 \[[トップ](#top)\]  
  
##  <a name="createAgentClass"></a> file\_reader クラスの作成  
 ここでは、`file_reader` クラスの作成方法について説明します。  ランタイムは、各エージェントがそれぞれのコンテキストで処理を実行するようにスケジュールを設定します。  そのため、処理を同期的に実行する一方で、他のコンポーネントとは非同期的に通信するエージェントを作成できます。  `file_reader` クラスでは、指定された入力ファイルからデータを読み取り、そのファイルのデータを指定されたターゲット コンポーネントに送信します。  
  
#### file\_reader クラスを作成するには  
  
1.  新しい C\+\+ ヘッダー ファイルをプロジェクトに追加します。  これを行うには、**ソリューション エクスプローラー**で **\[ヘッダー ファイル\]** ノードを右クリックし、**\[追加\]** をクリックして、**\[新しい項目\]** をクリックします。  **\[テンプレート\]** ペインの **\[ヘッダー ファイル \(.h\)\]** をクリックします。  **\[新しい項目の追加\]** ダイアログ ボックスの **\[ファイル名\]** ボックスに「`file_reader.h`」と入力し、**\[追加\]** をクリックします。  
  
2.  file\_reader.h に、次のコードを追加します。  
  
     [!code-cpp[concrt-basic-agent#17](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_2.h)]  
  
3.  file\_reader.h に、`agent` から派生する `file_reader` という名前のクラスを作成します。  
  
     [!code-cpp[concrt-basic-agent#2](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_3.h)]  
  
4.  クラスの `private` セクションに次のデータ メンバーを追加します。  
  
     [!code-cpp[concrt-basic-agent#3](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_4.h)]  
  
     `_file_name` メンバーは、エージェントが読み取る対象のファイル名です。  `_target` メンバーは、エージェントがファイルの内容を書き込む [concurrency::ITarget](../../parallel/concrt/reference/itarget-class.md) オブジェクトです。  `_error` メンバーでは、エージェントの有効期間中に発生したエラーを保持します。  
  
5.  `file_reader` クラスの `public` セクションに `file_reader` コンストラクターの次のコードを追加します。  
  
     [!code-cpp[concrt-basic-agent#4](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_5.h)]  
  
     各コンストラクター オーバーロードによって、`file_reader` データ メンバーが設定されます。  2 番目と 3 番目のコンストラクター オーバーロードによって、アプリケーションでエージェントに対して特定のスケジューラを使用できるようにします。  最初のオーバーロードでは、エージェントに対して既定のスケジューラを使用します。  
  
6.  `file_reader` クラスのパブリック セクションに `get_error` メソッドを追加します。  
  
     [!code-cpp[concrt-basic-agent#5](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_6.h)]  
  
     `get_error` メソッドにより、エージェントの有効期間中に発生したエラーを取得します。  
  
7.  クラスの `protected` セクションで、[concurrency::agent::run](../Topic/agent::run%20Method.md) メソッドを実装します。  
  
     [!code-cpp[concrt-basic-agent#6](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_7.h)]  
  
     `run` メソッドによりファイルを開き、そこからデータを読み取ります。  `run` メソッドでは、例外処理を使用して、ファイルの処理中に発生したエラーをキャプチャします。  
  
     このメソッドでは、ファイルからデータを読み取るたびに [concurrency::asend](../Topic/asend%20Function.md) 関数を呼び出し、そのデータをターゲット バッファーに送信します。  処理の終了を示す際には、空の文字列をターゲット バッファーに送信します。  
  
 file\_reader.h の内容全体の例を次に示します。  
  
 [!code-cpp[concrt-basic-agent#7](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_8.h)]  
  
 \[[トップ](#top)\]  
  
##  <a name="useAgentClass"></a> アプリケーションでの file\_reader クラスの使用  
 ここでは、`file_reader` クラスを使用して、テキスト ファイルの内容を読み取る方法について説明します。  また、このファイル データを受け取り、その Adler\-32 チェックサムを計算する [concurrency::call](../../parallel/concrt/reference/call-class.md) オブジェクトの作成方法についても説明します。  
  
#### アプリケーションで file\_reader クラスを使用するには  
  
1.  BasicAgent.cpp に、次の `#include` ステートメントを追加します。  
  
     [!code-cpp[concrt-basic-agent#8](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_9.cpp)]  
  
2.  BasicAgent.cpp に、次の `using` ディレクティブを追加します。  
  
     [!code-cpp[concrt-basic-agent#9](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_10.cpp)]  
  
3.  `_tmain` 関数に、処理の終了を通知する [concurrency::event](../Topic/event%20Class.md) オブジェクトを作成します。  
  
     [!code-cpp[concrt-basic-agent#10](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_11.cpp)]  
  
4.  データを受け取ったときにチェックサムを更新する `call` オブジェクトを作成します。  
  
     [!code-cpp[concrt-basic-agent#11](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_12.cpp)]  
  
     また、この `call` オブジェクトは、処理の終了を通知する空の文字列を受け取ると、`event` オブジェクトを設定します。  
  
5.  test.txt ファイルから読み取り、そのファイルの内容を `call` オブジェクトに書き込む `file_reader` オブジェクトを作成します。  
  
     [!code-cpp[concrt-basic-agent#12](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_13.cpp)]  
  
6.  エージェントを開始し、エージェントが終了するまで待機します。  
  
     [!code-cpp[concrt-basic-agent#13](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_14.cpp)]  
  
7.  `call` オブジェクトがすべてのデータを受け取り、終了するまで待機します。  
  
     [!code-cpp[concrt-basic-agent#14](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_15.cpp)]  
  
8.  エラーが発生していないかどうかファイル リーダーを確認します。  エラーが発生していない場合は、最終的な Adler\-32 チェックサムを計算し、その結果をコンソールに出力します。  
  
     [!code-cpp[concrt-basic-agent#15](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_16.cpp)]  
  
 完全な BasicAgent.cpp ファイルの例を次に示します。  
  
 [!code-cpp[concrt-basic-agent#16](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_17.cpp)]  
  
 \[[トップ](#top)\]  
  
## 入力のサンプル  
 これは、入力ファイル text.txt の内容のサンプルです。  
  
  **The quick brown fox**  
**jumps**  
**over the lazy dog**   
## 出力例  
 入力のサンプルを使用すると、このプログラムでは、次の出力が生成されます。  
  
  **Adler\-32 sum is fefb0d75**   
## 信頼性の高いプログラミング  
 データ メンバーへの同時アクセスを回避するために、クラスの `protected` セクションまたは `private` セクションに、処理を実行するメソッドを追加することをお勧めします。  クラスの `public` セクションには、メッセージをエージェントに送信するメソッドまたはメッセージをエージェントから受信するメソッドのみを追加してください。  
  
 必ず、[concurrency::agent::done](../Topic/agent::done%20Method.md) メソッドを呼び出して、エージェントを完了の状態に移行してください。  通常、このメソッドは、`run` メソッドから制御が戻る前に呼び出します。  
  
## 次の手順  
 エージェント ベースのアプリケーションの別の例については、「[チュートリアル: join を使用したデッドロックの防止](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)」を参照してください。  
  
## 参照  
 [非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)   
 [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)   
 [メッセージ パッシング関数](../../parallel/concrt/message-passing-functions.md)   
 [同期データ構造](../Topic/Synchronization%20Data%20Structures.md)   
 [チュートリアル: join を使用したデッドロックの防止](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)