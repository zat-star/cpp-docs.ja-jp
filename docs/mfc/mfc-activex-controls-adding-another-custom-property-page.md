---
title: "MFC ActiveX コントロール : カスタム プロパティ ページの追加 | Microsoft Docs"
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
  - "ActiveX コントロール [C++], プロパティ ページ"
  - "カスタム プロパティ ページ"
  - "MFC ActiveX コントロール [C++], プロパティ ページ"
  - "プロパティ ページ [C++], MFC ActiveX コントロール"
ms.assetid: fcf7e119-9f29-41a9-908d-e9b1607e08af
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# MFC ActiveX コントロール : カスタム プロパティ ページの追加
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

と同様に、1 種類のプロパティ ページに適合するより、ActiveX コントロールのプロパティがあります。  この場合は、ActiveX コントロールにこれらのプロパティを表示するプロパティ ページを追加できます。  
  
 ここでは、少なくとも 1 つがプロパティ ページを持つ ActiveX コントロールに新しいプロパティ ページを追加する方法について説明します。  ストック プロパティ ページ \(フォント、画像、色\) の追加の詳細については、記事 [MFC ActiveX コントロール: ストック プロパティ ページを使用します。](../mfc/mfc-activex-controls-using-stock-property-pages.md)を参照します。  
  
 次の手順では、ActiveX コントロール ウィザードが作成したサンプル ActiveX コントロール フレームワークを使用します。  したがって、クラス名と識別子はこの例で一意です。  
  
 ActiveX コントロールのプロパティ ページを使用する詳細については、次のトピックを参照します:  
  
-   [MFC ActiveX コントロール: プロパティ ページ](../mfc/mfc-activex-controls-property-pages.md)  
  
-   [MFC ActiveX コントロール: ストック プロパティ ページを使用します。](../mfc/mfc-activex-controls-using-stock-property-pages.md)  
  
    > [!NOTE]
    >  新しいプロパティ ページが ActiveX コントロールのプロパティ ページのサイズの標準に準拠することを強くお勧めします。  標準的なピクチャおよびカラー プロパティ ページは 250x62 ダイアログ単位 \(DLU\) を測定します。  標準フォント プロパティ ページは 250x110 DLU です。  ActiveX コントロール ウィザードで作成する既定のプロパティ ページは 250x62 DLU Standard を使用します。  
  
### 新しいプロパティ ページ テンプレートをプロジェクトに追加するには  
  
1.  開くコントロール プロジェクトを開き、プロジェクト ワークスペースの開いているリソース ビュー。  
  
2.  ショートカット メニューを開き、**\[リソースの追加\]** をクリックしますにリソース ビューを右クリックします。  
  
3.  **ダイアログ** ノードを展開し、**IDD\_OLE\_PROPPAGE\_SMALL**を選択します。  
  
4.  プロジェクトにリソースを追加するに `New` をクリックします。  
  
5.  プロパティ ウィンドウを更新する新しいプロパティ ページ テンプレートを選択します。  
  
6.  **ID** のプロパティの新しい値を入力します。  この例では **IDD\_PROPPAGE\_NEWPAGE**を使用します。  
  
7.  ツール バーの **\[\<ファイル名\> の保存\]** をクリックします。  
  
### 新しいテンプレートをクラスに関連付けます。  
  
1.  クラス ビューを開きます。  
  
2.  ショートカット メニューを開くには、クラス ビューで右クリックします。  
  
3.  ショートカット メニューの \[追加\] をクリックし、さらに \[クラスの追加\] をクリックします。  
  
     これは [クラスの追加](../ide/add-class-dialog-box.md) ダイアログ ボックスが表示されます。  
  
4.  **MFC クラス** のテンプレートをダブルクリックします。  
  
5.  [MFC クラス ウィザード](../mfc/reference/mfc-add-class-wizard.md)の **\[クラス名\]** ダイアログ ボックスで、新しいクラスの名前を入力します。\(この例では `CAddtlPropPage`します\)。  
  
