---
title: "ツール バー コントロールのスタイル |Microsoft ドキュメント"
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
- ToolBar control styles
ms.assetid: 0f717eb9-fa32-4263-b852-809238863feb
caps.latest.revision: 16
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1c50009a50c5b80e007add9de679315df6aecea9
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="toolbar-control-styles"></a>ツール バー コントロールのスタイル
[CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)がボタンの動作と外観を表すスタイル フラグのセットです。 これらのフラグの組み合わせを設定するにを呼び出して[CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle)します。 このトピックでは、スタイルのフラグの値とその意味を示します。  
  
## <a name="property-values"></a>プロパティ値  
 次の値では、コントロールを表すボタンの種類を決定します。  
  
 TBBS_BUTTON  
 標準プッシュ ボタン (既定)。  
  
 TBBS_CHECKBOX  
 チェック ボックスです。  
  
 TBBS_CHECKGROUP  
 チェック ボックスのグループの開始。  
  
 TBBS_GROUP  
 ボタンのグループの開始。  
  
 TBBS_SEPARATOR  
 区切り記号。  
  
 次の値は、コントロールの現在の状態を表します。  
  
 TBBS_CHECKED  
 チェック ボックスをオンにするとします。  
  
 TBBS_DISABLED  
 コントロールが無効にします。  
  
 TBBS_INDETERMINATE  
 チェック ボックスは、不定状態では。  
  
 TBBS_PRESSED  
 ボタンが押されました。  
  
 次の値は、ツールバーのボタンのレイアウトを変更します。  
  
 TBBS_BREAK  
 または、新しい列で、新しい行に列を分離することがなく、項目を配置します。  
  
## <a name="remarks"></a>コメント  
 現在のスタイルは[CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle)します。 新しい値を設定しないでください`m_nStyle`直接、いくつかの派生クラスを呼び出すときに、追加の処理を実行するため`SetStyles`です。  
  
 ビジュアル マネージャーでは、各状態のボタンの外観を決定します。 参照してください[ビジュアル マネージャー](../../mfc/visualization-manager.md)の詳細。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxtoolbarbutton.h  
  
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)   
 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [ビジュアル マネージャー](../../mfc/visualization-manager.md)



