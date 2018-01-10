---
title: "ツール バー コントロールのスタイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: ToolBar control styles [MFC]
ms.assetid: 0f717eb9-fa32-4263-b852-809238863feb
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9d81be893ce84da24b3a30518219ee1f6fd10057
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="toolbar-control-styles"></a>ツール バー コントロールのスタイル
[CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)外観を決定するスタイル フラグのセットと、ボタンの動作を持ちます。 これらのフラグの組み合わせを設定するには呼び出すことによって[CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle)です。 このトピックでは、スタイル フラグの値とその意味を示します。  
  
## <a name="property-values"></a>プロパティ値  
 次の値には、コントロールを表すボタンの種類を決定します。  
  
 TBBS_BUTTON  
 標準プッシュ ボタン (既定)。  
  
 TBBS_CHECKBOX  
 オンにします。  
  
 TBBS_CHECKGROUP  
 チェック ボックスのグループの開始。  
  
 TBBS_GROUP  
 ボタンのグループの開始。  
  
 TBBS_SEPARATOR  
 区切り記号。  
  
 次の値は、コントロールの現在の状態を表します。  
  
 TBBS_CHECKED  
 チェック ボックスをオンします。  
  
 TBBS_DISABLED  
 コントロールが無効です。  
  
 TBBS_INDETERMINATE  
 チェック ボックスは、不定状態では。  
  
 TBBS_PRESSED  
 ボタンが押されました。  
  
 次の値は、ツールバーのボタンのレイアウトを変更します。  
  
 TBBS_BREAK  
 新しい行にまたは新しい列の列を分離することがなく、項目を配置します。  
  
## <a name="remarks"></a>コメント  
 現在のスタイルが格納されている[CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle)です。 新しい値を設定しないで`m_nStyle`直接、いくつかの派生クラスで呼び出すときに、追加の処理を実行するため`SetStyles`です。  
  
 ビジュアル マネージャーでは、各状態のボタンの外観を決定します。 参照してください[ビジュアル マネージャー](../../mfc/visualization-manager.md)詳細についてはします。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxtoolbarbutton.h  
  
## <a name="see-also"></a>参照  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)   
 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [ビジュアル マネージャー](../../mfc/visualization-manager.md)


