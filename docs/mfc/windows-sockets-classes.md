---
title: "Windows Sockets クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.net
dev_langs: C++
helpviewer_keywords:
- sockets classes [MFC]
- Windows Sockets [MFC], classes
ms.assetid: 58b9ab8d-9e44-4db3-8265-e04e713d2e9a
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cbfcd2d1009f98565719fb514ce8c804092573da
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="windows-sockets-classes"></a>Windows Sockets クラス
Windows ソケットは、2 台のコンピューター間の通信にネットワーク プロトコルに依存しない方法を提供します。 これらのソケットは同期していることができます (プログラムは、通信が終了するまで待機する) または非同期 (プログラムは、通信が起こっている間に実行が続行されます)。  
  
 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)  
 Thin ラッパーで Windows ソケット API をカプセル化します。  
  
 [CSocket](../mfc/reference/csocket-class.md)  
 派生した上位レベルの抽象化`CAsyncSocket`です。 同期的に動作します。  
  
 [CSocketFile](../mfc/reference/csocketfile-class.md)  
 提供、 `CFile` Windows ソケットへのインターフェイスです。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../mfc/class-library-overview.md)

