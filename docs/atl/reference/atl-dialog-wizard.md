---
title: "ATL ダイアログ ウィザード |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.dlg.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding dialog resources
- ATL Dialog Wizard
ms.assetid: b0b9ace5-83c9-40d3-82c3-eb6293f10583
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 43540b1b86dbbf1777e7d5a7f6d8dec5dc618334
ms.lasthandoff: 02/24/2017

---
# <a name="atl-dialog-wizard"></a>ATL ダイアログ ウィザード
このウィザードが、プロジェクトにから派生した、ATL ダイアログ ボックス オブジェクトを挿入[CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md)します。 ダイアログ ボックスから派生した`CAxDialogImpl`ActiveX コントロールをホストすることができます。  
  
 ウィザードは、既定値 ダイアログ リソースを作成**OK**と**キャンセル**ボタン。 ダイアログ リソースを編集し、ActiveX コントロールを使用して追加、[ダイアログ エディター](../../windows/dialog-editor.md)リソース ビューで。  
  
 ヘッダー ファイルに挿入された、[メッセージ マップ](../../atl/message-maps-atl.md)既定値を処理するための宣言には、イベントが をクリックします。 参照してください[ ダイアログ ボックスを実装する](../../atl/implementing-a-dialog-box.md)ATL ダイアログ ボックスの詳細についてです。  
  
 **短い名前**  
 ATL ダイアログ オブジェクトの省略名を設定します。 指定した名前では、これらのフィールドを個別に変更する場合を除き、クラス名とファイル (.cpp、.h) 名を決定します。  
  
 `Class`  
 作成するクラスの名前を設定します。 この名前で指定した名前に基づきます**短い名前**、"C"、クラス名の一般的なプレフィックスが付きます。  
  
 **.h ファイル**  
 新しいオブジェクトのクラスのヘッダー ファイルの名前を設定します。 既定では、この名前はで指定した名前に基づく**短い名前**します。 ファイル名を任意の場所に保存するか、既存のファイルに、クラス宣言を追加する、省略記号ボタンをクリックします。 既存のファイルを選択すると場合、ウィザードは保存されません選択した場所に表示されるまで をクリック**完了**ウィザード。  
  
 ウィザードでは、ファイルは上書きされません。 クリックすると、既存のファイルの名前を選択するかどうかは**完了**ウィザードでは、クラス宣言がファイルの内容に追加されるかどうかを指定するように求められます。 をクリックして**はい**ファイルを追加する をクリックして**なし**ウィザードに戻り、別のファイル名を指定します。  
  
 **.cpp ファイル**  
 新しいオブジェクトのクラスの実装ファイルの名前を設定します。 既定では、この名前はで指定した名前に基づく**短い名前**します。 任意の場所にファイル名を保存する、省略記号ボタンをクリックします。 クリックするまで、選択した場所にファイルが保存されません**完了**ウィザード。  
  
 ウィザードでは、ファイルは上書きされません。 クリックすると、既存のファイルの名前を選択するかどうかは**完了**ウィザードでは、クラスの実装が、ファイルの内容に追加されるかどうかを指定するように求められます。 をクリックして**はい**ファイルを追加する をクリックして**なし**ウィザードに戻り、別のファイル名を指定します。  
  
## <a name="see-also"></a>関連項目  
 [[ATL] ダイアログ ボックス](../../atl/reference/adding-an-atl-dialog-box.md)


