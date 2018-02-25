---
title: "プロバイダーのデバッグ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- debugging [C++], providers
- OLE DB providers, debugging
- Visual C++ debugger, debugging providers
- Visual C++ debugger
ms.assetid: 90d4e7db-06ea-4de0-a7f4-4f3751d50d93
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c5dcca9888f22aadb629bcd79a5eb73b39cddcfa
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
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