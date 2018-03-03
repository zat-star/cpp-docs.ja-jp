---
title: "MFC ActiveX コントロール: ストック メソッドの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], stock methods
- MFC ActiveX controls [MFC], methods
- DoClick method [MFC]
ms.assetid: bc4fad78-cabd-4cc0-a798-464b1a682f0b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2531f84974626fcdb364df67b12f27d61e75a62a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-adding-stock-methods"></a>MFC ActiveX コントロール : ストック メソッドの追加
ストック メソッドは、クラスによって既に実装されている点で、カスタム メソッドとは異なります。 [COleControl](../mfc/reference/colecontrol-class.md)です。 たとえば、`COleControl`コントロールの更新メソッドをサポートしている定義済みのメンバー関数が含まれています。 このストック メソッドのディスパッチ マップ エントリが**DISP_STOCKFUNC_REFRESH**です。  
  
 `COleControl`2 つのストック メソッドをサポートしています: DoClick および更新します。 更新は、すぐに、コントロールの外観を更新するコントロールのユーザーによって呼び出されます。コントロールのクリックを発生させる DoClick が呼び出されるイベント。  
  
|メソッド|ディスパッチ マップ エントリ|コメント|  
|------------|------------------------|-------------|  
|`DoClick`|**DISP_STOCKPROP_DOCLICK に関するページ)**|Click イベントを発生させます。|  
|**最新の情報に更新**|**DISP_STOCKPROP_REFRESH に関するページ)**|コントロールの外観はすぐに更新します。|  
  
##  <a name="_core_adding_a_stock_method_using_classwizard"></a>ストック メソッドを使用して、追加する、メソッドの追加ウィザード  
 単純なストック メソッドの追加を使用して、[メソッド追加ウィザード](../ide/add-method-wizard.md)です。 次の手順では、MFC ActiveX コントロール ウィザードを使用して作成されたコントロールへの更新メソッドの追加を示します。  
  
#### <a name="to-add-the-stock-refresh-method-using-the-add-method-wizard"></a>メソッド追加ウィザードを使用して在庫の更新メソッドを追加するには  
  
1.  コントロールのプロジェクトを読み込みます。  
  
2.  [クラス ビュー] で、コントロールのライブラリ ノードを展開します。  
  
3.  コントロールのインターフェイス ノード (ライブラリ ノードの 2 番目のノード) を右クリックし、ショートカット メニューを開きます。  
  
4.  ショートカット メニューから **[追加]** をクリックし、**メソッドの追加**です。  
  
     メソッド追加ウィザードが開きます。  
  
5.  **メソッド名**ボックスで、クリックして**更新**です。  
  
6.  **[完了]**をクリックします。  
  
##  <a name="_core_classwizard_changes_for_stock_methods"></a>ストック メソッドのメソッド ウィザードの変更を追加します。  
 Refresh ストック メソッドが、コントロールの基底クラスでサポートされているため、**メソッド追加ウィザード**任意の方法でコントロールのクラスの宣言を変更することはできません。 コントロールのディスパッチ マップにされ、メソッドのエントリを追加、します。IDL ファイルです。 次の行がその実装にあるコントロールのディスパッチ マップに追加 (です。Cpp):  
  
 [!code-cpp[NVC_MFC_AxUI#16](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-methods_1.cpp)]  
  
 これにより、コントロールのユーザーに更新メソッドが使用可能なにします。  
  
 コントロールの次の行が追加されます。IDL ファイル:  
  
 [!code-cpp[NVC_MFC_AxUI#17](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-methods_2.idl)]  
  
 この行では、Refresh メソッドに、特定の ID 番号が割り当てられます。  
  
## <a name="see-also"></a>参照  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)

