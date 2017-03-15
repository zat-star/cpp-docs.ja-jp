---
title: "COleControlModule クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleControlModule
dev_langs:
- C++
helpviewer_keywords:
- OLE control modules
- MFC ActiveX controls, OLE control modules
- COleControlModule class
- control modules
ms.assetid: 0721724d-d4af-4eda-ad34-5a2b27810dd4
caps.latest.revision: 23
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
ms.sourcegitcommit: 5c6fbfc8699d7d66c40b0458972d8b6ef0dcc705
ms.openlocfilehash: 2e77c386875d25f47f0cc07eb3b7d315f1678c56
ms.lasthandoff: 02/24/2017

---
# <a name="colecontrolmodule-class"></a>COleControlModule クラス
OLE コントロール モジュール オブジェクトを派生するための基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class COleControlModule : public CWinApp  
```  
  
## <a name="remarks"></a>コメント  
 このクラスは、管理モジュールを初期化するためのメンバー関数を提供します。 Microsoft Foundation クラスを使用する各 OLE コントロール モジュールから派生した&1; つのオブジェクトを含めることができますのみ`COleControlModule`します。 その他の C++ のグローバル オブジェクトが構築されている場合は、このオブジェクトが構築されます。 派生宣言`COleControlModule`グローバル レベルのオブジェクト。  
  
 使用する方法について、`COleControlModule`を参照してください、 [CWinApp](../../mfc/reference/cwinapp-class.md)クラス」および「 [ActiveX コントロール](../../mfc/mfc-activex-controls.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 [CWinApp](../../mfc/reference/cwinapp-class.md)  
  
 `COleControlModule`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxctl.h  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル TESTHELP](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)




