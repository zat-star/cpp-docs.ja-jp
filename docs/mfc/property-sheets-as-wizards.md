---
title: "ウィザードとしてのプロパティ シート |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: property sheets, as wizards
ms.assetid: 1ea66ecb-23b0-484a-838d-58671a2999b5
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 65aedc5dbeb8a740d5713983f66eefe693864937
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="property-sheets-as-wizards"></a>ウィザードとしてのプロパティ シート
ウィザードのプロパティ シートの主な特徴は、タブの代わりに、[次へ] または [完了]、バックアップ、および [キャンセル] ボタンでナビゲーションが提供されることです。 呼び出す必要がある[CPropertySheet::SetWizardMode](../mfc/reference/cpropertysheet-class.md#setwizardmode)呼び出す前に[する](../mfc/reference/cpropertysheet-class.md#domodal)プロパティ シート オブジェクトでこの機能を活用するためにします。  
  
 ユーザーは同じ[CPropertyPage::OnSetActive](../mfc/reference/cpropertypage-class.md#onsetactive)と[CPropertyPage::OnKillActive](../mfc/reference/cpropertypage-class.md#onkillactive)別のページに 1 つのページから移動する際に通知します。 [次へ] および [完了] ボタンは、相互に排他的なコントロールです。つまり、一度にうち片方だけが表示されます。 最初のページで、[次へ] ボタンを有効にする必要があります。 ユーザーが最後のページにある場合は、[完了] ボタンを有効にする必要があります。 これを行わない自動的に、フレームワークによってです。 呼び出す必要がある[CPropertySheet::SetWizardButton](../mfc/reference/cpropertysheet-class.md#setwizardbuttons)これを実現するために最後のページにします。  
  
 すべての既定のボタンを表示するは、[完了] ボタンを表示し、[次へ] ボタンを移動します。 次のボタンに相対的位置を維持するため、[戻る] ボタンを移動します。  
  
## <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#5](../mfc/codesnippet/cpp/property-sheets-as-wizards_1.cpp)]  
  
## <a name="see-also"></a>参照  
 [プロパティ シート](../mfc/property-sheets-mfc.md)

