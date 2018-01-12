---
title: "ATL コレクションと列挙子クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- enumerators, ATL classes
- collection classes, ATL
ms.assetid: 6818db73-7094-48d8-a0ca-18147beec362
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8b172c0d3a6f453ec0d5f7b5bb3584ebf2f5140e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="atl-collection-and-enumerator-classes"></a>ATL コレクションと列挙子クラス
ATL は、コレクションと列挙子を実装するのに役立つ次のクラスを提供します。  
  
|クラス|説明|  
|-----------|-----------------|  
|[単独](../atl/reference/icollectiononstlimpl-class.md)|コレクション インターフェイスの実装|  
|[つまり](../atl/reference/ienumonstlimpl-class.md)|列挙子インターフェイスの実装 (C++ 標準ライブラリと互換性のあるコンテナーに格納されたデータを想定)|  
|[CComEnumImpl](../atl/reference/ccomenumimpl-class.md)|列挙子インターフェイスの実装 (配列に格納されたデータを想定)|  
|[CComEnumOnSTL](../atl/reference/ccomenumonstl-class.md)|列挙子オブジェクトの実装 (を使用して`IEnumOnSTLImpl`)|  
|[上記](../atl/reference/ccomenum-class.md)|列挙子オブジェクトの実装 (を使用して`CComEnumImpl`)|  
|[_Copy](../atl/atl-copy-policy-classes.md)|Policy クラスをコピーします。|  
|[_CopyInterface](../atl/atl-copy-policy-classes.md)|Policy クラスをコピーします。|  
|[CAdapt](../atl/reference/cadapt-class.md)|アダプター クラス (非表示に**演算子 (& a)**許可`CComPtr`、 `CComQIPtr`、および`CComBSTR`C++ 標準ライブラリのコンテナーに格納される)|  
  
## <a name="see-also"></a>参照  
 [コレクションと列挙子](../atl/atl-collections-and-enumerators.md)

