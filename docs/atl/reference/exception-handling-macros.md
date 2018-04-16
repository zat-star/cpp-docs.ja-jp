---
title: "例外処理マクロ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atldef/ATL::_ATLCATCH
- atldef/ATL::_ATLCATCHALL
- atldef/ATL::_ATLTRY
dev_langs:
- C++
helpviewer_keywords:
- exception handling, macros
- C++ exception handling, macros
ms.assetid: a8385d34-3fb0-4006-a42a-de045cacf0f4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 424a65c44d7bb22d1fef6e21e1892967ecd3e9b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="exception-handling-macros"></a>例外処理マクロ
これらのマクロは、例外処理のサポートを提供します。  
  
|||  
|-|-|  
|[_ATLCATCH](#_atlcatch)|関連する発生したエラーを処理するステートメント`_ATLTRY`です。|  
|[_ATLCATCHALL](#_atlcatchall)|関連する発生したエラーを処理するステートメント`_ATLTRY`です。|  
|[_ATLTRY](#_atltry)|エラーが発生する可能性があります、保護されたコード セクションをマークします。|  
  
## <a name="requirements"></a>要件:
**ヘッダー:** atldef.h

##  <a name="_atlcatch"></a>_ATLCATCH  
 関連する発生したエラーを処理するステートメント`_ATLTRY`です。  
  
```
_ATLCATCH(e)
```  
  
### <a name="parameters"></a>パラメーター  
 *e*  
 キャッチする例外。  
  
### <a name="remarks"></a>コメント  
 組み合わせて使用`_ATLTRY`です。 C++ に解決される[(CAtlException e) をキャッチ](../../cpp/try-throw-and-catch-statements-cpp.md)C++ 例外の指定された型を処理するためです。  
  
##  <a name="_atlcatchall"></a>_ATLCATCHALL  
 関連する発生したエラーを処理するステートメント`_ATLTRY`です。  
  
```
_ATLCATCHALL
```  
  
### <a name="remarks"></a>コメント  
 組み合わせて使用`_ATLTRY`です。 C++ に解決される[catch (...)](../../cpp/try-throw-and-catch-statements-cpp.md)すべての種類の C++ 例外を処理するためです。  
  
##  <a name="_atltry"></a>_ATLTRY  
 エラーが発生する可能性があります、保護されたコード セクションをマークします。  
  
```
_ATLTRY
```  
  
### <a name="remarks"></a>コメント  
 組み合わせて使用[_ATLCATCH](#_atlcatch)または[_ATLCATCHALL](#_atlcatchall)です。 C++ シンボルに解決される[再試行](../../cpp/try-throw-and-catch-statements-cpp.md)です。  
  
## <a name="see-also"></a>参照  
 [[マクロ]](../../atl/reference/atl-macros.md)
