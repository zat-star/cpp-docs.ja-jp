---
title: CDBErrorInfo::GetErrorRecords | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDBErrorInfo.GetErrorRecords
- ATL.CDBErrorInfo.GetErrorRecords
- ATL::CDBErrorInfo::GetErrorRecords
- GetErrorRecords
- CDBErrorInfo::GetErrorRecords
dev_langs:
- C++
helpviewer_keywords:
- GetErrorRecords method
ms.assetid: 07746774-bcca-4833-8f55-a619e9777c17
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5187de6c9150ead2c01c770e09cb1a7e64c48004
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="cdberrorinfogeterrorrecords"></a>CDBErrorInfo::GetErrorRecords
指定したオブジェクトのエラー レコードを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetErrorRecords(IUnknown* pUnk,   
   const IID& iid,   
   ULONG* pcRecords) throw();  


HRESULT GetErrorRecords(ULONG* pcRecords) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 *pUnk*  
 [in]エラー レコードを取得する対象のオブジェクトへのインターフェイスします。  
  
 `iid`  
 [in]エラーに関連付けられているインターフェイスの IID です。  
  
 *pcRecords*  
 [out]エラー レコードの (1 から始まる) の数へのポインター。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 エラー情報を取得するには、どのインターフェイスを確認する場合は、関数の最初の形式を使用します。 それ以外の場合、2 番目の形式を使用します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDBErrorInfo クラス](../../data/oledb/cdberrorinfo-class.md)