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
ms.openlocfilehash: 5fe6a018668f40c632e0ff980499afb7e60de8ea
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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
  
## <a name="see-also"></a>関連項目  
 [コレクションと列挙子](../atl/atl-collections-and-enumerators.md)

