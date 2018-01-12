---
title: "Idbschemarowsetimpl::createschemarowset |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDBSchemaRowsetImpl::CreateSchemaRowset
- ATL::IDBSchemaRowsetImpl::CreateSchemaRowset
- CreateSchemaRowset
- IDBSchemaRowsetImpl.CreateSchemaRowset
- ATL.IDBSchemaRowsetImpl.CreateSchemaRowset
dev_langs: C++
helpviewer_keywords: CreateSchemaRowset method
ms.assetid: ad3e3e4d-45b9-461c-b7b8-3af6843631b1
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 25d8149cb2e32505d87ef845b525684746d2b8da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="idbschemarowsetimplcreateschemarowset"></a>IDBSchemaRowsetImpl::CreateSchemaRowset
テンプレート パラメーターで指定されたオブジェクトの COM オブジェクトの作成関数を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      template < class   
      SchemaRowsetClass  
       >  
HRESULT CreateSchemaRowset(  
   IUnknown *pUnkOuter,  
   ULONG cRestrictions,  
   const VARIANT rgRestrictions[],  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown** ppRowset,  
   SchemaRowsetClass*& pSchemaRowset   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pUnkOuter`  
 [入力] 集約時は外部 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 。それ以外の場合は **NULL**。  
  
 `cRestrictions`  
 [入力] スキーマ行セットに適用する制限の数。  
  
 `rgRestrictions`  
 [入力] 行セットに適用する `cRestrictions`**VARIANT**の配列。  
  
 `riid`  
 [入力] 出力 [IUnknown](../../atl/queryinterface.md) の **QueryInterface**の対象インターフェイス。  
  
 `cPropertySets`  
 [入力] 設定するプロパティ セットの数。  
  
 `rgPropertySets`  
 [入力] 設定するプロパティを指定する [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 構造体の配列。  
  
 `ppRowset`  
 [出力] **で要求した出力** IUnknown `riid`。 この **IUnknown** はスキーマ行セット オブジェクトのインターフェイスです。  
  
 `pSchemaRowset`  
 [出力] スキーマ行セット クラスのインスタンスへのポインター。 通常、このパラメーターは使用されません。使用できるのは、スキーマ行セットを COM オブジェクトに渡す前に、その行セットで多くの作業を実行する必要があるときです。 `pSchemaRowset` の有効期間は `ppRowset`によって制限されます。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
## <a name="remarks"></a>コメント  
 この関数は、あらゆる種類のスキーマ行セットに対する汎用作成関数を実装します。 通常、この関数は、ユーザーからは呼び出されません。 これはスキーマ マップの実装によって呼び出されます。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [IDBSchemaRowsetImpl クラス](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl クラス メンバー](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [SCHEMA_ENTRY](../../data/oledb/schema-entry.md)   
 [スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)