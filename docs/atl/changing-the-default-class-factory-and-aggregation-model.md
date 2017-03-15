---
title: "既定のクラス ファクトリと集約モデルの変更 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "集約 [C++], 集約モデル"
  - "集約 [C++], 使用 (ATL を)"
  - "CComClassFactory クラス, 作成 (既定値を)"
  - "CComCoClass クラス, 既定のクラス ファクトリと集約モデル"
  - "クラス ファクトリ, 変更 (既定値を)"
  - "既定のクラス ファクトリ"
  - "既定のクラス ファクトリ, ATL"
  - "既定 [C++], 集約モデル (ATL の)"
  - "既定 [C++], クラス ファクトリ"
ms.assetid: 6e040e95-0f38-4839-8a8b-c9800dd47e8c
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 既定のクラス ファクトリと集約モデルの変更
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL を使用 [CComCoClass](../Topic/CComCoClass%20Class.md) は、オブジェクトの既定のクラス ファクトリと集約を定義するシミュレートします。  `CComCoClass` は、2 種類のマクロを指定します:  
  
-   [DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md) は [CComClassFactory](../atl/reference/ccomclassfactory-class.md)にクラス ファクトリを宣言します。  
  
-   [DECLARE\_AGGREGATABLE](../Topic/DECLARE_AGGREGATABLE.md) は、オブジェクトが集約できることを宣言します。  
  
 は、をクラス定義で別のマクロを指定することによってこれらの既定値をオーバーライドできます。  たとえば、`CComClassFactory`の代わりに [CComClassFactory2](../Topic/CComClassFactory2%20Class.md) を使用するには、[DECLARE\_CLASSFACTORY2](../Topic/DECLARE_CLASSFACTORY2.md) のマクロを指定する:  
  
 [!code-cpp[NVC_ATL_COM#2](../atl/codesnippet/CPP/changing-the-default-class-factory-and-aggregation-model_1.h)]  
  
 クラス ファクトリを定義する 2 つが他のマクロは [DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md) と [DECLARE\_CLASSFACTORY\_SINGLETON](../Topic/DECLARE_CLASSFACTORY_SINGLETON.md)です。  
  
 ATL は、既定の動作を実装するために `typedef` 機構を使用します。  たとえば、`DECLARE_AGGREGATABLE` のマクロは **\_CreatorClass**と呼ばれる ATL で参照される型を定義するために `typedef` を使用します。  派生クラスで、同じを使用して `typedef` が、シグネチャと、既定の動作をオーバーライドできます。を使用して ATL で基本クラスの `typedef` の結果として示すことに注意してください。  
  
## 参照  
 [ATL COM オブジェクトの基本事項](../atl/fundamentals-of-atl-com-objects.md)   
 [集約とクラス ファクトリに関するマクロ](../atl/reference/aggregation-and-class-factory-macros.md)