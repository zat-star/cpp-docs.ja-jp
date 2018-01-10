---
title: "Cenumerator::open |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CEnumerator.Open
- CEnumerator::Open
- ATL::CEnumerator::Open
- CEnumerator.Open
dev_langs: C++
helpviewer_keywords: Open method
ms.assetid: b22821a0-257a-4543-ad0c-2649d4ac092e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3a5c35b3806e04f20417c7053248d1a098456403
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cenumeratoropen"></a>CEnumerator::Open
モニカーを指定すると、いずれかの場合は、列挙子を呼び出すことによって、行セットを取得、列挙子のバインド[isourcesrowset:](https://msdn.microsoft.com/en-us/library/ms711200.aspx)です。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT Open(   
   LPMONIKER pMoniker    
) throw( );  
HRESULT Open(   
   const CLSID* pClsid = & CLSID_OLEDB_ENUMERATOR    
) throw( );  
HRESULT Open(   
   const CEnumerator& enumerator    
) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pMoniker`  
 [in]列挙子のモニカーへのポインター。  
  
 *pclsid の値*  
 [in]ポインター、 **CLSID**の列挙子。  
  
 `enumerator`  
 [in]列挙子への参照。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CEnumerator クラス](../../data/oledb/cenumerator-class.md)