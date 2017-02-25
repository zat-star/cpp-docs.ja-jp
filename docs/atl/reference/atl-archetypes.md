---
title: "ATL の原型 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "archetype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, 原型"
ms.assetid: 809fb0af-c0f4-4cc0-b5bc-afe3de5d9722
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# ATL の原型
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このコンテキストでは、*元は*、データ メンバー メソッド、静的関数、および typedef、またはそのほかの機能のコレクションを提供する概念的なクラスです。  元は、特定の概念を表すクラスを作成または操作に必要なセマンティクスの説明が含まれます。  同じ機能を提供して、を模倣クラスは、同じ概念を具体化および、使用できる場所にも使用できます。  
  
 は、テンプレート パラメーターの有効値の機能を説明するための C\+\+ に便利です。  テンプレートのデザイナーは、テンプレート パラメーターの必要で、十分な機能の明示的な要素を、コンパイラは、ビルド時には構文の要件を実装しますが、テンプレートのユーザーは、ドキュメントが意味について説明し、入力されなければ、とクラス間の関係を明確に有効にする必要があります。  
  
 標準 C\+\+ ライブラリの元の例は、反復子とコンテナーの種類です。  これらのトピックでは、[反復子の規則](../Topic/Iterators.md) と [STL コンテナー](../../standard-library/stl-containers.md)で説明します。  
  
 ATL Server では、次の原型を定義します:  
  
|名前|説明|  
|--------|--------|  
|[ワーカー元](../../atl/reference/worker-archetype.md)|*ワーカー* 元に準拠するクラスはスレッド プールにキューイング プロセス作業項目にコードを提供します。|  
  
## 参照  
 [概念](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)