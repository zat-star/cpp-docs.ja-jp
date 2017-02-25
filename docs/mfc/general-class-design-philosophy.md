---
title: "一般的なクラス デザインの考え方 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.mfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "クラス [C++], MFC クラスのデザイン"
  - "デザイン (クラスを)"
  - "MFC [C++], Windows API"
  - "Visual C, Windows API の呼び出し"
  - "Windows API [C++], および MFC"
ms.assetid: e6861ae0-1581-4d9c-9ddf-63f9afcdb913
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 一般的なクラス デザインの考え方
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft Windows は C\+\+ 言語が関係するようになったかなり以前に設計されています。  アプリケーションの桁が C 言語の Windows アプリケーション プログラミング インターフェイス \(API\) を使用する場合、そのインターフェイスは近い将来の間保持されます。  したがって、C\+\+ Windows インターフェイスは手順 C 言語 API 上に構築する必要があります。  これは C\+\+ アプリケーションが C アプリケーションと共存できることを保証します。  
  
 Microsoft Foundation Class ライブラリには、ウィンドウを次のデザインの目標を達成するオブジェクト指向インターフェイスです:  
  
-   Windows アプリケーションを作成するための工数が大幅に低減されます。  
  
-   C 言語 API でそれに相当する実行速度。  
  
-   オーバーヘッド最小限のコード サイズ。  
  
-   Windows C 関数を直接呼び出す機能。  
  
-   C\+\+ の C アプリケーションを簡単に変換します。  
  
-   C 言語の Windows のプログラミング作業の既存のベースで利用できる機能。  
  
-   C と C\+\+ の.で Windows API を簡単に使用できます。  
  
-   使用しやすく、ActiveX コントロール、データベース サポート、印刷、ツール バーとステータス バーのような複雑な機能の強力な抽象化です。  
  
-   効果的な C\+\+ 言語機能を使用すると、C\+\+ 用の Windows API を調整します。  
  
 MFC ライブラリの設計の詳細については、"参照してください:  
  
-   [アプリケーション フレームワーク](../mfc/application-framework.md)  
  
-   [C 言語 API との関係](../mfc/relationship-to-the-c-language-api.md)  
  
## 参照  
 [クラスの概要](../mfc/class-library-overview.md)