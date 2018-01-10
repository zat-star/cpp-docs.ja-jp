---
title: "Ccommand::getnextresult |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CCommand::GetNextResult
- CCommand::GetNextResult
- GetNextResult
- CCommand.GetNextResult
- ATL.CCommand.GetNextResult
dev_langs: C++
helpviewer_keywords: GetNextResult method
ms.assetid: 63df9b55-9490-45c4-934a-879c5c2725d8
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a3bf105f0c85d831d1a8e4bb0048a1385e6275da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ccommandgetnextresult"></a>CCommand::GetNextResult
次の結果がある場合のセットをフェッチします。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT GetNextResult(  
   DBROWCOUNT* pulRowsAffected,  
   bool bBind = true   
) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 *pulRowsAffected*  
 [入力/出力]コマンドによって影響を受ける行の数が返されるメモリへのポインター。  
  
 `bBind`  
 [in]コマンドを実行中の後に自動的にバインドするかどうかを指定します。 既定値は**true**、それが原因で、コマンドを自動的に連結されます。 設定`bBind`に**false**手動でバインドできるように、コマンドの自動に連結します。 (手動バインディングは、OLAP のユーザーに特に関心があるは) です。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 結果セットが既にフェッチされる場合、この関数は前の結果セットを解放し、列をバインド解除します。 場合`bBind`は**true**、新しい列をバインドします。  
  
 複数の結果を設定して指定した場合にのみ、この関数を呼び出す必要があります、`CCommand`テンプレート パラメーター *TMultiple*=`CMultipleResults`です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CCommand クラス](../../data/oledb/ccommand-class.md)