---
title: "COleControlModule クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- OleControlModule
dev_langs:
- C++
helpviewer_keywords:
- OLE control modules [MFC]
- MFC ActiveX controls [MFC], OLE control modules
- COleControlModule class [MFC]
- control modules [MFC]
ms.assetid: 0721724d-d4af-4eda-ad34-5a2b27810dd4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 196b69a0d86c3809415e030adb567c8642051f40
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="colecontrolmodule-class"></a>COleControlModule クラス
OLE コントロール モジュール オブジェクトを派生するための基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class COleControlModule : public CWinApp  
```  
  
## <a name="remarks"></a>コメント  
 このクラスは、コントロール モジュールを初期化するためのメンバー関数を提供します。 Microsoft Foundation classes を使用する各 OLE コントロール モジュールがから派生した 1 つのオブジェクトを含めることができますのみ`COleControlModule`です。 その他の C++ のグローバル オブジェクトが構築されるときに、このオブジェクトが構築されます。 宣言、派生`COleControlModule`グローバル レベルのオブジェクト。  
  
 使用する方法について、`COleControlModule`クラスを参照してください、 [CWinApp](../../mfc/reference/cwinapp-class.md)クラス」および「 [ActiveX コントロール](../../mfc/mfc-activex-controls.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 [CWinApp](../../mfc/reference/cwinapp-class.md)  
  
 `COleControlModule`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxctl.h  
  
## <a name="see-also"></a>参照  
 [MFC サンプル TESTHELP](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)



