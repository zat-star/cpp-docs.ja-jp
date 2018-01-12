---
title: "CBookmark クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CBookmark
- ATL::CBookmark<nSize>
- CBookmark
- ATL.CBookmark<nSize>
- ATL::CBookmark
dev_langs: C++
helpviewer_keywords: CBookmark class
ms.assetid: bc942f95-6f93-41d9-bb6e-bcdae4ae0b7a
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dba5f98912fc69bac5554a4c6231f77e17e99d98
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cbookmark-class"></a>CBookmark クラス
バッファーには、ブックマークの値を保持します。  
  
## <a name="syntax"></a>構文  
  
```  
template < DBLENGTH nSize = 0 >  
class CBookmark : public CBookmarkBase  
template < >  
class CBookmark< 0 > : public CBookmarkBase  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nSize`  
 ブックマーク バッファーのバイト単位のサイズ。 ときに`nSize`0 の場合は、ブックマークのバッファーは実行時に動的に作成されます。  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[CBookmark](../../data/oledb/cbookmark-class.md)|コンス トラクター|  
|[GetBuffer](../../data/oledb/cbookmark-getbuffer.md)|バッファーへのポインターを取得します。|  
|[GetSize](../../data/oledb/cbookmark-getsize.md)|バッファーのバイト単位のサイズを取得します。|  
|[SetBookmark](../../data/oledb/cbookmark-setbookmark.md)|ブックマークの値を設定します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子 =](../../data/oledb/cbookmark-operator-equal.md)|1 つ割り当てます`CBookmark`を別のクラスです。|  
  
## <a name="remarks"></a>コメント  
 **CBookmark\<0 >**テンプレート特殊化`CBookmark`; そのバッファーは実行時に動的に作成します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)