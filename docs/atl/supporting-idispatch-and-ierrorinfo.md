---
title: "IDispatch と IErrorInfo サポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IErrorInfo
- IDispatch
dev_langs: C++
helpviewer_keywords:
- ISupportErrorInfoImpl method
- IErrorInfo class suppor in ATL
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 7db2220f-319d-4ce9-9382-d340019f14f7
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b6d34f0d0616ae3980d1132b1f70812fe273d275
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="supporting-idispatch-and-ierrorinfo"></a>IDispatch と IErrorInfo をサポートします。
このテンプレート クラスを使用することができます[IDispatchImpl](../atl/reference/idispatchimpl-class.md)の既定の実装を提供する、`IDispatch Interface`オブジェクトの任意のデュアル インターフェイスの一部です。  
  
 オブジェクトで使用する場合、`IErrorInfo`エラーは、クライアントにバックアップし、オブジェクトがサポートする必要がありますを報告するインターフェイス、`ISupportErrorInfo Interface`インターフェイスです。 このテンプレート クラスは[ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md)オブジェクトにエラーが生成される 1 つのインターフェイスしかない場合は、これを実装する簡単な方法を提供します。  
  
## <a name="see-also"></a>関連項目  
 [ATL COM オブジェクトの基礎](../atl/fundamentals-of-atl-com-objects.md)

