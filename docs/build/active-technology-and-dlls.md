---
title: "Active テクノロジと Dll |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- in-process server DLLs
- Automation [C++], DLLs
- DLLs [C++], Active Technology
- Active technology [C++]
- MFC DLLs [C++], Active Technology
ms.assetid: 3ed27f8d-164a-4562-ad61-9f2333404cc7
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 44dcc58aed4025af2e3e2177e978633c13f0ef20
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="active-technology-and-dlls"></a>Active テクノロジと DLL
Active テクノロジにより、オブジェクトのサーバーを DLL 内部に完全に実装します。 この種類のサーバーには、インプロセス サーバーは呼び出されます。 MFC は、Active テクノロジは、サーバーをコンテナーのメイン メッセージ ループにフックするための手段を提供しないために主に、ビジュアル編集の機能は、すべてのプロセスでサーバーを完全にできません。 MFC には、アクセラレータ キーとアイドル処理を処理するコンテナー アプリケーションのメッセージ ループへのアクセスが必要です。  
  
 オートメーション サーバーを作成しているユーザー インターフェイスを持っていない場合は、インプロセス サーバー、サーバーを作成でき、DLL に完全に移行できます。  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [オートメーション サーバー](../mfc/automation-servers.md)  
  
## <a name="see-also"></a>参照  
 [Visual C++ の DLL](../build/dlls-in-visual-cpp.md)