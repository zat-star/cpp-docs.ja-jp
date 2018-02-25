---
title: "Icommandimpl::execute |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ICommandImpl::Execute
- ICommandImpl.Execute
dev_langs:
- C++
helpviewer_keywords:
- Execute method
ms.assetid: 033e0d4e-256b-4eed-9215-70e0bebb768c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8d4d24bbb7f7aad94210672ce9bbf0cc0c7d5414
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="icommandimplexecute"></a>ICommandImpl::Execute
コマンドを実行します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Execute(IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[icommand::execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="remarks"></a>コメント  
 要求された出力方向のインターフェイスは、この関数を作成する行セット オブジェクトから取得したインターフェイスになります。  
  
 **実行**呼び出し[CreateRowset](../../data/oledb/icommandimpl-createrowset.md)です。 1 つ以上の行セットを作成する、または別の行セットを作成するための独自の条件を提供する既定の実装をオーバーライドします。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [ICommandImpl クラス](../../data/oledb/icommandimpl-class.md)   
 [ICommandImpl::CancelExecution](../../data/oledb/icommandimpl-cancelexecution.md)