---
title: "COM マップに関するマクロ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COM インターフェイス, COM マップ マクロ"
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# COM マップに関するマクロ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

これらのマクロは COM インターフェイス マップを定義します。  
  
|||  
|-|-|  
|[BEGIN\_COM\_MAP](../Topic/BEGIN_COM_MAP.md)|COM インターフェイス マップ エントリの開始位置を示します。|  
|[COM\_INTERFACE\_ENTRY](../Topic/COM_INTERFACE_ENTRY%20Macros.md)|COM インターフェイス マップにインターフェイスを入力します。|  
|[COM\_INTERFACE\_ENTRY2](../Topic/COM_INTERFACE_ENTRY2.md)|2 つの継承元に関するあいまい性を解決します。|  
|[COM\_INTERFACE\_ENTRY\_IID](../Topic/COM_INTERFACE_ENTRY_IID.md)|このマクロは、インターフェイスを COM マップに入力し、インターフェイスの IID を指定するために使用します。|  
|[COM\_INTERFACE\_ENTRY2\_IID](../Topic/COM_INTERFACE_ENTRY2_IID.md)|[COM\_INTERFACE\_ENTRY2](../Topic/COM_INTERFACE_ENTRY2.md) と同じ機能を提供します。ただし、このマクロでは別の IID を指定できます。|  
|[COM\_INTERFACE\_ENTRY\_AGGREGATE](../Topic/COM_INTERFACE_ENTRY_AGGREGATE.md)|`iid` で識別されるインターフェイスが問い合わせを受けると、`COM_INTERFACE_ENTRY_AGGREGATE` は `punk` に転送します。|  
|[COM\_INTERFACE\_ENTRY\_AGGREGATE\_BLIND](../Topic/COM_INTERFACE_ENTRY_AGGREGATE_BLIND.md)|[COM\_INTERFACE\_ENTRY\_AGGREGATE](../Topic/COM_INTERFACE_ENTRY_AGGREGATE.md) と同じ機能を提供します。ただし、どのような IID についての問い合わせも `punk` に転送されます。|  
|[COM\_INTERFACE\_ENTRY\_AUTOAGGREGATE](../Topic/COM_INTERFACE_ENTRY_AUTOAGGREGATE.md)|[COM\_INTERFACE\_ENTRY\_AGGREGATE](../Topic/COM_INTERFACE_ENTRY_AGGREGATE.md) と同じ機能を提供します。ただし、`punk` が **NULL** の場合は、`clsid` で識別される集約を自動的に作成します。|  
|[COM\_INTERFACE\_ENTRY\_AUTOAGGREGATE\_BLIND](../Topic/COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND.md)|[COM\_INTERFACE\_ENTRY\_AUTOAGGREGATE](../Topic/COM_INTERFACE_ENTRY_AUTOAGGREGATE.md) と同じ機能を提供します。ただし、どのような IID についての問い合わせも `punk` に転送されます。また、`punk` が **NULL** の場合は、`clsid` で識別される集約を自動的に作成します。|  
|[COM\_INTERFACE\_ENTRY\_BREAK](../Topic/COM_INTERFACE_ENTRY_BREAK.md)|指定されたインターフェイスが問い合わせを受けると、プログラムが [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297) を呼び出すようにします。|  
|[COM\_INTERFACE\_ENTRY\_CACHED\_TEAR\_OFF](../Topic/COM_INTERFACE_ENTRY_CACHED_TEAR_OFF.md)|すべてのインスタンスについてインターフェイス固有のデータを保存します。|  
|[COM\_INTERFACE\_ENTRY\_TEAR\_OFF](../Topic/COM_INTERFACE_ENTRY_TEAR_OFF.md)|ティアオフ インターフェイスを公開します。|  
|[COM\_INTERFACE\_ENTRY\_CHAIN](../Topic/COM_INTERFACE_ENTRY_CHAIN.md)|処理が COM マップ内のこのエントリに達したときに、基本クラスの COM マップを処理します。|  
|[COM\_INTERFACE\_ENTRY\_FUNC](../Topic/COM_INTERFACE_ENTRY_FUNC.md)|ATL の `QueryInterface` ロジックにフックするための一般的な機構です。|  
|[COM\_INTERFACE\_ENTRY\_FUNC\_BLIND](../Topic/COM_INTERFACE_ENTRY_FUNC_BLIND.md)|[COM\_INTERFACE\_ENTRY\_FUNC](../Topic/COM_INTERFACE_ENTRY_FUNC.md) と同じ機能を提供します。ただし、IID について問い合わせると、`func` が呼び出されます。|  
|[COM\_INTERFACE\_ENTRY\_NOINTERFACE](../Topic/COM_INTERFACE_ENTRY_NOINTERFACE.md)|指定されたインターフェイスに対する問い合わせを受けると、**E\_NOINTERFACE** を返し、COM マップの処理を終了します。|  
|[END\_COM\_MAP](../Topic/END_COM_MAP.md)|COM インターフェイス マップ エントリの終了位置を示します。|  
  
## 参照  
 [マクロ](../../atl/reference/atl-macros.md)   
 [COM マップに関するグローバル関数](../../atl/reference/com-map-global-functions.md)