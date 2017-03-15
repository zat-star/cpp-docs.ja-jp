---
title: "MFC ActiveX コントロール : ストック メソッドの追加 | Microsoft Docs"
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
  - "DoClick メソッド"
  - "MFC ActiveX コントロール, メソッド"
  - "MFC ActiveX コントロール, ストック メソッド"
ms.assetid: bc4fad78-cabd-4cc0-a798-464b1a682f0b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# MFC ActiveX コントロール : ストック メソッドの追加
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ストック メソッドはカスタム メソッドと [COleControl](../mfc/reference/colecontrol-class.md)クラスによって実装されることです。  たとえば、`COleControl` はコントロールの更新のメソッドをサポートする定義済みのなメンバー関数が含まれています。  このストック メソッドのディスパッチ マップ エントリが **DISP\_STOCKFUNC\_REFRESH**です。  
  
 `COleControl` は 2 個のストック メソッドをサポートする: DoClick と更新。  更新は、コントロールのユーザーが、コントロールの外観を更新するために呼び出される; DoClick はコントロールの Click イベントを発生させるために呼び出します。  
  
|方法|ディスパッチ マップ エントリ|コメント|  
|--------|---------------------|----------|  
|`DoClick`|**DISP\_STOCKPROP\_DOCLICK \(\)**|Click イベントを発生させます。|  
|**更新する**|**DISP\_STOCKPROP\_REFRESH \(\)**|このコントロールの外観を更新します。|  
  
##  <a name="_core_adding_a_stock_method_using_classwizard"></a> メソッドの追加ウィザードを使用して、ストック メソッドの追加  
 ストック メソッドを追加するには [メソッド追加ウィザード](../ide/add-method-wizard.md)を使用する方法です。  次の手順では、MFC ActiveX コントロール ウィザードを使用して作成されたコントロールへの更新メソッドを追加することです。  
  
#### 標準的な更新のメソッドを追加ウィザードのメソッドを追加するには  
  
1.  コントロールのプロジェクトを読み込んでください。  
  
2.  クラス ビューで、コントロール ライブラリ ノードを展開します。  
  
3.  ショートカット メニューを表示するコントロール \(ライブラリ ノードの 2 番目のノード\) のインターフェイス ノードを右クリックします。  
  
4.  ショートカット メニューの **追加** をクリックし、**メソッドの追加**をクリックします。  
  
     これは、メソッドの追加ウィザードが表示されます。  
  
5.  **メソッド名** ボックスで、**最新の情報に更新**をクリックします。  
  
6.  \[完了\] をクリックします。  
  
##  <a name="_core_classwizard_changes_for_stock_methods"></a> ストック メソッドのメソッド ウィザードの変更を追加します。  
 標準的な更新のメソッドがコントロールの基本クラスによってサポートされているため、**メソッド追加ウィザード** では、コントロールのクラス宣言を変更しません。  これは、コントロールのディスパッチ マップと .IDL ファイルにメソッドのエントリを追加します。  以下は、実装 \(.cpp\) ファイルにあるコントロールのディスパッチ マップに追加します:  
  
 [!code-cpp[NVC_MFC_AxUI#16](../mfc/codesnippet/CPP/mfc-activex-controls-adding-stock-methods_1.cpp)]  
  
 これにより、更新のメソッドをコントロールのユーザーが使用できるようにします。  
  
 以下は、コントロールの .IDL ファイルに追加します:  
  
 [!code-cpp[NVC_MFC_AxUI#17](../mfc/codesnippet/CPP/mfc-activex-controls-adding-stock-methods_2.idl)]  
  
 この行は特定の ID 番号の更新メソッドに割り当てます。  
  
## 参照  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)