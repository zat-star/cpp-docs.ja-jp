---
title: "ICommandImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ICommandImpl
dev_langs:
- C++
helpviewer_keywords:
- ICommandImpl class
ms.assetid: ef285fef-0d66-45e6-a762-b03357098e3b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 80cc82023131a23ebfea33c5264cf83fdafb1b36
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="icommandimpl-class"></a>ICommandImpl クラス
実装を提供、 [ICommand](https://msdn.microsoft.com/en-us/library/ms709737.aspx)インターフェイスです。  
  
## <a name="syntax"></a>構文

```cpp
template <class T, class CommandBase = ICommand>   
class ATL_NO_VTABLE ICommandImpl : public CommandBase  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`ICommandImpl`です。  
  
 `CommandBase`  
 コマンド インターフェイスです。 既定値は、`ICommand` です。  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[CancelExecution](../../data/oledb/icommandimpl-cancelexecution.md)|現在のコマンドの実行をキャンセルします。|  
|[キャンセル](../../data/oledb/icommandimpl-cancel.md)|現在のコマンドの実行をキャンセルします。|  
|[CreateRowset](../../data/oledb/icommandimpl-createrowset.md)|行セット オブジェクトを作成します。|  
|[実行します。](../../data/oledb/icommandimpl-execute.md)|コマンドを実行します。|  
|[GetDBSession](../../data/oledb/icommandimpl-getdbsession.md)|コマンドを作成したセッションにインターフェイス ポインターを返します。|  
|[ICommandImpl](../../data/oledb/icommandimpl-icommandimpl.md)|コンストラクターです。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|[m_bCancel](../../data/oledb/icommandimpl-m-bcancel.md)|コマンドをキャンセルするかどうかを示します。|  
|[m_bCancelWhenExecuting](../../data/oledb/icommandimpl-m-bcancelwhenexecuting.md)|コマンドを実行するときに取り消されますかどうかを示します。|  
|[m_bIsExecuting](../../data/oledb/icommandimpl-m-bisexecuting.md)|コマンドが実行されているかどうかを示します。|  
  
## <a name="remarks"></a>コメント  
 Command オブジェクトに必須のインターフェイスです。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)