---
title: "コレクション クラスのヘルパー | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.classes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コレクション クラス, ヘルパー関数"
  - "ConstructElements 関数"
  - "DestructElements 関数"
  - "ヘルパー関数コレクション クラス"
  - "SerializeElements 関数"
ms.assetid: bc3a2368-9edd-4748-9e6a-13cba79517ca
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# コレクション クラスのヘルパー
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

要素を比較し、コピー、およびシリアル化などの目的でコレクション クラス `CMap`、`CList`と `CArray` の template 宣言されたなグローバル ヘルパー関数。  `CMap`に基づいて、`CList`クラスの実装の一部として `CArray`マップ、表示されるように、配列に格納されているデータの種類に合わせてバージョンで必要としてこれらの関数をオーバーライドする必要があります。  `SerializeElements`などのオーバーライドのヘルパー関数については、[コレクション: タイプ セーフなコレクションを設定する方法](../../mfc/how-to-make-a-type-safe-collection.md)記事を参照してください。  **ConstructElements** と **DestructElements** が廃止されることに注意してください。  
  
 Microsoft Foundation Class ライブラリには、コレクション クラスをカスタマイズするために役立つ次のグローバル関数が用意されています。:  
  
### コレクション クラスのヘルパー  
  
|||  
|-|-|  
|[CompareElements](../Topic/CompareElements.md)|要素が同じかどうかを示します。|  
|[CopyElements](../Topic/CopyElements.md)|1 種類の配列から別のプロジェクトにコピーする要素。|  
|[DumpElements](../Topic/DumpElements.md)|ストリーム指向の診断を提供します。|  
|[HashKey](../Topic/HashKey.md)|ハッシュ キーを計算します。|  
|[SerializeElements](../Topic/SerializeElements.md)|ストアは、アーカイブに対して、要素を取得します。|  
  
## 参照  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)   
 [CMap クラス](../../mfc/reference/cmap-class.md)   
 [CList クラス](../../mfc/reference/clist-class.md)   
 [CArray クラス](../../mfc/reference/carray-class.md)