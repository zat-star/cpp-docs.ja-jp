---
title: "ExitInstance メンバー関数は、|Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
dev_langs:
- C++
helpviewer_keywords:
- programs [MFC], terminating
- CWinApp class [MFC], ExitInstance
- ExitInstance method [MFC]
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 99898a5e80c3f487c7f53fe81d13d3d1eb55ebd5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="exitinstance-member-function"></a>ExitInstance メンバー関数
[ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance)クラスのメンバー関数[CWinApp](../mfc/reference/cwinapp-class.md)関数が呼び出されるアプリケーションのコピーによって終了した、通常、ユーザー、アプリケーションを終了します。  
  
 オーバーライド`ExitInstance`グラフィック デバイス インターフェイス (GDI) のリソースの解放や、プログラムの実行時に使用されるメモリを解放するなどの特別なクリーンアップ処理を必要があるかどうか。 ただし、ドキュメントやビューなど、標準的なアイテムのクリーンアップは、これらのオブジェクトに固有のクリーンアップを行うためのオーバーライド可能な他の関数と、フレームワークによって提供されます。  
  
## <a name="see-also"></a>参照  
 [CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)
