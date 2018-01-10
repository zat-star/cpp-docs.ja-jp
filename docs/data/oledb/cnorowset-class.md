---
title: "CNoRowset クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CNoRowset
- ATL::CNoRowset<TAccessor>
- CNoRowset
- ATL.CNoRowset<TAccessor>
- ATL::CNoRowset
dev_langs: C++
helpviewer_keywords: CNoRowset class
ms.assetid: 55c6c7a4-9e3a-4775-a2dd-c8b333012fa6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 901d857b5095dd882a368b9a87e8a7d38d20bc42
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cnorowset-class"></a>CNoRowset クラス
テンプレート引数として使用できます (`TRowset`) の[CCommand](../../data/oledb/ccommand-class.md)または[CTable](../../data/oledb/ctable-class.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
template <class TAccessor = CAccessorBase>  
class CNoRowset  
```  
  
#### <a name="parameters"></a>パラメーター  
 `TAccessor`  
 アクセサー クラス。 既定値は、`CAccessorBase` です。  
  
## <a name="remarks"></a>コメント  
 使用して`CNoRowset`コマンドが行セットを返さない場合は、テンプレート引数として。  
  
 `CNoRowset`その他のアクセサー クラスのメソッドに対応しているそれぞれの次のスタブ メソッドを実装します。  
  
-   **BindFinished** -バインドが完了したことを示します (返します`S_OK`)。  
  
-   **閉じる**-行と、現在の IRowset インターフェイスを解放します。  
  
-   `GetIID`-接続ポイントのインターフェイス ID を取得します。  
  
-   **GetInterface**のインターフェイスを取得します。  
  
-   `GetInterfacePtr`-カプセル化されたインターフェイス ポインターを取得します。  
  
-   **SetAccessor** -アクセサーへのポインターを設定します。  
  
-   **SetupOptionalRowsetInterfaces** -行セットの省略可能なインターフェイスを設定します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)