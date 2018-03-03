---
title: "IDispatch と IErrorInfo サポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IErrorInfo
- IDispatch
dev_langs:
- C++
helpviewer_keywords:
- ISupportErrorInfoImpl method
- IErrorInfo class suppor in ATL
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 7db2220f-319d-4ce9-9382-d340019f14f7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f39db3e844df884e8e95352bed2a078b01beede8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="supporting-idispatch-and-ierrorinfo"></a>IDispatch と IErrorInfo をサポートします。
このテンプレート クラスを使用することができます[IDispatchImpl](../atl/reference/idispatchimpl-class.md)の既定の実装を提供する、`IDispatch Interface`オブジェクトの任意のデュアル インターフェイスの一部です。  
  
 オブジェクトで使用する場合、`IErrorInfo`エラーは、クライアントにバックアップし、オブジェクトがサポートする必要がありますを報告するインターフェイス、`ISupportErrorInfo Interface`インターフェイスです。 このテンプレート クラスは[ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md)オブジェクトにエラーが生成される 1 つのインターフェイスしかない場合は、これを実装する簡単な方法を提供します。  
  
## <a name="see-also"></a>参照  
 [ATL COM オブジェクトの基礎](../atl/fundamentals-of-atl-com-objects.md)

