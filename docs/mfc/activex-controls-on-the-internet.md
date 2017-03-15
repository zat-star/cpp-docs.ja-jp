---
title: "インターネット上の ActiveX コントロール | Microsoft Docs"
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
  - "ActiveX コントロール [C++], 作成"
  - "ActiveX コントロール [C++], インターネット"
  - "ダウンロード (ActiveX コントロールでデータを)"
  - "インターネット アプリケーション [C++], ActiveX コントロール"
  - "ネットワーク [C++], ダウンロード (ActiveX コントロールで)"
  - "OLE コントロール [C++], アップグレード (ActiveX に)"
ms.assetid: 7ab943c8-2022-41df-9065-d629b616eeec
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# インターネット上の ActiveX コントロール
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ActiveX コントロールは、OLE コントロール固有の更新バージョンです。  コントロールは、さまざまなコンテナーで使用できるインターネットの COM 対応の Web ブラウザーを含むプログラミング可能なソフトウェア コンポーネントを開発するための主要なアーキテクチャです。  すべての ActiveX コントロールは、インターネットのコントロールで、アクティブ ドキュメントに機能を追加するか、Web ページに含めることができます。  Web ページのコントロールはスクリプトを使用して互いに通信できます。  
  
 ActiveX コントロールは、インターネットに限定されません。  ActiveX コントロールは、任意のコンテナーでコントロールがそのコンテナーに必要なインターフェイスをサポートする場合に使用できます。  
  
 **ActiveX コントロールは、次のような利点があります。:**  
  
-   前の OLE コントロールよりも少ない要求インターフェイス。  
  
-   ウィンドウなしである機能と常に埋め込み先編集。  
  
 **ActiveX コントロールのために、コントロールは次のようにする必要があります:**  
  
-   **IUnknown** インターフェイスをサポートします。  
  
-   COM オブジェクトになります。  
  
-   エクスポート **DLLRegisterServer** と **DLLUnRegisterServer**。  
  
-   機能に必要な追加サポート インターフェイス。  
  
## 既存のコントロールをインターネットに合うようにします。  
 インターネットの環境で適切に動作するコントロールをデザインすると、インターネットの比較的小さい伝送速度に事項を考慮する必要があります。  既存のコントロールを使用して; ただし、コード サイズが小さくなり、コントロール プロパティを非同期にダウンロードするユーザーが行う必要のある手順があります。  
  
 コントロールのパフォーマンスを向上させるために、効率の考慮事項のヒントに従います。:  
  
-   記事 [ActiveX コントロール: 最適化](../mfc/mfc-activex-controls-optimization.md)"で説明されている手法を実装してください。  
  
-   コントロールがどのようにインスタンス化されるかを検討します。  
  
-   非同期です。; 他のプログラムを妨げることなく。  
  
-   小さなブロック データをダウンロードします。  
  
     ビットマップやビデオ データなどの大きなストリームをダウンロードした場合、コンテナーと連携して制御データを非同期にアクセスします。  データの取得になる可能性のある他のコントロールを協調的に使用するインクリメンタルまたは推移的な方法でデータを取得してください。  コードは、非同期にダウンロードできます。  
  
-   背景のダウンロードのコードとプロパティ。  
  
-   できるだけ迅速になったユーザー インターフェイスのアクティブ。  
  
-   永続データを、プロパティと大きなデータ Blob どのように格納されるか検討 \(ビットマップ イメージなど\) またはビデオ データの両方\)。  
  
     大量の永続データのコントロールは、大きいビットマップまたは AVI ファイルなどのメソッドのダウンロードに細心の注意が必要です。  コントロールの背景のデータを取得するとき、ドキュメントまたはページをできるだけ早く表示されると、ユーザーがページと対話できるようにします。  
  
-   コードのサイズと実行時を修正するための効率的なルーチンを記述します。  
  
     永続データのバイトしかの小さなボタンとラベル コントロールは、インターネットの環境で使用する手段としては、ブラウザー内で正しく動作します。  
  
-   検討の進行がコンテナーに伝えられます。  
  
     ユーザーがいつページとやり取りすることができるため、どのダウンロードが完了したか含む非同期ダウンロードの進行状況のコンテナーを通知します。  コンテナーは、進行状況 \(完了したパーセントなど\) を表示できます。  
  
-   コントロールがクライアント コンピューターに登録方法を検討します。  
  
## 新しい ActiveX コントロールの作成  
 新しいコントロールをアプリケーション ウィザードを使用すると、非同期モニカー、他の最適化のサポートを有効にすることもできます。  ダウンロード コントロール プロパティのサポートを非同期的に追加するには、次の手順を実行します。:  
  
#### プロジェクトが MFC ActiveX コントロール ウィザードを使用して作成します。  
  
1.  **ファイル** メニューをクリック `New`。  
  
2.  **MFC ActiveX コントロール ウィザード** を Visual C\+\+ のプロジェクトから選択し、プロジェクトに名前を付けます。  
  
