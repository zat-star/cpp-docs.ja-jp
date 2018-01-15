---
title: "インターネット アプリケーションのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Web applications [MFC], testing
- debugging Web applications [MFC], testing applications
- testing [MFC], Internet applications
- debugging [MFC], Web applications
- Internet debugging and testing
ms.assetid: ac4c74e3-d4ad-4e19-8f6c-e270de067f01
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0cc214eb98b8aa9e927fd471ba313e4cade426a2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="testing-internet-applications"></a>インターネット アプリケーションのテスト
特に、Web サーバーで実行されているアプリケーションの場合、インターネットには、一意なテスト課題があります。 初期のテストは実行される可能性があります、テスト サーバーに接続するシングル ユーザーのクライアントを使用します。 これは、コードのデバッグに役立つになります。  
  
 実際の条件下でテストするも: 複数のクライアントが低速シリアル回線と同様に高速接続を介して接続されている、モデム接続を含むです。 実際の状況をシミュレートするが困難であることができますが、確実に即したシナリオのコストと、それらを実行する価値があります。 可能であれば、することも容量とストレス テストするためのツールを使用します。 バグ、タイミング バグなどの特定のクラスを検出し、再現する、が困難なです。  
  
 インターネットのプログラミングの課題の 1 つは、その可視性です。 サイトに多くのアクセスは、サーバーの速度が低下可能性があります。 気付かれないようにするようにサーバーを必要とします。 アプリケーションが (たとえば、レジストリへの書き込み中に、またはクライアントの cookie を書き込み中にデータの破損など) が失敗した場合、ユーザーのコンピューターが破壊される可能性がありますを何もできないようにするには。  
  
## <a name="see-also"></a>参照  
 [MFC インターネット プログラミングの作業](../mfc/mfc-internet-programming-tasks.md)   
 [MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)

