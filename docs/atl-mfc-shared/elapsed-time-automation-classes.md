---
title: "経過時間: オートメーション クラス |Microsoft ドキュメント"
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
- elapsed time, calculating in Automation
- Automation classes, elapsed time
- time, elapsed
- intervals, date and time
- calculations, date and time
ms.assetid: 26b34b37-c10e-4b91-82c3-1dc5ffb5361f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 51479f73112ed80ee981f3919fd3941d1eb0c8f2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="elapsed-time-automation-classes"></a>経過時間: オートメーション クラス
この手順は、2 つの差を計算する方法を示しています。`CTime`オブジェクトを取得、`CTimeSpan`結果。  
  
#### <a name="to-calculate-elapsed-time"></a>経過時間を計算するには  
  
1.  2 つ作成`COleDateTime`オブジェクト。  
  
2.  いずれかの設定、`COleDateTime`を現在の時刻のオブジェクト。  
  
3.  時間のかかるタスクを実行します。  
  
4.  他の設定`COleDateTime`を現在の時刻のオブジェクト。  
  
5.  2 つの時刻の差を取得します。  
  
     [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/cpp/elapsed-time-automation-classes_1.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [日付と時刻: オートメーション サポート](../atl-mfc-shared/date-and-time-automation-support.md)

