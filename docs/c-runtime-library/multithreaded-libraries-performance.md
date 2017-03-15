---
title: "マルチスレッド ライブラリのパフォーマンス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ライブラリ, マルチスレッド"
  - "マルチスレッド ライブラリ"
  - "パフォーマンス, マルチスレッド"
  - "スレッド処理 [C++], パフォーマンス"
ms.assetid: faa5d808-087c-463d-8f0d-8c478d137296
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# マルチスレッド ライブラリのパフォーマンス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

シングルスレッド CRT は使用できません。  このトピックでは、マルチスレッド ライブラリを最大限のパフォーマンス方法について説明します。  
  
## パフォーマンスの最大化  
 マルチスレッド ライブラリのパフォーマンスは、が削除されたシングルスレッド ライブラリのパフォーマンスが向上し、ピクセルです。  これらの状況で高いが必要な場合は、いくつかの新機能があります。  
  
-   ストリームをロックし、[\_nolock 関数](../c-runtime-library/nolock-functions.md) を使用するためにストリームに直接アクセスすることをロックする独立したストリーム。  これにより、ロックの使用が重要なループの外側でホイストされるようにようにします。  
  
-   スレッドごとのロケールはマルチスレッドのシナリオのロケール アクセスのコストを削減します \([\_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)を参照してください。  
  
-   ロケールに依存する関数には多くのコスト \(たとえば、[printf、\_printf\_l、wprintf、\_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)\) を削除するパラメーターとして \(パラメーターで終わる名前と\) ロケールを受け取ります。  
  
-   共通のコードページの最適化は多くの短い操作のコストを削減します。  
  
-   [\_CRT\_DISABLE\_PERFCRIT\_LOCKS](../c-runtime-library/crt-disable-perfcrit-locks.md) を定義すると、シングルスレッド I\/O モデルを想定し、関数の\_nolock のフォームを使用するようにすべての I\/O 操作を実行します。  これは、非常に I\/O ベースのシングルスレッド アプリケーションのパフォーマンスを向上させることができます。  
  
-   CRT ヒープのハンドルの公開大幅にスケーリングされたシナリオのパフォーマンスを向上する CRT ヒープの Windows の下位断片化ヒープ \(LFH\) を実行できます。  
  
## 参照  
 [CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)