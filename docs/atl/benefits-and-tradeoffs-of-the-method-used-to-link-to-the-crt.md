---
title: "CRT へのリンクに使用する方法の利点とトレードオフ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: _ATL_MIN_CRT macro
ms.assetid: 49b485f7-9487-49e4-b12a-0f710b620e2b
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 244415a947918a836e8c4c67dbd18758ec40393c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt"></a>CRT へのリンクに使用する方法の利点とトレードオフ
プロジェクトは、動的または静的 CRT にリンクできます。 次の表は、利点とトレードオフに使用する方法の選択に関連するについて説明します。  
  
|メソッド|特長|トレードオフ|  
|------------|-------------|--------------|  
|CRT に静的にリンク<br /><br /> (**ランタイム ライブラリ**'éý'**シングル スレッド**)|イメージを実行するシステムでは、CRT DLL は必要はありません。|約 25 K のスタートアップ コードは、そのサイズを大幅に増やすこと、イメージに追加されます。|  
|CRT に動的にリンク<br /><br /> (**ランタイム ライブラリ**'éý'**マルチ スレッド**)|イメージでは小さすぎるため、CRT スタートアップ コードは必要ありません。|ただし、CRT DLL は、イメージを実行するシステム上でなければなりません。|  
  
 トピック[ATL プロジェクトで CRT にリンク](../atl/linking-to-the-crt-in-your-atl-project.md)で CRT にリンクする方法を選択する方法について説明します。  
  
## <a name="see-also"></a>参照  
 [ATL および C ランタイム コードによるプログラミング](../atl/programming-with-atl-and-c-run-time-code.md)   
 [Dll および Visual C ランタイム ライブラリの動作](../build/run-time-library-behavior.md)   
 [CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)

