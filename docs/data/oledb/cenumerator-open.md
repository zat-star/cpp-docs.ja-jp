---
title: "Cenumerator::open |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CEnumerator.Open
- CEnumerator::Open
- ATL::CEnumerator::Open
- CEnumerator.Open
dev_langs:
- C++
helpviewer_keywords:
- Open method
ms.assetid: b22821a0-257a-4543-ad0c-2649d4ac092e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1492208d75637a1a0e3eb1b959aac34a81043b07
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="cenumeratoropen"></a>CEnumerator::Open
モニカーを指定すると、いずれかの場合は、列挙子を呼び出すことによって、行セットを取得、列挙子のバインド[isourcesrowset:](https://msdn.microsoft.com/en-us/library/ms711200.aspx)です。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Open(LPMONIKER pMoniker) throw();  


HRESULT Open(const CLSID* pClsid = & CLSID_OLEDB_ENUMERATOR) throw();  


HRESULT Open(const CEnumerator& enumerator) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pMoniker`  
 [in]列挙子のモニカーへのポインター。  
  
 *pClsid*  
 [in]ポインター、 **CLSID**の列挙子。  
  
 `enumerator`  
 [in]列挙子への参照。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CEnumerator クラス](../../data/oledb/cenumerator-class.md)