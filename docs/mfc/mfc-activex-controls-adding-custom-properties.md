---
title: "MFC ActiveX コントロール : カスタム プロパティの追加 | Microsoft Docs"
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
  - "MFC ActiveX コントロール, プロパティ"
  - "プロパティ [MFC], カスタム"
ms.assetid: 85af5167-74c7-427b-b8f3-e0d7b73942e5
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# MFC ActiveX コントロール : カスタム プロパティの追加
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

カスタム プロパティは、ストック プロパティにカスタム プロパティを `COleControl` クラスによって既に実装されないことです。  プロパティがカスタム コントロールを使用するプログラマに ActiveX コントロールを特定の状態に表示するために使用されます。  
  
 ここでは、プロパティの追加ウィザードを使用して ActiveX コントロールにカスタム プロパティを追加する方法と、生成されたコード変更について説明します。  ここでは、次の内容について説明します。  
  
-   [カスタム プロパティを追加するプロパティの追加ウィザードを使用して](#_core_using_classwizard_to_add_a_custom_property)  
  
-   [カスタム プロパティのプロパティ ウィザードの変更を追加します。](#_core_classwizard_changes_for_custom_properties)  
  
 カスタム プロパティは、実装の 4 種類の影響があります: メンバー変数は、通知のメンバー変数は、およびパラメーターで表される get または set メソッド。  
  
-   メンバー変数の実装  
  
     この実装では、コントロール クラスのメンバー変数としてプロパティの状態を表します。  プロパティ値が変化するかを確認する必要がある場合は、メンバー変数の実装を使用します。  3 種類の、この実装はプロパティの最小限のサポート コードを作成します。  メンバー変数の実装のディスパッチ マップ エントリ マクロは [DISP\_PROPERTY](../Topic/DISP_PROPERTY.md)です。  
  
-   通知の実装を持つメンバー変数  
  
     この実装は、プロパティの追加ウィザードによって作成されるメンバー変数と通知関数で構成されます。  通知関数はフレームワークによって自動的にプロパティ値が変更された後に呼び出されます。  プロパティ値が変更された後に通知する必要がある場合は、通知の実装を持つメンバー変数を使用します。  この実装は、関数呼び出しを必要とするため、より多くの時間を要します。  この実装のディスパッチ マップ エントリ マクロは [DISP\_PROPERTY\_NOTIFY](../Topic/DISP_PROPERTY_NOTIFY.md)です。  
  
-   または、メソッドを実装する。  
  
     この実装では、コントロール クラスのメンバー関数のペアで構成されます。  Get\/Set メソッドの実装は自動的にプロパティが変更されると、コントロールのユーザーが要求したときに、コントロールのユーザーがプロパティと構成メンバー関数の現在の値を要求する場合は、Get メンバー関数を呼び出します。  渡された値を検証したり、読み取り専用または書き込み専用プロパティ型のプロパティの値を実行時中に計算するか、実際のプロパティを変更する前に、コントロールのユーザーを実装する必要がある場合は、この実装を使用します。  この実装のディスパッチ マップ エントリ マクロは [DISP\_PROPERTY\_EX](../Topic/DISP_PROPERTY_EX.md)です。  以下のセクションで、[Add a Custom のプロパティへのプロパティの追加ウィザードを使用して](#_core_using_classwizard_to_add_a_custom_property)は、この実装を示すために CircleOffset のカスタム プロパティを使用します。  
  
-   パラメーター化されたな実装  
  
     パラメーター化されたな実装はプロパティの追加ウィザードによってサポートされます。  パラメーター化されたプロパティが \(検索プロパティの配列とも呼ばれる\) コントロールの単一のプロパティを使用して、一連の値にアクセスするために使用できます。  この実装のディスパッチ マップ エントリ マクロは `DISP_PROPERTY_PARAM`です。  この型の実装の詳細については、" MFC ActiveX コントロールの [パラメーター化されたプロパティの実装](../mfc/mfc-activex-controls-advanced-topics.md) を参照します: 高度なトピック。  
  
##  <a name="_core_using_classwizard_to_add_a_custom_property"></a> Add a Custom のプロパティへのプロパティの追加ウィザードを使用して  
 次の手順では、カスタム プロパティ、Get\/Set メソッドの実装を使用する CircleOffset を追加することを示します。  CircleOffset のカスタム プロパティは、コントロールのユーザーがコントロールの外接する四角形の中央の範囲をオフセットすることができます。  実装を持つカスタム プロパティ以外の追加する手順は非常に似ています。get または set メソッド。  
  
 これと同じプロシージャが目的の他にカスタム プロパティを追加することもできます。  CircleOffset プロパティ名とパラメーターのカスタム プロパティの名前で置き換えます。  
  
#### CircleOffset のカスタム プロパティの追加ウィザードのプロパティを追加するには  
  
1.  コントロールのプロジェクトを読み込んでください。  
  
2.  クラス ビューで、コントロール ライブラリ ノードを展開します。  
  
3.  ショートカット メニューを表示するコントロール \(ライブラリ ノードの 2 番目のノード\) のインターフェイス ノードを右クリックします。  
  
4.  ショートカット メニューで、クリック **追加** は、**\[プロパティの追加\]** をクリックします。  
  
     これは [プロパティ 追加ウィザード](../ide/names-add-property-wizard.md)を開きます。  
  
5.  **プロパティ名** ボックスで、`CircleOffset`を入力します。  
  
6.  **Implementation Type**の場合、クリック **Get\/Set メソッドの設定**。  
  
7.  **プロパティの種類** ボックスで、**short**を選択します。  
  
8.  型の一意の名前は Set 関数取得または既定の名前を受け入れます。  
  
9. \[完了\] をクリックします。  
  
##  <a name="_core_classwizard_changes_for_custom_properties"></a> カスタム プロパティのプロパティ ウィザードの変更を追加します。  
 CircleOffset にカスタム プロパティを追加すると、プロパティの追加ウィザードはヘッダーを変更します。コントロール クラスの H\) と実装 \(.cpp\) ファイル。  
  
 次の行が追加されます。2 個の関数を宣言する H ファイルは `GetCircleOffset` と `SetCircleOffset`という:  
  
 [!code-cpp[NVC_MFC_AxUI#25](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-properties_1.h)]  
  
 以下は、コントロールの .IDL ファイルに追加します:  
  
 [!code-cpp[NVC_MFC_AxUI#26](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-properties_2.idl)]  
  
 この行は、プロパティの追加ウィザードのメソッドおよびプロパティの一覧のメソッドの位置にある特定の ID 番号 CircleOffset のプロパティに割り当てます。  
  
 さらに 2 コントロールのハンドラー関数に CircleOffset のプロパティをマップするには、次の行はディスパッチ マップに \(コントロール クラスの .cpp ファイルに\) :追加されます  
  
 [!code-cpp[NVC_MFC_AxUI#27](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-properties_3.cpp)]  
  
 最後に、`GetCircleOffset` の実装と `SetCircleOffset` 関数はコントロールの .cpp ファイルの末尾に追加されます。  ほとんどの場合、プロパティの値を返すには、Get 関数を変更します。  Set 関数は通常、プロパティの変更の前または後にも実行されるコードが含まれます。  
  
 [!code-cpp[NVC_MFC_AxUI#28](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-properties_4.cpp)]  
  
 プロパティの追加ウィザードが Set 関数の本体に、[SetModifiedFlag](../Topic/COleControl::SetModifiedFlag.md)に、自動的に呼び出しを追加することに注意してください。  この関数を呼び出すと、変更されるようにコントロールを示します。  コントロールが変更された場合、新しい状態はコンテナーを保存したときに保存されます。  この関数は、コントロールの永続的な状態の一部として保存されているプロパティの値が変更されるときに呼び出されます。  
  
## 参照  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX コントロール : プロパティ](../mfc/mfc-activex-controls-properties.md)   
 [MFC ActiveX コントロール : メソッド](../mfc/mfc-activex-controls-methods.md)   
 [COleControl クラス](../mfc/reference/colecontrol-class.md)