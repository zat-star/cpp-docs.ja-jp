---
title: "CDialog クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDialog クラス"
  - "MFC ダイアログ ボックス, 基本クラス"
  - "モーダル ダイアログ ボックス, 作成"
  - "モードレス ダイアログ ボックス, 作成"
  - "モードレス ダイアログ ボックス, 表示"
ms.assetid: ca64b77e-2cd2-47e3-8eff-c2645ad578f9
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDialog クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

画面のダイアログ ボックスを表示するために使用される基本クラスです。  
  
## 構文  
  
```  
class CDialog : public CWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CDialog::CDialog](../Topic/CDialog::CDialog.md)|`CDialog` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDialog::Create](../Topic/CDialog::Create.md)|`CDialog` オブジェクトを初期化します。  モードレス ダイアログ ボックスを作成し、`CDialog` のオブジェクトにアタッチします。|  
|[CDialog::CreateIndirect](../Topic/CDialog::CreateIndirect.md)|メモリ \(がベース\)、リソースのダイアログ ボックス テンプレートからモードレス ダイアログ ボックスを作成します。|  
|[CDialog::DoModal](../Topic/CDialog::DoModal.md)|されたときにモーダル ダイアログ ボックスを呼び出し、を返します。|  
|[CDialog::EndDialog](../Topic/CDialog::EndDialog.md)|モーダル ダイアログ ボックスを閉じます。|  
|[CDialog::GetDefID](../Topic/CDialog::GetDefID.md)|ダイアログ ボックスの既定のプッシュ ボタン コントロールの ID を取得します。|  
|[CDialog::GotoDlgCtrl](../Topic/CDialog::GotoDlgCtrl.md)|ダイアログ ボックスの指定したダイアログ ボックスのコントロールにフォーカスを移動します。|  
|[CDialog::InitModalIndirect](../Topic/CDialog::InitModalIndirect.md)|メモリ \(がベース\)、リソースのダイアログ ボックス テンプレートからモーダル ダイアログ ボックスを作成します。  パラメーターは関数 `DoModal` が呼び出されるまで格納されます。|  
|[CDialog::MapDialogRect](../Topic/CDialog::MapDialogRect.md)|四角形のダイアログ ボックス単位を単位を除外するに変換します。|  
|[CDialog::NextDlgCtrl](../Topic/CDialog::NextDlgCtrl.md)|ダイアログ ボックスの次のダイアログ ボックスのコントロールにフォーカスを移動します。|  
|[CDialog::OnInitDialog](../Topic/CDialog::OnInitDialog.md)|ダイアログ ボックスの初期化処理を拡張するためにオーバーライドします。|  
|[CDialog::OnSetFont](../Topic/CDialog::OnSetFont.md)|ダイアログ ボックス コントロールにテキストを描画するときに使用するのフォントを指定するためにオーバーライドします。|  
|[CDialog::PrevDlgCtrl](../Topic/CDialog::PrevDlgCtrl.md)|ダイアログ ボックスの前のダイアログ ボックスのコントロールにフォーカスを移動します。|  
|[CDialog::SetDefID](../Topic/CDialog::SetDefID.md)|指定したプッシュ ボタンにダイアログ ボックスの既定のプッシュ ボタン コントロールを変更します。|  
|[CDialog::SetHelpID](../Topic/CDialog::SetHelpID.md)|ダイアログ ボックスの状況依存のヘルプの ID を設定します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDialog::OnCancel](../Topic/CDialog::OnCancel.md)|\[キャンセル\]ボタンまたは Esc キー操作のためにオーバーライドします。  既定値は **DoModal** のダイアログ ボックスを **IDCANCEL**を閉じます。|  
|[CDialog::OnOK](../Topic/CDialog::OnOK.md)|モーダル ダイアログ ボックスの\[OK\]ボタンのアクションを実行します。  既定値は `DoModal` のダイアログ ボックスを **IDOK**を閉じます。|  
  
## 解説  
 ダイアログ ボックスは、2 種類です: モーダルおよびモードレス。  モーダル ダイアログ ボックスは、ユーザーによってアプリケーションが進む前に閉じる必要があります。  モードレス ダイアログ ボックスは、ユーザーがダイアログ ボックスを表示し、ダイアログ ボックスをキャンセルしたりせずに、別のタスクに戻ることができます。  
  
 `CDialog` のオブジェクトはダイアログ テンプレートと `CDialog`派生クラスの組み合わせです。  ダイアログ テンプレート リソースを作成し、に格納するためにダイアログ エディターを使用すると `CDialog`から派生したクラスを作成するには、クラス追加ウィザードを使用します。  
  
 ダイアログ ボックスは、他のウィンドウ、Windows からのメッセージを受信します。  ダイアログ ボックスで、ダイアログ ボックスのコントロールからの通知メッセージをユーザーが、ダイアログ ボックスにやり取りするのか、後処理する場合に特に必要があります。  選択するには、メッセージを処理したく、実際のクラスには、適切なメッセージ マップのエントリとメッセージ ハンドラー メンバー関数を追加するプロパティ ウィンドウを使用します。  だけハンドラー メンバー関数のアプリケーション固有のコードを記述する必要があります。  
  
 必要に応じて、メッセージ マップのエントリを常に記述して、メンバーは、手動で機能します。  
  
 ただし、すべて単純なダイアログ ボックスで、ユーザーがダイアログ ボックスのコントロールに入力されたストアのデータまたはユーザーのデータを表示するダイアログは、派生クラスにメンバー変数を追加します。  メンバー変数を作成し、コントロールに関連付けるために追加の変数のウィザードを使用できます。  同時に、各変数の値変数の型と許容範囲を選択します。  コード ウィザードは、ダイアログの派生クラスにメンバー変数を追加します。  
  
 マップ データが自動的にメンバー変数とダイアログ ボックスのコントロール間でのデータの交換を処理するために生成されます。  データ マップは適切な値を設定してダイアログ ボックスのコントロールを初期化し、データを取得し、データを検証する関数を提供します。  
  
 モーダル ダイアログ ボックスを作成するには、スタックのオブジェクトをダイアログ、派生クラスのコンストラクターを使用して構築し、次にダイアログのウィンドウとコントロールを作成するに `DoModal` を呼び出します。  モードレス ダイアログを作成する場合は、ダイアログ クラス コンストラクターの **\[作成\]** を呼び出します。  
  
 また [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]に説明されているように [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) のデータ構造を使用してメモリ テンプレートを作成できます。  `CDialog` のオブジェクトを構築すると、モードレス ダイアログ ボックス、または呼び出し [InitModalIndirect](../Topic/CDialog::InitModalIndirect.md) と [DoModal](../Topic/CDialog::DoModal.md) をモーダル ダイアログ ボックスを作成するために作成されるように [CreateIndirect](../Topic/CDialog::CreateIndirect.md) を呼び出します。  
  
 交換と検証のデータ マップで、新しいダイアログ クラスに追加 `CWnd::DoDataExchange` のオーバーライドで記述されます。  交換と検証機能の詳細については [DoDataExchange](../Topic/CWnd::DoDataExchange.md) のメンバーが `CWnd` で関数"を参照してください。  
  
 プログラマの場合、フレームワークは両方 [CWnd::UpdateData](../Topic/CWnd::UpdateData.md)の呼び出しによって `DoDataExchange` を間接的に呼び出します。  
  
 フレームワークは、モーダル ダイアログ ボックスを閉じるにユーザーが\[OK\]をクリックすると `UpdateData` を呼び出します。  \(データは\[キャンセル\]ボタンがクリックされた場合は取得されません\)。[OnInitDialog](../Topic/CDialog::OnInitDialog.md) の既定の実装は、コントロールの初期値を設定するに `UpdateData` を呼び出します。  通常、さらにコントロールを初期化するに `OnInitDialog` をオーバーライドします。  `OnInitDialog` は、すべてのダイアログ コントロールが作成された後、ダイアログ ボックスが表示される直前に呼び出されます。  
  
 モーダルまたはモードレス ダイアログ ボックスの実行中に `CWnd::UpdateData` をいつでも呼び出すことができます。  
  
 ダイアログ ボックスを手動で作成する場合には、必要なメンバー変数を独自派生ダイアログ ボックス クラスに追加して、これらの値を設定または取得するためにメンバー関数を追加します。  
  
 モーダル ダイアログ ボックスは、ユーザーが\[OK\]または\[キャンセル\]ボタンを押すか、コードで `EndDialog` のメンバー関数を呼び出すときに自動的に閉じます。  
  
 モードレス ダイアログ ボックスを実装すると、`OnCancel` のメンバー関数を常にオーバーライドし、その中の `DestroyWindow` を呼び出します。  ダイアログ ボックスを表示するが、を呼び出して、オブジェクトを破棄せず `EndDialog`をため、基本クラス `CDialog::OnCancel`を呼び出さないでください。  モードレス ダイアログ ボックスは、通常 **new**に割り当てられるため、**this**を削除するには、モードレス ダイアログ ボックスの `PostNcDestroy` をオーバーライドする必要があります。  モーダル ダイアログ ボックスは、普通、フレームで構築され、`PostNcDestroy` のクリーンアップは必要ではありません。  
  
 `CDialog`の詳細については、" "を参照してください:  
  
-   [ダイアログ ボックス](../../mfc/dialog-boxes.md)  
  
-   サポート技術情報の文書 Q262954: " HOWTO: スクロール バーを持つ Resizeable のダイアログ ボックスを作成します。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CDialog`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [MFC DLGCBR32 サンプル](../../top/visual-cpp-samples.md)   
 [MFC DLGTEMPL サンプル](../../top/visual-cpp-samples.md)   
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)