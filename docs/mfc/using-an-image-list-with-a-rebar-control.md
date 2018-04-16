---
title: "Rebar コントロールでイメージ リストの使い方 |Microsoft ドキュメント"
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
helpviewer_keywords:
- image lists [MFC], rebar controls
- rebar controls [MFC], image lists
ms.assetid: 1a5836ac-019a-46aa-8741-b35c3376b839
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: acb4ed52982f7ab23dac044eeacf315f45aa1232
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="using-an-image-list-with-a-rebar-control"></a>Rebar コントロールでのイメージ リストの使い方
各 rebar バンド含めることができます、特に、関連付けられているイメージ リストのイメージです。 次の手順では、rebar バンドでイメージを表示するために必要な手順について説明します。  
  
### <a name="to-display-images-in-a-rebar-band"></a>Rebar バンドでイメージを表示するには  
  
1.  イメージ リスト オブジェクトにアタッチ、rebar コントロールを呼び出すことによって[SetImageList](../mfc/reference/crebarctrl-class.md#setimagelist)、既存のイメージ リストにポインターを渡します。  
  
2.  変更、 **REBARBANDINFO** rebar バンドにイメージを代入する構造体。  
  
    -   設定、 **fMask**メンバー **RBBIM_IMAGE**、必要に応じて、追加のフラグを含めるには、ビットごとの OR 演算子を使用します。  
  
    -   設定、`iImage`を表示するイメージのイメージ リスト インデックスへのメンバーです。  
  
3.  サイズ、テキスト、および必要な情報を使用して、含まれる子ウィンドウのハンドルなど、残りのデータ メンバーを初期化します。  
  
4.  挿入 (イメージ) の新しいバンドへの呼び出しで[CReBarCtrl::InsertBand](../mfc/reference/crebarctrl-class.md#insertband)渡す、 **REBARBANDINFO**構造体。  
  
 次の例では、2 つのイメージを既存のイメージ リスト オブジェクトが rebar コントロール オブジェクトに接続されている前提としています (`m_wndReBar`)。 新しい rebar バンド (によって定義された`rbi`)、最初のイメージを含むへの呼び出しに追加された`InsertBand`:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#28](../mfc/codesnippet/cpp/using-an-image-list-with-a-rebar-control_1.cpp)]  
  
## <a name="see-also"></a>参照  
 [CReBarCtrl の使い方](../mfc/using-crebarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

