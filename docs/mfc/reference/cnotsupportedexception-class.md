---
title: "行わないクラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CNotSupportedException
- AFX/CNotSupportedException
- AFX/CNotSupportedException::CNotSupportedException
dev_langs:
- C++
helpviewer_keywords:
- CNotSupportedException class
- unsupported features
- exceptions, not supported
ms.assetid: e517391b-eb94-4c39-ae32-87b45bf7d624
caps.latest.revision: 20
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 6cb66448d0dadaf1f70c3606bc1b9027bd217a38
ms.lasthandoff: 02/24/2017

---
# <a name="cnotsupportedexception-class"></a>行わないクラス
サポートされていない機能を要求した結果として起こる例外を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CNotSupportedException : public CSimpleException  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CNotSupportedException::CNotSupportedException](#cnotsupportedexception)|`CNotSupportedException` オブジェクトを構築します。|  
  
## <a name="remarks"></a>コメント  
 さらに認定には、実現できないことも必要はありません。  
  
 使用する方法について`CNotSupportedException`、記事を参照して[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CNotSupportedException`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="cnotsupportedexception"></a>CNotSupportedException::CNotSupportedException  
 `CNotSupportedException` オブジェクトを構築します。  
  
```  
CNotSupportedException();
```  
  
### <a name="remarks"></a>コメント  
 このコンス トラクターを直接使用されませんではなく、グローバル関数を呼び出す[AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception)します。 例外の処理の詳細については、記事を参照してください。[例外処理 (MFC)](../exception-handling-in-mfc.md)します。  
  
## <a name="see-also"></a>関連項目  
 [CException クラス](cexception-class.md)   
 [階層図](../hierarchy-chart.md)