6.  ファイル名を変更するには、**変更**をクリックします。  実装およびヘッダー ファイル名を入力するか、既定の名前を受け入れます。  
  
7.  **基底クラス** ボックスで、`COlePropertyPage`を選択します。  
  
8.  **ダイアログ ID** ボックスで、**IDD\_PROPPAGE\_NEWPAGE**を選択します。  
  
9. クラスをクリック **完了** 。  
  
 割り当てるにはコントロールのユーザーは、この新しいプロパティ ページで、必要なコントロールのプロパティ ページの ID マクロ セクションに次の変更もアクセスします \(コントロールの実装ファイルにある\) :  
  
 [!code-cpp[NVC_MFC_AxUI#32](../mfc/codesnippet/CPP/mfc-activex-controls-adding-another-custom-property-page_1.cpp)]  
  
 `BEGIN_PROPPAGEIDS` マクロ \(プロパティ ページ数\) の 2 番目のパラメーターを 1 ~ 2.の高めなければことに注意してください。  
  
 、ヘッダーが格納されるようにコントロールの実装ファイル \(.cpp\) ファイルを変更する必要があります。H\) 新しいプロパティ ページ クラス ファイル。  
  
 次の手順では、新しいプロパティ ページに型名とキャプションを提供する 2 種類の新しい文字列のリソースを作成することです。  
  
#### 新しい文字列リソースがプロパティ ページに追加するには  
  
1.  開くコントロール プロジェクトを開き開いているリソース ビュー。  
  
2.  **ストリング テーブル** フォルダーをダブルクリックし、文字列を追加する既存のストリング テーブルのリソースをダブルクリックします。  
  
     これはウィンドウのストリング テーブルを開きます。  
  
3.  空白行をストリング テーブルの最後に選択し、文字列のテキスト、またはキャプションを入力する: たとえば、「追加プロパティ ページ」。  
  
     これは **キャプション** と **ID** ボックスを表示 **文字列プロパティ** ページが表示されます。  **キャプション** ボックスに入力した文字列が含まれます。  
  
4.  **ID** ボックスで、文字列の ID を選択するか入力します。  キーは、Enter キーを押します。  
  
     この例では、新しいプロパティ ページのタイプ名に **IDS\_SAMPLE\_ADDPAGE** を使用します。  
  
5.  キャプションの ID と「追加プロパティ ページ」の **IDS\_SAMPLE\_ADDPPG\_CAPTION** を使用して手順 3 ~ 4 を繰り返します。  
  
6.  新しいプロパティ ページ クラスの .cpp ファイルには IDS\_SAMPLE\_ADDPAGE が [AfxOleRegisterPropertyPageClass](../Topic/AfxOleRegisterPropertyPageClass.md)を渡せるように \(この例では `CAddtlPropPage`\) 次の例のように `CAddtlPropPage::CAddtlPropPageFactory::UpdateRegistry` を変更する:  
  
     [!code-cpp[NVC_MFC_AxUI#33](../mfc/codesnippet/CPP/mfc-activex-controls-adding-another-custom-property-page_2.cpp)]  
  
7.  **IDS\_SAMPLE\_ADDPPG\_CAPTION** が `COlePropertyPage` のコンストラクターに渡すことが `CAddtlPropPage` のコンストラクターを次のように変更する:  
  
     [!code-cpp[NVC_MFC_AxUI#34](../mfc/codesnippet/CPP/mfc-activex-controls-adding-another-custom-property-page_3.cpp)]  
  
 必要な変更のリビルドにし、プロジェクトを新しいプロパティ ページをテストするには、テスト コンテナーを使用した後。  テスト コンテナーへのアクセス方法については、「[テスト コンテナーでのプロパティとイベントのテスト](../mfc/testing-properties-and-events-with-test-container.md)」を参照してください。  
  
## 参照  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)