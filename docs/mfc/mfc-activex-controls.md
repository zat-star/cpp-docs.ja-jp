---
title: "MFC ActiveX コントロール | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MFC ActiveX Controls (MFC)"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX コントロール [C++], MFC"
  - "COleControl クラス, MFC ActiveX コントロール"
  - "コンテナー [C++], MFC ActiveX コントロール"
  - "ディスパッチ マップ, MFC ActiveX コントロールの"
  - "イベント [C++], ActiveX コントロール"
  - "MFC ActiveX コントロール [C++]"
  - "MFC ActiveX コントロール [C++], アクティブ/非アクティブの状態"
  - "MFC ActiveX コントロール [C++], コンテナー"
  - "MFC ActiveX コントロール [C++], シリアル化"
  - "シリアル化 [C++], MFC ActiveX コントロール"
ms.assetid: c911fb74-3afc-4bf3-a0f5-7922b14d9a1b
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# MFC ActiveX コントロール
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ActiveX コントロールは、コンポーネント オブジェクト モデル \(COM: Component Object Model\) に基づく再利用可能なソフトウェア コンポーネントです。多岐にわたる OLE の機能をサポートしており、さまざまなソフトウェアの要件に合わせてカスタマイズできます。  ActiveX コントロールは、通常の ActiveX コントロール コンテナー内と、インターネット上の WWW \(World Wide Web\) ページの両方で使用できるように設計されています。  ここで説明する MFC または [Active Template Library \(ATL\)](../atl/active-template-library-atl-concepts.md) のどちらかを使用して、ActiveX コントロールを作成できます。  
  
 ActiveX コントロールは、独自のウィンドウに自らを描画し、\(マウス クリックなどの\) イベントに応答し、オートメーション オブジェクトに含まれているのと同様のプロパティおよびメソッドを含むインターフェイスを通じて管理することができます。  
  
 これらのコントロールは、データベース アクセス、データの監視、またはグラフの作成など、多くの用途で開発できます。  移植性以外にも、既存の OLE コンテナーとの互換性、OLE コンテナーのメニューと自らのメニューの統合など、以前の ActiveX コントロールでは使用できなかった機能が、現在の ActiveX コントロールではサポートされています。  また、ActiveX コントロールはオートメーションを完全にサポートしており、その結果、コントロールは読み取り\/書き込みのプロパティや一連のメソッドを公開し、コントロール ユーザーがそれらを呼び出すことができます。  
  
 ウィンドウなしの ActiveX コントロールや、アクティブになったときのみウィンドウを作成する ActiveX コントロールを作成することもできます。  ウィンドウなしのコントロールを使用すると、アプリケーションの表示が高速化され、透明なコントロールや長方形以外のコントロールを作り出すこともできます。  また、ActiveX コントロールのプロパティを非同期で読み込むこともできます。  
  
 ActiveX コントロールは、インプロセス サーバー \(通常は小さなオブジェクト\) として実装され、任意の OLE コンテナー内で使用することができます。  ActiveX コントロールに対応するように設計された OLE コンテナー内で ActiveX コントロールを使用する場合のみ、ActiveX コントロールのすべての機能を利用できることに注意してください。  ActiveX コントロールをサポートするコンテナーの一覧については、["Port ActiveX Controls to Other Applications \(他のアプリケーションへの ActiveX コントロールの移植\)"](../Topic/Containers%20for%20ActiveX%20Controls.md) を参照してください。  これ以後はこのコンテナーの種類を "コントロール コンテナー" と呼びますが、これらのコンテナーはコントロールのプロパティとメソッドを使用して ActiveX コントロールを操作し、イベントの形式で ActiveX コントロールからの通知を受け取ることができます。  次の図に、この双方向のやり取りを示します。  
  
 ![ActiveX コントロール コンテナーとコントロールの相互作用](../mfc/media/vc37221.gif "vc37221")  
ActiveX コントロール コンテナーとウィンドウを持つ ActiveX コントロールとの対話  
  
 ActiveX コントロールの最適化に関する最新の情報については、["MFC ActiveX Controls: Optimization \(MFC ActiveX コントロール: 最適化\)"](../mfc/mfc-activex-controls-optimization.md) を参照してください。  
  
 MFC ActiveX コントロールを作成するには、["Create an ActiveX control project \(ActiveX コントロール プロジェクトの作成\)"](../mfc/reference/mfc-activex-control-wizard.md) を参照してください。  
  
 詳細については、次のトピックを参照してください。  
  
