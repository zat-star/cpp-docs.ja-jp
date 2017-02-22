---
title: "MFC ActiveX コントロール : 高度なプロパティの実装 | Microsoft Docs"
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
  - "MFC ActiveX コントロール, エラー コード"
  - "MFC ActiveX コントロール, プロパティ"
  - "プロパティ [MFC], ActiveX コントロール"
ms.assetid: ec2e6759-5a8e-41d8-a275-99af8ff6f32e
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# MFC ActiveX コントロール : 高度なプロパティの実装
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、ActiveX コントロールの詳細プロパティの実装に関するトピックについて説明します。:  
  
-   [読み取り専用および書き込み専用プロパティ](#_core_read2donly_and_write2donly_properties)  
  
-   [プロパティから返されるエラー コード](#_core_returning_error_codes_from_a_property)  
  
##  <a name="_core_read2donly_and_write2donly_properties"></a> 読み取り専用および書き込み専用プロパティ  
 プロパティの追加ウィザードは、高速で簡単なメソッドをコントロールの読み取り専用または書き込み専用のプロパティを実装することです。  
  
#### 読み取り専用または書き込み専用のプロパティを実装するには  
  
1.  コントロールのプロジェクトを読み込んでください。  
  
2.  クラス ビューで、コントロール ライブラリ ノードを展開します。  
  
3.  ショートカット メニューを表示するコントロール \(ライブラリ ノードの 2 番目のノード\) のインターフェイス ノードを右クリックします。  
  
4.  ショートカット メニューで、クリック **追加** は、**\[プロパティの追加\]** をクリックします。  
  
     これは [プロパティ 追加ウィザード](../ide/names-add-property-wizard.md)を開きます。  
  
5.  **プロパティ名** ボックスで、プロパティの名前を入力します。  
  
6.  **Implementation Type**の場合、クリック **Get\/Set メソッドの設定**。  
  
7.  **プロパティの種類** ボックスで、プロパティに適切な値を選択します。  
  
8.  読み取り専用プロパティが必要な場合は、Set 関数の名前をオフにします。  書き込み専用のプロパティを使用する場合は、Get 関数名をオフにします。  
  
9. \[完了\] をクリックします。  
  
 この場合、プロパティの追加ウィザードは、標準設定の代わりにディスパッチ マップ エントリで関数 `SetNotSupported` または `GetNotSupported` を挿入または関数を取得します。  
  
 読み取り専用または書き込み専用として既存のプロパティを変更する場合は、ディスパッチ マップを手動で編集し、不要なセットを削除したり、コントロール クラスから関数を取得できます。  
  
 プロパティ \(たとえば、\) 条件付きで読み取り専用または書き込み専用にする場合は、コントロールが特定のモードで実行されている場合のみ、セットを提供するか、標準の方法で取得できます。関数が必要な場合には `SetNotSupported` または `GetNotSupported` 関数を呼び出します。  たとえば、次のようになります。  
  
 [!code-cpp[NVC_MFC_AxUI#29](../mfc/codesnippet/CPP/mfc-activex-controls-advanced-property-implementation_1.cpp)]  
  
 このコード サンプルでは `m_bReadOnlyMode` のデータ メンバーが **TRUE**場合 `SetNotSupported` を呼び出します。  **FALSE**が新しい値に、プロパティが設定されます。  
  
##  <a name="_core_returning_error_codes_from_a_property"></a> プロパティから返されるエラー コード  
 使用するロックを取得しようとしている間またはプロパティを設定するには、パラメーターとして `SCODE` \(ステータス コード\) を受け取る `COleControl::ThrowError` 関数をエラーが発生することを示しています。  定義済みのな `SCODE` を使用するか、独自の 1 を定義できます。  カスタム `SCODE`s を定義するための定義済みのな `SCODE`s と説明の一覧については、" MFC ActiveX コントロール: [ActiveX コントロールの Handling Errors](../mfc/mfc-activex-controls-advanced-topics.md) を参照してください。高度なトピック。  
  
 ヘルパー関数は、[COleControl::SetNotSupported](../Topic/COleControl::SetNotSupported.md)[COleControl::GetNotSupported](../Topic/COleControl::GetNotSupported.md)と [COleControl::SetNotPermitted](../Topic/COleControl::SetNotPermitted.md)などの一般的な定義済みのな `SCODE`s 用にあります。  
  
> [!NOTE]
>  `ThrowError` Get または Set 関数またはオートメーション メソッド内部プロパティからエラーを返すための手段としてのみ使用されるようになっています。  これらは適切な例外ハンドラーがスタックにいる唯一の場合です。  
  
 コードの他の領域のレポートの例外の詳細については、" MFC ActiveX コントロールの [COleControl::FireError](../Topic/COleControl::FireError.md) とセクション [ActiveX コントロールの Handling Errors](../mfc/mfc-activex-controls-advanced-topics.md) を参照します: 高度なトピック。  
  
## 参照  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX コントロール : プロパティ](../mfc/mfc-activex-controls-properties.md)   
 [MFC ActiveX コントロール : メソッド](../mfc/mfc-activex-controls-methods.md)   
 [COleControl クラス](../mfc/reference/colecontrol-class.md)