---
title: "一般的なクラス デザインの理念 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.mfc
dev_langs: C++
helpviewer_keywords:
- designing classes [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- classes [MFC], MFC class design
- Windows API [MFC], and MFC
ms.assetid: e6861ae0-1581-4d9c-9ddf-63f9afcdb913
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7e4c5c15e7d18fb768b7b0fffa99140ae64075da
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="general-class-design-philosophy"></a>一般的なクラス デザインの考え方
Microsoft Windows では、C++ 言語が普及よりかなり前に設計されています。 数千のアプリケーションでは、C 言語の Windows アプリケーション プログラミング インターフェイス (API) を使用するため、そのインターフェイスは、近い将来に保持されます。 手続き型の C 言語 API の上に、任意の C++ Windows インターフェイスを構築する必要がそのためです。 これは、C++ アプリケーションが C のアプリケーションと共存できることを保証します。  
  
 Microsoft Foundation Class ライブラリでは、次の設計目標を満たす Windows へのオブジェクト指向インターフェイスを示します。  
  
-   Windows のアプリケーションを記述する作業量を大幅に縮小します。  
  
-   実行速度が、C 言語 API と同等です。  
  
-   サイズのオーバーヘッドを最小限のコード。  
  
-   任意の Windows の C 関数を直接呼び出す権限です。  
  
-   既存の C アプリケーションを C++ 簡単に変換します。  
  
-   C 言語の Windows プログラミングの経験の既存のベースから利用する機能。  
  
-   C. でよりも C++ で Windows API の使用が容易になります  
  
-   ActiveX コントロール、データベースのサポート、印刷、ツールバー、およびステータス バーなどの機能を使いやすく強力な抽象化に複雑です。  
  
-   C++ 言語の機能を効果的に使用する C++ の場合は true。 Windows API。  
  
 MFC ライブラリのデザインの詳細を参照してください。  
  
-   [アプリケーション フレームワーク](../mfc/application-framework.md)  
  
-   [C 言語 API との関係](../mfc/relationship-to-the-c-language-api.md)  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../mfc/class-library-overview.md)

