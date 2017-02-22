---
title: "基本クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "基本クラス"
  - "基本クラス, virtual"
  - "派生クラス, 複数の基本"
  - "継承, 複数の"
  - "多重継承, 基本クラス"
  - "仮想基本クラス"
ms.assetid: 6e6d54d0-6f21-4a16-9103-22935d98f596
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 基本クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

継承プロセスは、基底クラス、および派生クラスによって追加された新しいメンバーで構成される、新しい派生クラスを作成します。  多重継承では、同じ基底クラスが複数の派生クラスの一部になる継承グラフが生成される場合があります。  次の図は、こうしたグラフを示しています。  
  
 ![基底クラスの複数インスタンス](../cpp/media/vc38xn1.png "vc38XN1")  
単一基底クラスの複数インスタンス  
  
 図では、`CollectibleString` と `CollectibleSortable` のコンポーネントのイメージ表現が表示されます。  ただし、基底クラス `Collectible` は、`CollectibleSortableString` パスと `CollectibleString` パスを経由した `CollectibleSortable` 内にあります。  この冗長性を取り除くために、継承されるときにこのようなクラスを仮想基底クラスとして宣言できます。  
  
 仮想基底クラスの宣言の詳細、および仮想基底クラスを持つオブジェクトの作成方法については、「[仮想基底クラス](../Topic/Virtual%20Base%20Classes.md)」を参照してください。  
  
## 参照  
 [派生クラスの概要](../misc/overview-of-derived-classes.md)