-   [ActiveX コントロール コンテナー](../mfc/activex-control-containers.md)  
  
-   [Active ドキュメント](../Topic/Active%20Documents.md)  
  
-   [ActiveX コントロールを使用する](../Topic/Using%20ActiveX%20Controls.md)  
  
-   [\<caps:sentence id\="tgt23" sentenceid\="e07c7a1ebdac21120a91f75018670c81" class\="tgtSentence"\>ActiveX コントロールについて\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms693753)  
  
-   [既存の ActiveX コントロールをインターネットで使用するためのアップグレード](../Topic/Upgrading%20an%20Existing%20ActiveX%20Control.md)  
  
##  <a name="_core_basic_components_of_an_activex_control"></a> ActiveX コントロールの基本コンポーネント  
 ActiveX コントロールは複数のプログラム要素を使用して、コントロール コンテナーやユーザーとの双方向のやり取りを効率的に実行します。  これらの要素は、[COleControl](../mfc/reference/colecontrol-class.md) クラス、つまり一連のイベント発生関数と 1 つのディスパッチ マップです。  
  
 独自に開発するすべての ActiveX コントロール オブジェクトは、MFC 基底クラス `COleControl` から強力な機能セットを継承します。  これらの機能には、埋め込み先でのアクティブ化機能と、オートメーション ロジックが含まれています。  `COleControl` はコントロール オブジェクトに対して、MFC ウィンドウ オブジェクトと同じ機能、およびイベント発生機能を提供できます。  `COleControl` は、[ウィンドウなしのコントロール](../mfc/providing-windowless-activation.md)に対しても、ウィンドウ機能 \(マウスのキャプチャ、キーボード フォーカス、スクロール\) を提供します。これらのコントロールは通常、ウィンドウ機能を果たすために自らのコンテナーに依存していますが、その方法に比べて表示が非常に高速になります。  
  
 コントロール クラスは `COleControl` から派生するため、特定の条件が満たされている場合は、コントロール コンテナーに対して、イベントとも呼ばれるメッセージを送信、つまり "発生させる" 機能を継承します。  これらのイベントは、コントロール内で重要な動作が発生したときにそのことをコントロール コンテナーに通知するために使用されます。  イベントにパラメーターをアタッチして、イベントに関する追加情報をコントロール コンテナーに送信することもできます。  ActiveX コントロール イベントの詳細については、["MFC ActiveX Controls: Events \(MFC ActiveX コントロール: イベント\)"](../mfc/mfc-activex-controls-events.md) を参照してください。  
  
 最後の要素はコントロール ユーザーに対して一連の関数 \(メソッド\) と属性 \(プロパティ\) を公開するために使用されるディスパッチ マップです。  プロパティを使用すると、コントロール コンテナーまたはコントロール ユーザーがさまざまな方法でコントロールを操作できます。  ユーザーはコントロールの外観の変更、コントロールの特定の値の変更、コントロールが維持する特定のデータへのアクセスなど、コントロールに対する要求を実行することもできます。  このインターフェイスは、コントロール開発者によって決定され、**\[クラス ビュー\]** を使用して定義されます。  ActiveX コントロールのメソッドとプロパティの詳細については、["MFC ActiveX Controls: Methods \(MFC ActiveX コントロール: メソッド\)"](../mfc/mfc-activex-controls-methods.md) と ["Properties \(プロパティ\)"](../mfc/mfc-activex-controls-properties.md) を参照してください。  
  
##  <a name="_core_interaction_between_controls_with_windows_and_activex_control_containers"></a> ウィンドウを持つコントロールと、ActiveX コントロール コンテナー間での双方向のやり取り  
 コントロール コンテナー内でコントロールを使用すると、コントロールは 2 つのメカニズムを使用して通信を行います。つまり、プロパティとメソッドを公開し、イベントを発生させます。  次の図に、これら 2 つのメカニズムを実装する方法を示します。  
  
 ![ActiveX コントロールがコンテナーと通信する](../Image/vc37222.gif "vc37222")  
ActiveX コントロール コンテナーと ActiveX コントロールとの通信  
  
 前の図では、コントロールが他の OLE インターフェイスを \(オートメーションとイベント以外の方法で\) 処理する方法も示します。  
  
 コントロールとコンテナーとのすべての通信は、`COleControl` によって実行されます。  コンテナーの一部の要求を処理するために、**COleControl**  は、コントロール クラス内で実装されるメンバー関数を呼び出します。  すべてのメソッドと一部のプロパティは、この方法で処理されます。  開発するコントロールが属するクラスは、`COleControl` のメンバー関数を呼び出して、コンテナーとの通信を開始することもできます。  イベントは次の方法で発生します。  
  
