---
title: "ローカル サーバーとして、プログラムを実行している |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- debugging [ATL], running services as local server
- ATL services, running as local servers
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 131bfefb35164b2d1e53f5671016235e5426c096
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="running-the-program-as-a-local-server"></a>ローカル サーバーとして、プログラムの実行
サービスとしてプログラムを実行する便利な場合、プログラムが通常のローカル サーバーとして実行できるように、レジストリを一時的に変更することができます。 名前を`LocalService`、アプリケーション Id の値を`_LocalService`を確認してください、 `LocalServer32` CLSID の下にあるキーが正しく設定します。 (名前 DCOMCNFG を使用して、アプリケーションを別のコンピューターで実行することを指定することに注意してください、`LocalServer32`キーを`_LocalServer32`)。ローカル サーバーは複数数秒かかります起動時にあるため、プログラムを実行しているへの呼び出し**余分**で`CAtlServiceModuleT::Start`が失敗するまでに数秒かかります。  
  
## <a name="see-also"></a>関連項目  
 [デバッグのヒント](../atl/debugging-tips.md)

