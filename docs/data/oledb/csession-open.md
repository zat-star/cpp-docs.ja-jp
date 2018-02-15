---
title: "Csession::open |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CSession::Open
- CSession::Open
- CSession.Open
- ATL.CSession.Open
dev_langs:
- C++
helpviewer_keywords:
- Open method
ms.assetid: c2050c2c-9817-4857-be49-189f346968f6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 919e87efcf38442954544c0471698fcbe5d563c9
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="csessionopen"></a>CSession::Open
データ ソース オブジェクトの新しいセッションを開きます。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Open(const CDataSource& ds,  
   DBPROPSET *pPropSet = NULL,  
   ULONG ulPropSets = 0) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ds`  
 [in]セッションを開く対象となるデータ ソース。  
  
 *pPropSet*  
 [in]配列へのポインター [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx)プロパティと設定する値を含む構造体。 参照してください[プロパティ セットとプロパティ グループ](https://msdn.microsoft.com/en-us/library/ms713696.aspx)で、 *OLE DB プログラマーズ リファレンス*Windows SDK にします。  
  
 `ulPropSets`  
 [in]数[DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx)に渡された構造体、 *pPropSet*引数。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 データ ソース オブジェクトを使用して、開く必要があります[cdatasource::open](../../data/oledb/cdatasource-open.md)に渡す前に`CSession::Open`です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CSession クラス](../../data/oledb/csession-class.md)