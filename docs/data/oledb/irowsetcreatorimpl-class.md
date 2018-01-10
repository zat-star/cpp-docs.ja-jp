---
title: "IRowsetCreatorImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IRowsetCreatorImpl
- ATL.IRowsetCreatorImpl
- ATL::IRowsetCreatorImpl<T>
- ATL.IRowsetCreatorImpl<T>
- IRowsetCreatorImpl
dev_langs: C++
helpviewer_keywords: IRowsetCreatorImpl class
ms.assetid: 92cc950f-7978-4754-8d9a-defa63867d82
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3a1a1c17ad9469ff31b5520ffadb3349f86827ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetcreatorimpl-class"></a>IRowsetCreatorImpl クラス
同じ機能を実行`IObjectWithSite`OLE DB プロパティこともできますが、 **DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS**です。  
  
## <a name="syntax"></a>構文  
  
```  
template < class T >  
class ATL_NO_VTABLE IRowsetCreatorImpl   
   : public IObjectWithSiteImpl< T >  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス**IRowsetCreator**です。  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[SetSite](../../data/oledb/irowsetcreatorimpl-setsite.md)|行セット オブジェクトを含むサイトを設定します。|  
  
## <a name="remarks"></a>コメント  
 このクラスから継承[IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765)と上書き[IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869)です。 プロバイダー コマンドまたはセッション オブジェクトは、行セットを作成するときに呼び出す`QueryInterface`を探して、行セット オブジェクト`IObjectWithSite`と呼び出し`SetSite`行セット オブジェクトの引き渡し**IUnkown**サイト インターフェイスとしてインターフェイスです。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)