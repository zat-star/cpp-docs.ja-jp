---
title: "現在の時刻: 汎用クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- time, setting current
- current time, CTime object
- procedures, getting current time
- initializing objects, with the current time
- time, getting current
ms.assetid: c39e6775-6a92-4b27-95a7-5c86ed371d8a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a6c43ffd60d837bdd8f061057cf1c36340b6e6af
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="current-time-general-purpose-classes"></a>現在の時刻: 汎用クラス
次の手順を作成する方法を示しています、`CTime`オブジェクトを現在の時刻に初期化します。  
  
#### <a name="to-get-the-current-time"></a>現在の時刻を取得するには  
  
1.  割り当てる、`CTime`オブジェクトに、次のようにします。  
  
     [!code-cpp[NVC_ATLMFC_Utilities#171](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_1.cpp)]  
  
    > [!NOTE]
    >  初期化されていない`CTime`オブジェクトが有効な時刻に初期化されていません。  
  
2.  呼び出す、`CTime::GetCurrentTime`オペレーティング システムから現在の時刻を取得します。 この関数を返します、`CTime`の値を設定するために使用できるオブジェクト`CTime`、次のようにします。  
  
     [!code-cpp[NVC_ATLMFC_Utilities#172](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_2.cpp)]  
  
     `GetCurrentTime`から静的メンバー関数は、`CTime`クラス、その名前をクラスと、スコープ解決演算子の名前を修飾する必要があります (`::`)、`CTime::GetCurrentTime()`です。  
  
 もちろん、2 つの手順に従って以前結合できます、単一のプログラム ステートメントに次のように。  
  
 [!code-cpp[NVC_ATLMFC_Utilities#173](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_3.cpp)]  
  
## <a name="see-also"></a>参照  
 [日付と時刻: 汎用クラス](../atl-mfc-shared/date-and-time-general-purpose-classes.md)



