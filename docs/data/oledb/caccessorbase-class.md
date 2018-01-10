---
title: "CAccessorBase クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CAccessorBase
dev_langs: C++
helpviewer_keywords: CAccessorBase class
ms.assetid: 389b65be-11ca-4ae0-9290-60c621c4982b
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9b7c12430c4e7a6872afd46e72e93a29a3189333
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="caccessorbase-class"></a>CAccessorBase クラス
OLE DB テンプレートのすべてのアクセサーは、このクラスから派生します。 `CAccessorBase`複数のアクセサーを管理する 1 つの行セットを使用できます。 また、両方のパラメーターと出力列のバインドを提供します。  
  
## <a name="syntax"></a>構文  
  
```  
// Replace with syntax  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[閉じる](../../data/oledb/caccessorbase-close.md)|アクセサーを閉じます。|  
|[GetHAccessor](../../data/oledb/caccessorbase-gethaccessor.md)|アクセサー ハンドルを取得します。|  
|[GetNumAccessors](../../data/oledb/caccessorbase-getnumaccessors.md)|クラスで作成したアクセサーの数を取得します。|  
|[IsAutoAccessor](../../data/oledb/caccessorbase-isautoaccessor.md)|指定されたアクセサーが自動かどうかをテストします。|  
|[ReleaseAccessors](../../data/oledb/caccessorbase-releaseaccessors.md)|アクセサーを解放します。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)