##  <a name="_core_active_and_inactive_states_of_an_activex_control"></a> ActiveX コントロールのアクティブ状態と非アクティブ状態  
 各コントロールには、アクティブおよび非アクティブという 2 つの基本的な状態があります。  従来、これらの状態は、コントロールがウィンドウを持つかどうかという形で判別されていました。  アクティブなコントロールはウィンドウを持ち、非アクティブなコントロールはウィンドウを持たないという分類でした。  ウィンドウなしのアクティブ状態が導入された結果、この区別はもう普遍的ではありませんが、今でも多くのコントロールに適用されます。  
  
 [ウィンドウなしのコントロール](../mfc/providing-windowless-activation.md)がアクティブになると、そのコントロールは自らのコンテナーからマウスのキャプチャ、キーボード フォーカス、スクロールおよび他のウィンドウ サービスを呼び出します。  [非アクティブなコントロールでマウスによる双方向のやり取りを実現する](../Topic/Providing%20Mouse%20Interaction%20While%20Inactive.md)ことや、[待機しておき、アクティブになったときにウィンドウを作成する](../mfc/turning-off-the-activate-when-visible-option.md)コントロールを作成することもできます。  
  
 ウィンドウを持つコントロールがアクティブになると、コントロール コンテナー、ユーザー、および Windows との双方向のやり取りができます。  下の図では、ActiveX コントロール、コントロール コンテナー、およびオペレーティング システムの間の通信パスを示します。  
  
 ![アクティブなウィンドウ付きの ActiveX コントロールの Msg 処理](../mfc/media/vc37223.gif "vc37223")  
ウィンドウを持つ ActiveX コントロールがアクティブになったときの Windows メッセージの処理  
  
##  <a name="_core_serializing_activex_elements"></a> シリアル化  
 永続化とも呼ばれるデータのシリアル化機能により、コントロールは自らのプロパティの値を永続ストレージに書き込むことができます。  その後、ストレージからオブジェクトの状態を読み取ることで、コントロールを再作成できます。  
  
 コントロールは、ストレージ メディアにアクセスする役割を果たさないことに注意してください。  代わりに、適切なときに使用できるように、コントロール コンテナーがストレージ メディアをコントロールに提供する役割を果たします。  シリアル化の詳細については、["MFC ActiveX Controls: Serializing \(MFC ActiveX コントロール: シリアル化\)"](../mfc/mfc-activex-controls-serializing.md) を参照してください。  シリアル化の最適化については、"ActiveX Controls: Optimization \(ActiveX コントロール: 最適化\)" の ["Optimizing Persistence and Initialization \(永続化および初期化の最適化\)"](../mfc/optimizing-persistence-and-initialization.md) を参照してください。  
  
##  <a name="_core_installing_activex_control_classes_and_tools"></a> ActiveX コントロール クラスとツールのインストール  
 Visual C\+\+ をインストールするときに、セットアップで ActiveX コントロールを選択した \(既定で選択されます\) 場合は、MFC ActiveX コントロール クラス、およびリテール バージョンとデバッグ バージョンの ActiveX コントロール ランタイム DLL が自動的にインストールされます。  
  
 既定では、ActiveX コントロール クラスとツールは、\\Program Files\\Microsoft Visual Studio .NET の下にある次のサブディレクトリにインストールされます。  
  
-   **\\Common7\\Tools**  
  
     テスト コンテナー ファイル \(TstCon32.exe、およびそのヘルプ ファイル\) を格納します。  
  
-   **\\Vc7\\atlmfc\\include**  
  
     MFC を使用して ActiveX コントロールを開発するために必要なインクルード ファイルを格納します。  
  
-   **\\Vc7\\atlmfc\\src\\mfc**  
  
     MFC 内の特定の ActiveX コントロール クラスに対応するソース コードを格納します。  
  
-   **\\Vc7\\atlmfc\\lib**  
  
     MFC を使用して ActiveX コントロールを開発するために必要なライブラリを格納します。  
  
 また、MFC ActiveX コントロール用のサンプルもあります。  これらの例の詳細については、["Controls Samples: MFC\-Based ActiveX Controls \(コントロールのサンプル: MFC ベースの ActiveX コントロール\)"](../top/visual-cpp-samples.md) を参照してください。  
  
## 参照  
 [ユーザー インターフェイス要素](../mfc/user-interface-elements-mfc.md)