---
title: 4.1 OMP_SCHEDULE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: d0dce411-2351-4ee9-a1cc-c0322a58b65c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 330e5ea576e3cd779a7c17c21d00b6459f5e7043
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2018
---
# <a name="41-ompschedule"></a>4.1 OMP_SCHEDULE
**OMP_SCHEDULE**にのみ適用されます**の**と**の並列**をスケジュールの種類を持つディレクティブ**ランタイム**です。 このようなループのスケジュールの種類とチャンク サイズは、認識されているスケジュールの種類のいずれかをする、省略可能なこの環境変数を設定して実行時に設定できます*chunk_size*です。  
  
 **の**と**の並列**型を持つスケジュール以外のディレクティブ**ランタイム**、 **OMP_SCHEDULE**は無視されます。 この環境変数の既定値は、実装定義です。 場合、省略可能な*chunk_size*が設定されている値は正の値である必要があります。 場合*chunk_size*設定、値 1 が想定されている以外の場合、**静的**スケジュールします。 **静的**スケジュール、既定のチャンク サイズは、ループのイテレーション領域をループに適用されるスレッドの数で割った値に設定されています。  
  
 例:  
  
```  
setenv OMP_SCHEDULE "guided,4"  
setenv OMP_SCHEDULE "dynamic"  
```  
  
## <a name="cross-references"></a>クロス リファレンス  
  
-   **デ**ィレクティブを参照してください[セクション 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) [11] ページ。  
  
-   **並列**ディレクティブを参照してください[セクション 2.5.1](../../parallel/openmp/2-5-1-parallel-for-construct.md) 16 ページです。