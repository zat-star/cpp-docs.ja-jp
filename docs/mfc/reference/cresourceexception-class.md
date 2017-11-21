---
title: "関数クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CResourceException
- AFXWIN/CResourceException
- AFXWIN/CResourceException::CResourceException
dev_langs: C++
helpviewer_keywords: CResourceException [MFC], CResourceException
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 497ced5337a44bb0d72be734cfea35a30ead383b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="cresourceexception-class"></a>関数クラス
Windows が要求されたリソースを見つけられないか、割り当てられないときに生成されます。  
  
## <a name="syntax"></a>構文  
  
```  
class CResourceException : public CSimpleException  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CResourceException::CResourceException](#cresourceexception)|`CResourceException` オブジェクトを構築します。|  
  
## <a name="remarks"></a>コメント  
 さらに修飾には、必要になるかはありません。  
  
 使用する方法についての`CResourceException`、記事を参照して[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CResourceException`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cresourceexception"></a>CResourceException::CResourceException  
 `CResourceException` オブジェクトを構築します。  
  
```  
CResourceException();
```  
  
### <a name="remarks"></a>コメント  
 このコンス トラクターを直接使用しないでくださいではなくグローバル関数を呼び出すことは[AfxThrowResourceException](exception-processing.md#afxthrowresourceexception)です。 例外の詳細については、記事を参照してください。 [MFC での例外処理](../exception-handling-in-mfc.md)です。  
  
## <a name="see-also"></a>関連項目  
 [CException クラス](cexception-class.md)   
 [階層図](../hierarchy-chart.md)


