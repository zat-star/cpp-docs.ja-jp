---
title: "Crestrictions::open |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRestrictions.Open
- ATL::CRestrictions::Open
- ATL.CRestrictions.Open
- CRestrictions::Open
dev_langs:
- C++
helpviewer_keywords:
- Open method
ms.assetid: 0aff0cc3-543a-47d2-8d6b-ebb36926b6db
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1cd31f50258303492cfb7ca92daa5cdfb526c44a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="crestrictionsopen"></a>CRestrictions::Open
ユーザー指定の制限に従って、結果セットを返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Open(const CSession& session,  
   LPCTSTR lpszParam 1 = NULL,  
   LPCTSTR lpszParam 2 = NULL,  
   LPCTSTR lpszParam 3 = NULL,  
   LPCTSTR lpszParam 4 = NULL,  
   LPCTSTR lpszParam 5 = NULL,  
   LPCTSTR lpszParam 6 = NULL,  
   LPCTSTR lpszParam 7 = NULL,  
   bool bBind = true);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `session`  
 [in]データ ソースへの接続に使用される既存のセッション オブジェクトを指定します。  
  
 *lpszParam*  
 [in]スキーマ行セットの制限を指定します。  
  
 `bBind`  
 [in]列マップを自動的にバインドするかどうかを指定します。 既定値は**true**、それが原因で列マップが自動的に連結されます。 設定`bBind`に**false**手動でバインドできるように、列マップの自動に連結します。 (手動バインディングは、OLAP のユーザーに特に関心があるは) です。  
  
## <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
## <a name="remarks"></a>コメント  
 7 個の制限の最大値は、スキーマ行セットを指定できます。  
  
 参照してください[IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx)定義されている制限については、各スキーマ行セットにします。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbsch.h  
  
## <a name="see-also"></a>参照  
 [CRestrictions クラス](../../data/oledb/crestrictions-class.md)   
 [スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)