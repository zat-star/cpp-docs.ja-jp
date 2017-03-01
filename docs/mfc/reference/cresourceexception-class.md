---
title: "クラスの関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CResourceException
dev_langs:
- C++
helpviewer_keywords:
- resource allocation exception
- resources [C++], allocating
- resource exceptions
- exceptions, resource
- CResourceException class
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
caps.latest.revision: 22
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
ms.openlocfilehash: 2013a73f91687277df9dd1e6747aba2dd02a4346
ms.lasthandoff: 02/24/2017

---
# <a name="cresourceexception-class"></a>関数のクラス
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
 さらに認定には、実現できないことも必要はありません。  
  
 使用する方法について`CResourceException`、記事を参照して[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CResourceException`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="a-namecresourceexceptiona--cresourceexceptioncresourceexception"></a><a name="cresourceexception"></a>CResourceException::CResourceException  
 `CResourceException` オブジェクトを構築します。  
  
```  
CResourceException();
```  
  
### <a name="remarks"></a>コメント  
 このコンス トラクターを直接使用されませんではなく、グローバル関数を呼び出す[AfxThrowResourceException](exception-processing.md#afxthrowresourceexception)します。 例外の詳細については、記事を参照してください。[例外処理 (MFC)](../exception-handling-in-mfc.md)します。  
  
## <a name="see-also"></a>関連項目  
 [CException クラス](cexception-class.md)   
 [階層図](../hierarchy-chart.md)



