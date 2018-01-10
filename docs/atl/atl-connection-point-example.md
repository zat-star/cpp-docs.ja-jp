---
title: "ATL 接続ポイントの使用例 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- connection points [C++], examples
- examples [ATL]
ms.assetid: a49721b7-f308-43de-8868-f662a94bc81a
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cf59a8093568b96b5f2173d91ba52a6bfeb103b0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="atl-connection-point-example"></a>ATL 接続ポイントの例
この例は、サポートするオブジェクトを示しています。 [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638)アウトゴーイング インターフェイスとして。  
  
 [!code-cpp[NVC_ATL_Windowing#84](../atl/codesnippet/cpp/atl-connection-point-example_1.h)]  
  
 指定するときに`IPropertyNotifySink`、アウトゴーイング インターフェイスとクラスを使用して[IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md)の代わりに`IConnectionPointImpl`です。 例:  
  
 [!code-cpp[NVC_ATL_Windowing#85](../atl/codesnippet/cpp/atl-connection-point-example_2.h)]  
  
## <a name="see-also"></a>参照  
 [接続ポイント](../atl/atl-connection-points.md)

