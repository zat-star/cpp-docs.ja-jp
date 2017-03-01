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
- CMemoryException
dev_langs:
- C++
helpviewer_keywords:
- CMemoryException class
- memory exceptions
- exceptions, memory type
- C++ exception handling, memory
- memory, exception handling
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
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
ms.openlocfilehash: 87be1b16d546791d24bbffa62207ec9ccb350139
ms.lasthandoff: 02/24/2017

---
# <a name="cmemoryexception-class"></a>関数のクラス
メモリ不足例外条件を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMemoryException : public CSimpleException  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMemoryException::CMemoryException](#cmemoryexception)|`CMemoryException` オブジェクトを構築します。|  
  
## <a name="remarks"></a>コメント  
 さらに認定には、実現できないことも必要はありません。 メモリ不足例外のスローによって自動的に**新しい**します。 使用して、独自のメモリ関数を記述する場合`malloc`例では後、は、メモリ不足例外をスローするためのします。  
  
 詳細については`CMemoryException`、記事を参照して[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CMemoryException`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="a-namecmemoryexceptiona--cmemoryexceptioncmemoryexception"></a><a name="cmemoryexception"></a>CMemoryException::CMemoryException  
 `CMemoryException` オブジェクトを構築します。  
  
```  
CMemoryException();  
```  
  
### <a name="remarks"></a>コメント  
 このコンス トラクターを直接使用されませんではなく、グローバル関数を呼び出す[AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception)します。 割り当てられていたメモリ内の例外オブジェクトを構築するのでメモリ不足の状況でこのグローバル関数は成功しています。 例外の処理の詳細については、記事を参照してください。[例外](../exception-handling-in-mfc.md)します。  
  
## <a name="see-also"></a>関連項目  
 [CException クラス](cexception-class.md)   
 [階層図](../hierarchy-chart.md)




