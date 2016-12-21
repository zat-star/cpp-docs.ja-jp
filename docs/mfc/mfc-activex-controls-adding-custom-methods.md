---
title: "MFC ActiveX コントロール : カスタム メソッドの追加 | Microsoft Docs"
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
  - "MFC ActiveX コントロール, メソッド"
  - "PtInCircle カスタム メソッド"
ms.assetid: 8f8dc344-44a0-4021-8db5-4cdd3d700e18
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC ActiveX コントロール : カスタム メソッドの追加
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

カスタム メソッドはストック メソッドと `COleControl`で既に実装されないことです。  データをコントロールに追加した各カスタム メソッドの実装を提供する必要があります。  
  
 ActiveX コントロールのユーザーは、コントロール固有のアクションを実行するカスタム メソッドをいつでも呼び出すことができます。  カスタム メソッドのディスパッチ マップ エントリがフォーム `DISP_FUNCTION`です。  
  
##  <a name="_core_adding_a_custom_method_with_classwizard"></a> 追加のメソッドと、ウィザードでカスタム メソッドの追加  
 次の手順では、ActiveX コントロールのスケルトン コードへのカスタム PtInCircle メソッドを追加することです。  PtInCircle はコントロールに渡す座標が範囲外にあるかどうかの中によって決まります。  これと同じプロシージャが他のカスタム メソッドを追加することもできます。  PtInCircle メソッド名、およびパラメーターをカスタム メソッドの名前とパラメーターに置き換えてください。  
  
> [!NOTE]
>  この例では、"イベントの `InCircle` 関数を使用します。  この関数の詳細については、記事 [MFC ActiveX コントロール: ActiveX コントロールにカスタム イベントを追加できます。](../Topic/MFC%20ActiveX%20Controls:%20Adding%20Custom%20Events.md)を参照します。  
  
#### PtInCircle カスタム メソッドを追加ウィザードのメソッドを追加するには  
  
1.  コントロールのプロジェクトを読み込んでください。  
  
2.  クラス ビューで、コントロール ライブラリ ノードを展開します。  
  
3.  ショートカット メニューを表示するコントロール \(ライブラリ ノードの 2 番目のノード\) のインターフェイス ノードを右クリックします。  
  
4.  ショートカット メニューの **追加** をクリックし、**メソッドの追加**をクリックします。  
  
     これは、メソッドの追加ウィザードが表示されます。  
  
5.  **メソッド名** ボックスで、`PtInCircle`を入力します。  
  
6.  **内部名** ボックスで、メソッドの内部関数の名前を入力するか、既定値 \(この場合は `PtInCircle`\) を使用します。  
  
7.  **戻り値の型** ボックスで、メソッドの戻り値の型の **VARIANT\_BOOL** をクリックします。  
  
8.  **パラメータの種類** と **パラメータ名** のコントロールを使用して、`xCoord` \(型 **OLE\_XPOS\_PIXELS**\) というパラメーターを追加します。  
  
9. **パラメータの種類** と **パラメータ名** のコントロールを使用して、`yCoord` \(型 **OLE\_YPOS\_PIXELS**\) というパラメーターを追加します。  
  
10. \[完了\] をクリックします。  
  
##  <a name="_core_classwizard_changes_for_custom_methods"></a> カスタム メソッドのメソッド ウィザードの変更を追加します。  
 カスタム メソッドを追加すると、追加のメソッド ウィザードはコントロール クラスのヘッダーを変更します。H\) と実装 \(.cpp\) ファイル。  次の行では、コントロール クラスのヘッダーのディスパッチ マップの宣言に追加されます。H\) ファイル:  
  
 [!code-cpp[NVC_MFC_AxUI#18](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-methods_1.h)]  
  
 このコードは、Dispatch メソッド ハンドラーによって呼び出されます `PtInCircle`を宣言します。  この関数は、外部名 PtInCircle を使用するコントロールのユーザーから呼び出すことができます。  
  
 以下は、コントロールの .IDL ファイルに追加します:  
  
 [!code-cpp[NVC_MFC_AxUI#19](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-methods_2.idl)]  
  
 この行は特定の ID 番号、メソッドの追加ウィザードのメソッドのメソッドの位置 PtInCircle のメソッドに割り当て、プロパティを選択します。  カスタム メソッドを追加するには、追加のメソッド ウィザードが使用されているため、のエントリがプロジェクトの .IDL ファイルに自動的に追加されます。  
  
 また、コントロール クラスの実装 \(.cpp\) ファイル内の次の行はコントロールのディスパッチ マップに追加します:  
  
 [!code-cpp[NVC_MFC_AxUI#20](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-methods_3.cpp)]  
  
 `DISP_FUNCTION` マクロはコントロールのハンドラー関数に PtInCircle メソッド、`PtInCircle`をマップし、**VARIANT\_BOOL**であると戻り値の型を宣言し `PtInCircle`に渡される型 **VTS\_XPOS\_PIXELS** と **VTS\_YPOSPIXELS** の 2 個のパラメーターを宣言します。  
  
 最後に、追加のメソッドはウィザード コントロールの実装 \(.cpp\) ファイルの下にスタブ関数 `CSampleCtrl::PtInCircle` を追加します。  既に説明したように機能する `PtInCircle` に次のように変更する必要があります:  
  
 [!code-cpp[NVC_MFC_AxUI#21](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-methods_4.cpp)]  
  
## 参照  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)   
 [\[クラス ビュー\] ウィンドウとオブジェクト ブラウザーのアイコン](../Topic/Class%20View%20and%20Object%20Browser%20Icons.md)