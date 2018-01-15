---
title: "行わないクラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CNotSupportedException
- AFX/CNotSupportedException
- AFX/CNotSupportedException::CNotSupportedException
dev_langs: C++
helpviewer_keywords: CNotSupportedException [MFC], CNotSupportedException
ms.assetid: e517391b-eb94-4c39-ae32-87b45bf7d624
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4013b26e3c07d6ec2a729bf9868db48923e35f86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
 さらに修飾には、必要になるかはありません。  
  
 使用する方法についての`CNotSupportedException`、記事を参照して[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CNotSupportedException`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afx.h  
  
##  <a name="cnotsupportedexception"></a>CNotSupportedException::CNotSupportedException  
 `CNotSupportedException` オブジェクトを構築します。  
  
```  
CNotSupportedException();
```  
  
### <a name="remarks"></a>コメント  
 このコンス トラクターを直接使用しないでくださいではなくグローバル関数を呼び出すことは[AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception)です。 例外の処理の詳細については、記事を参照してください。 [MFC での例外処理](../exception-handling-in-mfc.md)です。  
  
## <a name="see-also"></a>参照  
 [CException クラス](cexception-class.md)   
 [階層図](../hierarchy-chart.md)


