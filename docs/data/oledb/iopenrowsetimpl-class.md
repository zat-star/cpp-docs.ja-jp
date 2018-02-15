---
title: "IOpenRowsetImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IOpenRowsetImpl
dev_langs:
- C++
helpviewer_keywords:
- IOpenRowsetImpl class
ms.assetid: d259cedc-1db4-41cf-bc9f-5030907ab486
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: aa59f1a4f8b599cc74cbe824815c65b60e7b6af1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="iopenrowsetimpl-class"></a>IOpenRowsetImpl クラス
実装を提供、`IOpenRowset`インターフェイスです。  
  
## <a name="syntax"></a>構文

```cpp
template <class SessionClass>  
class IOpenRowsetImpl : public IOpenRowset  
```  
  
#### <a name="parameters"></a>パラメーター  
 `SessionClass`  
 派生したクラス、`IOpenRowsetImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[CreateRowset](../../data/oledb/iopenrowsetimpl-createrowset.md)|行セット オブジェクトを作成します。 ユーザーが直接呼び出されません。|  
|[OpenRowset](../../data/oledb/iopenrowsetimpl-openrowset.md)|開き、単一のベース テーブルまたはインデックスからすべての行を含む行セットを返します。 (にない ATLDB です。H)|  
  
## <a name="remarks"></a>コメント  
 [IOpenRowset](https://msdn.microsoft.com/en-us/library/ms716946.aspx)セッション オブジェクトの必須インターフェイスです。 それが開き、単一のベース テーブルまたはインデックスからすべての行を含む行セットを返します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)