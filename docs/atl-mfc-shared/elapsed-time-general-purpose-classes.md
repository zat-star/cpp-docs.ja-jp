---
title: "汎用クラスでの経過時間: |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- adding dates
- calculating dates and times
- dates, calculating intervals
- elapsed time, calculating
- elapsed time
- time, elapsed
- intervals, date and time
- calculations, date and time
ms.assetid: e5c5d3d2-ce1d-409e-875c-98848434e716
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 51eea60669fb7ad35525d65013ffc8420649349b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="elapsed-time-general-purpose-classes"></a>汎用クラスでの経過時間:
次の手順は、2 つの差を計算する方法を示しています。`CTime`オブジェクトを取得、`CTimeSpan`結果。  
  
#### <a name="to-calculate-elapsed-time"></a>経過時間を計算するには  
  
1.  使用して、`CTime`と`CTimeSpan`経過時間を次のように計算するオブジェクト。  
  
     [!code-cpp[NVC_ATLMFC_Utilities#174](../atl-mfc-shared/codesnippet/cpp/elapsed-time-general-purpose-classes_1.cpp)]  
  
     計算した後`elapsedTime`のメンバー関数を使用する`CTimeSpan`を経過した時間の値のコンポーネントを抽出します。  
  
## <a name="see-also"></a>参照  
 [日付と時刻: 汎用クラス](../atl-mfc-shared/date-and-time-general-purpose-classes.md)

