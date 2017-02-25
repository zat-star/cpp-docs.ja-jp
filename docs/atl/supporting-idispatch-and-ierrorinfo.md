---
title: "IDispatch と IErrorInfo のサポート | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IErrorInfo"
  - "IDispatch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDispatch クラス サポート ATL"
  - "IDispatchImpl クラス"
  - "IErrorInfo クラス サポート ATL"
  - "ISupportErrorInfoImpl メソッド"
ms.assetid: 7db2220f-319d-4ce9-9382-d340019f14f7
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# IDispatch と IErrorInfo のサポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

テンプレート クラス [IDispatchImpl](../atl/reference/idispatchimpl-class.md) を使用すると、オブジェクトのデュアル インターフェイスの `IDispatch Interface` 部分について、既定の実装を用意できます。  
  
 クライアントにエラーを報告するためにオブジェクトで `IErrorInfo` インターフェイスを使用する場合は、オブジェクトが `ISupportErrorInfo Interface` インターフェイスをサポートしている必要があります。  オブジェクトでエラーを生成するインターフェイスが 1 つだけである場合は、テンプレート クラス [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) を使用すると、**ISupportErrorInfo** インターフェイスを簡単に実装できます。  
  
## 参照  
 [ATL COM オブジェクトの基本事項](../atl/fundamentals-of-atl-com-objects.md)