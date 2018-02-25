---
title: CUtlProps::OnInterfaceRequested | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUtlProps
dev_langs:
- C++
helpviewer_keywords:
- OnInterfaceRequested method
ms.assetid: a5e1a879-cff3-4e01-b902-2249a152984f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cdac2b6069e5f72534a304794b65723bef8ceb47
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="cutlpropsoninterfacerequested"></a>CUtlProps::OnInterfaceRequested
コンシューマー メソッドを呼び出すと、オブジェクトのいずれかで作成インターフェイスは、省略可能なインターフェイスの要求を処理します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      virtual HRESULT CUtlPropsBase::OnInterfaceRequested(REFIID riid);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `riid`  
 [in]要求されたインターフェイスの IID です。 詳細については、の説明を参照して、`riid`のパラメーター`ICommand::Execute`で、 *OLE DB プログラマーズ リファレンス*(で、 *MDAC SDK*)。  
  
## <a name="remarks"></a>コメント  
 **OnInterfaceRequested**コンシューマー メソッドを呼び出すと、オブジェクトのいずれかで作成インターフェイスは、省略可能なインターフェイスのコンシューマーの要求を処理 (など**IDBCreateSession**、 **IDBCreateCommand**、 `IOpenRowset`、または`ICommand`)。 要求されたインターフェイスに対応する OLE DB プロパティを設定します。 たとえば、コンシューマーが要求する**IID_IRowsetLocate**、 **OnInterfaceRequested**設定、 **DBPROP_IRowsetLocate**インターフェイスです。 これにより行セットの作成時に適切な状態を維持します。  
  
 このメソッドは、コンシューマーが呼び出したときに**iopenrowset::openrowset**または`ICommand::Execute`です。  
  
 プロバイダーがそのインターフェイスに関連付けられているプロパティに設定する場合は、コンシューマーは、オブジェクトを開くし、省略可能なインターフェイスを要求、`VARIANT_TRUE`です。 プロパティに固有の処理を許可する**OnInterfaceRequested**プロバイダーの前に呼び出されます**Execute**メソッドが呼び出されます。 既定では、 **OnInterfaceRequested**次のインターフェイスを処理します。  
  
-   `IRowsetLocate`  
  
-   `IRowsetChange`  
  
-   `IRowsetUpdate`  
  
-   **IConnectionPointContainer**  
  
-   `IRowsetScroll`  
  
 その他のインターフェイスを処理する場合は、関数を処理する、データ ソース、セッション、コマンド、または行セット クラスでは、この関数をオーバーライドします。 上書きは、プロパティを設定すると、連鎖プロパティも設定されることを確認するインターフェイスを通常の設定/取得するプロパティを通過する必要があります (を参照してください[OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md))。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [CUtlProps クラス](../../data/oledb/cutlprops-class.md)