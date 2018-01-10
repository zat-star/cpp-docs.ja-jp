---
title: "Idbschemarowsetimpl::getschemas |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IDBSchemaRowsetImpl::GetSchemas
- GetSchemas
- IDBSchemaRowsetImpl<SessionClass>::GetSchemas
- ATL.IDBSchemaRowsetImpl.GetSchemas
- ATL::IDBSchemaRowsetImpl<SessionClass>::GetSchemas
- IDBSchemaRowsetImpl.GetSchemas
- IDBSchemaRowsetImpl::GetSchemas
dev_langs: C++
helpviewer_keywords: GetSchemas method
ms.assetid: fbe725a6-3acd-45f8-bcaf-10a6c1239cd2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ce07c59eb9dd806d2f297591e8f3b389b3f4ce54
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="idbschemarowsetimplgetschemas"></a>IDBSchemaRowsetImpl::GetSchemas
[IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)でアクセスできるスキーマ行セットの一覧を返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      STDMETHOD ( GetSchema s )(  
   ULONG * pcSchemas,  
   GUID ** prgSchemas,  
   ULONG** prgRest  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *pcSchemas*  
 [出力] スキーマの数が格納される **ULONG** へのポインター。  
  
 *prgSchemas*  
 [出力] スキーマ行セット GUID の配列へのポインターが格納される GUID の配列へのポインター。  
  
 *prgRest*  
 [出力] 制限配列が格納される **ULONG**の配列へのポインター。  
  
## <a name="remarks"></a>コメント  
 このメソッドは、プロバイダーによってサポートされるすべてのスキーマ行セットの配列を返します。 参照してください[idbschemarowset::getschemas](https://msdn.microsoft.com/en-us/library/ms719605.aspx) Windows SDK にします。  
  
 この関数の実装では、セッション クラスでスキーマ マップを持っている必要があります。 スキーマ マップ情報を使用して、マップ内のスキーマの GUID の配列で応答します。 これは、プロバイダーによってサポートされるスキーマを表します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [IDBSchemaRowsetImpl クラス](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl クラス メンバー](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [Idbschemarowsetimpl::getrowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)   
 [Idbschemarowset::getrowset](https://msdn.microsoft.com/en-us/library/ms722634.aspx)   
 [スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)