3.  **コントロールの設定** ページで、**非同期でプロパティを読み込む\(L\)**を選択します。  このオプションを選択するための準備完了状態プロパティと準備完了 state changed イベントを設定します。  
  
     [ActiveX コントロール: 最適化](../mfc/mfc-activex-controls-optimization.md)で説明されている他の最適化を、**ウィンドウなしでアクティブ\(S\)**などの選択できます。  
  
4.  プロジェクトを作成するに **完了** をクリックします。  
  
#### CDataPathProperty から派生したクラスを作成するには  
  
1.  `CDataPathProperty`から派生するクラスを作成します。  
  
2.  コントロールのヘッダー ファイルを含むソース・コード ファイルごとに、その前にこのクラスのヘッダー ファイルを追加します。  
  
3.  このクラスでは、`OnDataAvailable`をオーバーライドします。  この関数は、データの表示に使用するたびに呼び出されます。  データが使用可能になると、段階的に実行することにより、選択した方法、たとえば処理。  
  
     コード例の抜粋を次に段階的にエディット コントロールのデータを表示する簡単な例です。  エディット コントロールを消去 **BSCF\_FIRSTDATANOTIFICATION** フラグの使用に注意してください。  
  
     [!code-cpp[NVC_MFCActiveXControl#1](../mfc/codesnippet/CPP/activex-controls-on-the-internet_1.cpp)]  
  
     `CListCtrl` クラスを使用するに AFXCMN.H を含める必要があることに注意してください。  
  
4.  コントロールの全体的な状態の変更 \(たとえば、対話型読み込みから初期化されるへのユーザー\)、呼び出し `COleControl::InternalSetReadyState`とき。  コントロールが 1 データ パスのプロパティがある場合は、ダウンロードが完了したことをコンテナーに通知するために **BSCF\_LASTDATANOTIFICATION** のコードを追加します。  たとえば、次のようになります。  
  
     [!code-cpp[NVC_MFCActiveXControl#2](../mfc/codesnippet/CPP/activex-controls-on-the-internet_2.cpp)]  
  
5.  `OnProgress` をオーバーライドします。  `OnProgress`で、どの程度現在のダウンロードに沿っているかを示すことが最大範囲と数を示す数に渡されます。  ユーザーに完了したパーセントなどの状態を表示するには、これらの値を使用できます。  
  
 次の手順では、コントロールにクラスを使用するには、派生しましたプロパティを追加します。  
  
#### プロパティを追加するには  
  
1.  **\[クラス ビュー\]** でライブラリ ノードの下のインターフェイスを右クリックし、**追加**、**\[プロパティの追加\]** を選択します。  これは **プロパティ 追加ウィザード**を開始します。  
  
2.  **プロパティ 追加ウィザード**で、**Set\/Get Methods** のオプション ボタンをクリックし、**プロパティ名** \(たとえば、EditControlText を入力し、**プロパティの型**として BSTR を選択します。  
  
3.  \[完了\] をクリックします。  
  
4.  `CDataPathProperty`のメンバー変数\- ActiveX コントロール クラスの派生クラスを宣言します。  
  
     [!code-cpp[NVC_MFCActiveXControl#3](../mfc/codesnippet/CPP/activex-controls-on-the-internet_3.h)]  
  
5.  **Get\/Set** のメソッドを実装してください。  **取得**では、文字列を返します。  `Set`では、プロパティを読み込み、`SetModifiedFlag`を呼び出します。  
  
     [!code-cpp[NVC_MFCActiveXControl#4](../mfc/codesnippet/CPP/activex-controls-on-the-internet_4.cpp)]  
  
6.  [DoPropExchange](../Topic/COleControl::DoPropExchange.md)で次の行を追加する:  
  
     [!code-cpp[NVC_MFCActiveXControl#5](../mfc/codesnippet/CPP/activex-controls-on-the-internet_5.cpp)]  
  
7.  この行を追加して、コントロールをリセットするには、オーバーライド [ResetData](../Topic/CDataPathProperty::ResetData.md) :プロパティ  
  
     [!code-cpp[NVC_MFCActiveXControl#6](../mfc/codesnippet/CPP/activex-controls-on-the-internet_6.cpp)]  
  
## 判断する CDataPathProperty または CCachedDataPathProperty から派生するかどうか  
 前の例では `CDataPathProperty`コントロールからのプロパティを派生するための手順について説明します。  これは、すべてのデータを維持する必要がないかをに頻繁に変更される、現在の値のみリアルタイム データをダウンロードすると便利です。  例では、株式情報のコントロールです。  
  
 また `CCachedDataPathProperty`から派生します。  この場合、ダウンロードされたデータは、ファイルにキャッシュされます。  これは、たとえば、徐々ににビットマップをコントロールするすべてのダウンロードしたデータを保持する必要がある場合に重要です。  この場合、クラスにデータを含むメンバー変数があります:  
  
 `CMemFile m_Cache;`  
  
 ActiveX コントロール クラスでは、`OnDraw` にデータを表示するには、このメモリ マップト ファイルを使用できます。  ActiveX コントロール `CCachedDataPathProperty`\-派生クラスでは、メンバー関数 `OnDataAvailable` をオーバーライドして、基本クラスの実装を呼び出した後にコントロールを無効にします。  
  
 [!code-cpp[NVC_MFCActiveXControl#7](../mfc/codesnippet/CPP/activex-controls-on-the-internet_7.cpp)]  
  
## ActiveX コントロールを使用して非同期的にダウンロード データ  
 ネットワーク経由でデータを非同期にダウンロードする必要があります。  その利点は大量のデータを転送するか、または接続が低速で実行される場合は、ダウンロードされないクライアント プロセスの他のプロセスがあります。  
  
 非同期モニカーは、ネットワーク上のデータを非同期にダウンロードする手段を提供します。  非同期モニカーの読み取り操作は、操作が完了したことがなくても、すぐに制御を返します。  
  
 たとえば、10 バイトのみ使用でき、読み取り、1K ファイルでブロックが返されますが、現在使用できる 10 バイトが非同期に呼び出されます。  
  
 `CAsyncMonikerFile` クラスを使用して [非同期モニカー](../mfc/asynchronous-monikers-on-the-internet.md) を実装します。  ただし、ActiveX コントロールは非同期コントロール プロパティの実装を支援するために `CAsyncMonikerFile`から派生される `CDataPathProperty` クラスを使用できます。  
  
 ASYNDOWN サンプルはデータを読み取るためにタイマーを使用して非同期ループを設定する方法を示します。  ASYNDOWN は、サポート技術情報の文書「HOWTO:で詳しく説明します。AsyncDown データは非同期ダウンロード」 \(Q177244\) と、Microsoft ダウンロード センターからダウンロードできます。\(Microsoft サポート技術情報のオンライン サービスからマイクロソフト サポート オンライン ファイル」 \(Q119591\) をダウンロードする方法についての詳細については Microsoft ダウンロード センターから、参照します記事「ファイル。\) サポート技術情報の文書は、MSDN ライブラリ CD\-ROM または [http:\/\/support.microsoft.com\/support](http://support.microsoft.com/support) で参照できます。  
  
 ASYNDOWN で使用する基本的な方法は、データが使用可能なことを示すために、**CDataPathProperty::OnDataAvailable** タイマーを設定します。  タイマー メッセージを受け取ると、アプリケーションは、データを 128 バイトのブロックを読取り、エディット コントロールを塗りつぶします。  タイマー メッセージが処理されるときにデータを使用できない場合、タイマーが消えます。  `OnDataAvailable` は より多くのデータが遅れてはタイマーを発生させます。  
  
## Web ページ上のコントロールの表示  
 Web ページにコントロールを挿入するオブジェクト タグと属性の例を次に示します。  
  
 `<OBJECT`  
  
 `CLASSID="clsid:FC25B780-75BE-11CF-8B01-444553540000"`  
  
 `CODEBASE="/ie/download/activex/iechart.ocx"`  
  
 `ID=chart1`  
  
 `WIDTH=400`  
  
 `HEIGHT=200`  
  
 `ALIGN=center`  
  
 `HSPACE=0`  
  
 `VSPACE=0`  
  
 `>`  
  
 `<PARAM NAME="BackColor" value="#ffffff">`  
  
 `<PARAM NAME="ForeColor" value="#0000ff">`  
  
 `<PARAM NAME="url" VALUE="/ie/controls/chart/mychart.txt">`  
  
 `</OBJECT>`  
  
## 既存の ActiveX コントロールの新しい ActiveX コントロール機能を使用するために更新  
 OLE コントロールが 4.2 より前のバージョンの Visual C\+\+ を使用して作成された場合、パフォーマンスが向上し、機能を強化するために実行できる手順がいくつかあります。  これらの詳細な説明については [ActiveX コントロール: 最適化](../mfc/mfc-activex-controls-optimization.md)変更、参照します。  
  
 既存のコントロールに非同期サポート プロパティを追加する場合は、独自の準備完了状態プロパティおよび `ReadyStateChange` イベントを追加する必要があります。  コントロールのコンストラクターで、追加する:  
  
 [!code-cpp[NVC_MFCActiveXControl#8](../mfc/codesnippet/CPP/activex-controls-on-the-internet_8.cpp)]  
  
 コードが [COleControl::InternalSetReadyState](../Topic/COleControl::InternalSetReadyState.md)を呼び出して、ダウンロードできるように準備状態を更新します。  ユーザーが `InternalSetReadyState` を呼び出すことができる 1 種類の場所は `CDataPathProperty`の `OnProgress` のオーバーライド\-派生クラスからです。  
  
 次に、[新しい ActiveX コントロールの作成](#_core_how_do_i_create_a_new_activex_control.3f)の手順に従います。  
  
## 参照  
 [MFC インターネット プログラミングの作業](../mfc/mfc-internet-programming-tasks.md)   
 [MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)