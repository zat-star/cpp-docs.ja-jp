---
title: "プロバイダーのデバッグ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- debugging [C++], providers
- OLE DB providers, debugging
- Visual C++ debugger, debugging providers
- Visual C++ debugger
ms.assetid: 90d4e7db-06ea-4de0-a7f4-4f3751d50d93
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6cfcb90daaf23a5fd8e248d43b920340e38d8057
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="debugging-your-provider"></a>プロバイダーのデバッグ
ストアには、プロバイダーをデバッグする 2 つの方法があります。  
  
-   プロセスでは、プロバイダーが作成された、ためには、通常、OLE DB コンシューマー テンプレートとプロバイダーをステップを使用して一部のコンシューマー コードを作成できます。  
  
-   Visual C に付属している ITEST ユーティリティを使用することができます。  
  
### <a name="to-use-the-itest-utility"></a>ITEST ユーティリティを使用するには  
  
1.  プロバイダー プロジェクトを開きます。  
  
2.  **プロジェクト** メニューのをクリックして**設定**です。  
  
3.  **プロパティ ページ**ダイアログ ボックスで、をクリックして、**デバッグ**タブです。  
  
4.  **デバッグ セッションの実行可能ファイル**ボックスで、ITEST アプリケーションを選択します。  
  
5.  ブレークポイントを設定し、通常どおりにデバッグします。  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)