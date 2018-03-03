---
title: "Windows Sockets クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.net
dev_langs:
- C++
helpviewer_keywords:
- sockets classes [MFC]
- Windows Sockets [MFC], classes
ms.assetid: 58b9ab8d-9e44-4db3-8265-e04e713d2e9a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cea7690c9d1f754006a38c793fcd9608747c13b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="windows-sockets-classes"></a>Windows Sockets クラス
Windows ソケットは、2 台のコンピューター間の通信にネットワーク プロトコルに依存しない方法を提供します。 これらのソケットは同期していることができます (プログラムは、通信が終了するまで待機する) または非同期 (プログラムは、通信が起こっている間に実行が続行されます)。  
  
 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)  
 Thin ラッパーで Windows ソケット API をカプセル化します。  
  
 [CSocket](../mfc/reference/csocket-class.md)  
 派生した上位レベルの抽象化`CAsyncSocket`です。 同期的に動作します。  
  
 [CSocketFile](../mfc/reference/csocketfile-class.md)  
 提供、 `CFile` Windows ソケットへのインターフェイスです。  
  
## <a name="see-also"></a>参照  
 [クラスの概要](../mfc/class-library-overview.md)

