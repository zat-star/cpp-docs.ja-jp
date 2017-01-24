---
title: "集約オブジェクトの作成 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "集約オブジェクト [C++], 作成"
  - "集約 [C++], 作成 (集約オブジェクトを)"
ms.assetid: fc29d7aa-fd53-4276-9c2f-37379f71b179
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 集約オブジェクトの作成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

集計は、内部オブジェクトに外部オブジェクトの **IUnknown** へのポインターを提供する **IUnknown** の呼び出しに委任します。  
  
### 集約オブジェクトを作成するには  
  
1.  **IUnknown** のポインターをクラスに追加し、オブジェクトのコンストラクター **null** で要素を初期化します。  
  
2.  集計を作成するためにオーバーライド [FinalConstruct](../Topic/CComObjectRootEx::FinalConstruct.md)。  
  
3.  2 番目のパラメーターとして定義される [COM\_INTERFACE\_ENTRY\_AGGREGATE](../Topic/COM_INTERFACE_ENTRY_AGGREGATE.md) のマクロに対して手順 1 で **IUnknown** のポインターを使用します。  
  
4.  **IUnknown** のポインターを解放するためにオーバーライド [FinalRelease](../Topic/CComObjectRootEx::FinalRelease.md)。  
  
> [!NOTE]
>  `FinalConstruct`中に集約オブジェクトのインターフェイスを使用して解放する場合、クラス オブジェクトの定義に [DECLARE\_PROTECT\_FINAL\_CONSTRUCT](../Topic/DECLARE_PROTECT_FINAL_CONSTRUCT.md) のマクロを追加する必要があります。  
  
## 参照  
 [ATL COM オブジェクトの基本事項](../atl/fundamentals-of-atl-com-objects.md)