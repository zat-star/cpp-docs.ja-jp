---
title: "Ccommand::prepare |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCommand.Prepare
- CCommand::Prepare
- Prepare
dev_langs:
- C++
helpviewer_keywords:
- Prepare method
ms.assetid: f0e473fc-2f7a-4d29-96c2-1328dc21e702
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2055913394a1760c8b0012d53a11bfa0b1a0a1e6
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="ccommandprepare"></a>CCommand::Prepare
検証し、現在のコマンドを最適化できます。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT CCommandBase::Prepare(ULONG cExpectedRuns = 0) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 *cExpectedRuns*  
 [in]コマンドを実行する回数。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 このメソッドは、OLE DB メソッドをラップ[icommandprepare::prepare](https://msdn.microsoft.com/en-us/library/ms718370.aspx)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CCommand クラス](../../data/oledb/ccommand-class.md)