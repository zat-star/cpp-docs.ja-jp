---
title: "Cbulkrowset::movetobookmark |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBulkRowset<TAccessor>::MoveToBookmark
- CBulkRowset.MoveToBookmark
- MoveToBookmark
- ATL.CBulkRowset.MoveToBookmark
- CBulkRowset::MoveToBookmark
- ATL::CBulkRowset<TAccessor>::MoveToBookmark
- ATL::CBulkRowset::MoveToBookmark
dev_langs:
- C++
helpviewer_keywords:
- MoveToBookmark method
ms.assetid: 76aab025-819e-4ecd-ae0a-d8d3fb2d2099
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 07703acbe483f30c2d458f481b7ff301c937d6d4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="cbulkrowsetmovetobookmark"></a>CBulkRowset::MoveToBookmark
ブックマークまたは指定されたオフセット位置の行でマークされた行がフェッチされます (`lSkip`) そのブックマークからです。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT MoveToBookmark(const CBookmarkBase& bookmark,  
   DBCOUNTITEM lSkip = 0) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `bookmark`  
 [in]データをフェッチする位置を示すブックマーク。  
  
 `lSkip`  
 [in]対象の行にブックマークからの行の数。 場合`lSkip`0 の場合は、フェッチされた最初の行は、ブックマークが付けられた行です。 場合`lSkip`1 の場合は、ブックマークが付けられた行の後ろには、行、最初の行をフェッチします。 場合`lSkip`-1 で、最初のフェッチされた行は、行のブックマークが付けられた行の前にします。  
  
## <a name="return-value"></a>戻り値  
 参照してください[irowset::getdata](https://msdn.microsoft.com/en-us/library/ms716988.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CBulkRowset クラス](../../data/oledb/cbulkrowset-class.md)