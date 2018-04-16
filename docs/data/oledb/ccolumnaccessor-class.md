---
title: "CColumnAccessor クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CColumnAccessor
- ATL::CColumnAccessor
- ATL.CColumnAccessor
dev_langs:
- C++
helpviewer_keywords:
- CColumnAccessor class
ms.assetid: 6ce1e67f-6a20-490d-9326-c168b43eee7e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fa03f7ee652ee176c7333ac5ef4e264b7f4d5cf8
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="ccolumnaccessor-class"></a>CColumnAccessor クラス
挿入されたコンシューマー コードが生成されます。  
  
## <a name="syntax"></a>構文

```cpp
class CColumnAccessor : public CAccessorBase  
```  
  
## <a name="remarks"></a>コメント  
 挿入されたコードでは、すべての列を別のアクセサーとしてバインドされます。 このクラスは、挿入されたコードで使用されていることに注意してください (たとえば、生じる場合、デバッグするときに) が、通常しないか、そのメソッドを直接使用します。  
  
 `CColumnAccessor` 他のアクセサー クラスのメソッドへの機能で対応しているそれぞれの次のスタブ メソッドを実装します。  
  
-   `CColumnAccessor` コンス トラクターです。インスタンスを作成し、初期化、`CColumnAccessor`オブジェクト。  
  
-   `CreateAccessor` 列バインド構造体のメモリを割り当て、列のデータ メンバーを初期化します。  
  
-   **BindColumns**アクセサーに列をバインドします。  
  
-   **SetParameterBuffer**パラメーターのバッファーを割り当てます。  
  
-   `AddParameter` パラメーターのエントリの構造体をパラメーターの入力を追加します。  
  
-   **HasOutputColumns**アクセサーに出力列があるかどうかを決定  
  
-   **HasParameters**アクセサーがパラメーターを持つかどうかを決定します。  
  
-   `BindParameters` 列に作成されたパラメーターをバインドします。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)