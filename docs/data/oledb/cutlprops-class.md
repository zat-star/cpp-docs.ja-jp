---
title: "CUtlProps クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CUtlProps
dev_langs: C++
helpviewer_keywords: CUtlProps class
ms.assetid: bb525178-765c-4e23-a110-c0fd70c05437
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 75e92f48729d0aae9f85cc7b7c5c97e4778f96a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cutlprops-class"></a>CUtlProps クラス
プロパティの OLE DB インターフェイスのさまざまなプロパティを実装する (たとえば、 `IDBProperties`、 `IDBProperties`、および`IRowsetInfo`)。  
  
## <a name="syntax"></a>構文  
  
```  
template < class T >  
class ATL_NO_VTABLE CUtlProps : public CUtlPropsBase  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 クラスを含む、`BEGIN_PROPSET_MAP`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[GetPropValue](../../data/oledb/cutlprops-getpropvalue.md)|プロパティのセットからプロパティを取得します。|  
|[IsValidValue](../../data/oledb/cutlprops-isvalidvalue.md)|プロパティを設定する前に、値を検証するために使用します。|  
|[OnInterfaceRequested](../../data/oledb/cutlprops-oninterfacerequested.md)|コンシューマーは、オブジェクト作成インターフェイスのメソッドを呼び出すときは、省略可能なインターフェイスの要求を処理します。|  
|[OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)|チェーンされたプロパティを処理するプロパティを設定した後に呼び出されます。|  
|[SetPropValue](../../data/oledb/cutlprops-setpropvalue.md)|プロパティ セットのプロパティを設定します。|  
  
## <a name="remarks"></a>コメント  
 このクラスのほとんどは、実装の詳細です。  
  
 `CUtlProps`内部的にプロパティを設定するための 2 つのメンバーが含まれています: [GetPropValue](../../data/oledb/cutlprops-getpropvalue.md)と[SetPropValue](../../data/oledb/cutlprops-setpropvalue.md)です。  
  
 プロパティ セットのマップで使用されるマクロの詳細については、次を参照してください。 [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)と[END_PROPSET_MAP](../../data/oledb/end-propset-map.md)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)