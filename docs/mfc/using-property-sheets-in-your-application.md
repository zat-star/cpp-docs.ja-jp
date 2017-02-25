---
title: "アプリケーションでのプロパティ シートの使用 | Microsoft Docs"
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
  - "AddPage メソッド"
  - "CPropertyPage クラス, スタイル"
  - "Create メソッド [C++], プロパティ シート"
  - "ダイアログ リソース"
  - "ダイアログ テンプレート, プロパティ シート"
  - "DoModal メソッドのプロパティ シート"
  - "プロパティ ページ, プロパティ シート"
  - "プロパティ シート, プロパティ シートの概要"
ms.assetid: 240654d4-152b-4e3f-af7b-44234339206e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# アプリケーションでのプロパティ シートの使用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

アプリケーションのプロパティ シートを使用するには、次の手順を実行する:  
  
1.  各プロパティ ページのダイアログ テンプレート リソースを作成します。  ユーザーが 1 ページから別のページに切り替えるできるだけ一貫して配置します各ページであることに注意してください。  
  
     すべてのページのダイアログ テンプレートは同じサイズである必要はありません。  フレームワークは、プロパティ ページに対するプロパティ シートに割り当てる領域のサイズを決めるために最大ページ サイズを使用します。  
  
     プロパティ ページのダイアログ テンプレート リソースを作成するときに、プロパティ ダイアログ ボックスのプロパティ シートで次のスタイルを指定する必要があります:  
  
    -   このページのタブに表示するテキストに **全般** ページの **キャプション** のエディット ボックスを設定します。  
  
    -   **子**に **スタイル** ページの **IDataObject::GetData** のリスト ボックスを設定します。  
  
    -   **細枠**に **スタイル** ページの **Insert New Control** のリスト ボックスを設定します。  
  
    -   **スタイル** ページの **Titlebar** のチェック ボックスがオンになっていることを確認します。  
  
    -   **その他のスタイル** ページの **無効** のチェック ボックスがオンになっていることを確認します。  
  
2.  [CPropertyPage](../mfc/reference/cpropertypage-class.md)\-各プロパティ ページ ダイアログ テンプレートに対応する派生クラス\) を作成します。  [クラスの追加](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)を参照してください。  基本クラスとして `CPropertyPage` をクリックします。  
  
3.  このプロパティ ページの値を保持するメンバー変数を作成します。  プロパティ ページにメンバー変数を追加する方法は、メンバー変数をダイアログ ボックスに追加するとプロパティ ページを特化したダイアログ ボックスであるため、まったく同じです。  詳細については、「[ダイアログ ボックス コントロールのメンバー変数の定義](../mfc/defining-member-variables-for-dialog-controls.md)」を参照してください。  
  
4.  ソース・コードの [CPropertySheet](../mfc/reference/cpropertysheet-class.md) オブジェクトを構築します。  通常、プロパティ シートを表示するコマンドのハンドラーの `CPropertySheet` オブジェクトを構築します。  このオブジェクトは、プロパティ シートを表します。  [DoModal](../Topic/CPropertySheet::DoModal.md) 関数とモーダル プロパティ シートを作成する場合、フレームワークは、3 個のコマンド ボタンを既定で指定する: わかりました、取り消しは、適用します。  フレームワークは [作成](../Topic/CPropertySheet::Create.md) 関数で作成されたモードレス プロパティ シートのコマンド ボタンを作成します。  に追加し、そのほかのコントロール \(プレビュー ウィンドウなど\) またはモードレス プロパティ シートを表示するよう `CPropertySheet` からクラスを派生する必要はありません。  この手順は、プロパティ シートを閉じるために使用できる既定のコントロールがないため、モードレス プロパティ シートに必要です。  
  
5.  プロパティ シートに追加するページごとに次の手順を実行します。:  
  
    -   各 `CPropertyPage`の 1 種類のオブジェクト \(この手順で前に作成した派生クラスを作成します。  
  
    -   各ページの呼び出し [CPropertySheet::AddPage](../Topic/CPropertySheet::AddPage.md)。  
  
     通常、`CPropertySheet` を作成するオブジェクトは、この手順で `CPropertyPage` オブジェクトを作成します。  ただし、`CPropertySheet`\-派生クラス、`CPropertySheet` オブジェクトに格納 `CPropertyPage` オブジェクトを埋め込み、`CPropertySheet`の各ページの `AddPage` を呼び出す場合は、派生クラスのコンストラクターの実装すれば。  `AddPage` は プロパティ シートのページの一覧への `CPropertyPage` オブジェクトを追加しますが、実際にはそのページのウィンドウを作成しません。  したがって `AddPage`を呼び出すには、プロパティ シートのウィンドウの作成まで待つ必要はありません; プロパティ シートのコンストラクターから `AddPage` を呼び出すことができます。  
  
     プロパティ シートの単一行に合わせて、プロパティ シートに複数のタブがある場合既定では複数行に、タブを組み合わせて使用します。  スタックを無効にするには、**FALSE**にパラメーターがの [CPropertySheet::EnableStackedTabs](../Topic/CPropertySheet::EnableStackedTabs.md) を呼び出します。  プロパティ シートを作成するとき `EnableStackedTabs` を呼び出す必要があります。  
  
6.  プロパティ シートを表示するに [CPropertySheet::DoModal](../Topic/CPropertySheet::DoModal.md) または [作成](../Topic/CPropertySheet::Create.md) を呼び出します。  モーダル ダイアログ ボックスとしてプロパティ シートを作成するに `DoModal` を呼び出します。  モードレス ダイアログ ボックスとしてプロパティ シートを作成するに **作成** を呼び出します。  
  
7.  プロパティ シートのプロパティ ページと所有者間でデータを交換します。  これは技術情報 [データ交換](../mfc/exchanging-data.md)で説明します。  
  
 プロパティ シートを使用する方法の例については、MFC の一般的な [PROPDLG](../top/visual-cpp-samples.md)サンプルを参照してください。  
  
## 参照  
 [プロパティ シート](../mfc/property-sheets-mfc.md)