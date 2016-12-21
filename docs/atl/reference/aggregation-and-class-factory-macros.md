---
title: "集約とクラス ファクトリに関するマクロ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "集約 [C++], ATL マクロ"
  - "クラス ファクトリ, ATL マクロ"
ms.assetid: d99d379a-0eec-481f-8daa-252dac18f163
caps.latest.revision: 17
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 集約とクラス ファクトリに関するマクロ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

これらのマクロは集計を制御すると、クラス ファクトリを宣言する方法を示します。  
  
|||  
|-|-|  
|[DECLARE\_AGGREGATABLE](../Topic/DECLARE_AGGREGATABLE.md)|、オブジェクトが集約できることを宣言します \(既定値\)。|  
|[DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md)|クラス ファクトリを [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)の ATL の既定のクラス ファクトリであることを宣言します。|  
|[DECLARE\_CLASSFACTORY\_EX](../Topic/DECLARE_CLASSFACTORY_EX.md)|自分のクラス ファクトリ オブジェクトがクラス ファクトリであることを宣言します。|  
|[DECLARE\_CLASSFACTORY2](../Topic/DECLARE_CLASSFACTORY2.md)|[CComClassFactory2](../Topic/CComClassFactory2%20Class.md) がクラス ファクトリであることを宣言します。|  
|[DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md)|[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) がクラス ファクトリであることを宣言します。|  
|[DECLARE\_CLASSFACTORY\_SINGLETON](../Topic/DECLARE_CLASSFACTORY_SINGLETON.md)|[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) がクラス ファクトリであることを宣言します。|  
|[DECLARE\_GET\_CONTROLLING\_UNKNOWN](../Topic/DECLARE_GET_CONTROLLING_UNKNOWN.md)|`GetControllingUnknown` の仮想関数を宣言します。|  
|[DECLARE\_NOT\_AGGREGATABLE](../Topic/DECLARE_NOT_AGGREGATABLE.md)|、オブジェクトが集約できないことを宣言します。|  
|[DECLARE\_ONLY\_AGGREGATABLE](../Topic/DECLARE_ONLY_AGGREGATABLE.md)|、オブジェクトを集約する必要があることを宣言します。|  
|[DECLARE\_POLY\_AGGREGATABLE](../Topic/DECLARE_POLY_AGGREGATABLE.md)|外側の未知の値をチェックし、オブジェクトを、必要に応じて、aggregatable または not aggregatable 宣言します。|  
|[DECLARE\_PROTECT\_FINAL\_CONSTRUCT](../Topic/DECLARE_PROTECT_FINAL_CONSTRUCT.md)|内部オブジェクトの構築時に削除の外部オブジェクトを保護します。|  
|[DECLARE\_VIEW\_STATUS](../Topic/DECLARE_VIEW_STATUS.md)|コンテナーに **VIEWSTATUS** のフラグを指定します。|  
  
## 参照  
 [マクロ](../../atl/reference/atl-macros.md)