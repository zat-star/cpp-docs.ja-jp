---
title: "Cenumerator::find |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CEnumerator::Find
- ATL::CEnumerator::Find
- ATL.CEnumerator.Find
- CEnumerator.Find
dev_langs:
- C++
helpviewer_keywords:
- Find method
ms.assetid: 69a153af-d6c3-40fd-9018-27c7d2f344c6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 66298c4be2bb1e43aa37899fe652ccbf6694faae
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="cenumeratorfind"></a>CEnumerator::Find
使用可能なプロバイダーの中から指定した名前を検索します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      bool Find(TCHAR* szSearchName) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 *szSearchName*  
 [in]検索する名前です。  
  
## <a name="return-value"></a>戻り値  
 **true**名前が見つからない場合。 それ以外の場合、 **false**です。  
  
## <a name="remarks"></a>コメント  
 この名前にマップ、 **SOURCES_NAME**のメンバー、 [ISourcesRowset](https://msdn.microsoft.com/en-us/library/ms715969.aspx)インターフェイスです。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CEnumerator クラス](../../data/oledb/cenumerator-class.md)