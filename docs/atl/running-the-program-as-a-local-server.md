---
title: "ローカル サーバーとして、プログラムを実行している |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- debugging [ATL], running services as local server
- ATL services, running as local servers
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3e398bfed0174e4ec2a262ea03076ed17881f900
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="running-the-program-as-a-local-server"></a>ローカル サーバーとして、プログラムの実行
サービスとしてプログラムを実行する便利な場合、プログラムが通常のローカル サーバーとして実行できるように、レジストリを一時的に変更することができます。 名前を`LocalService`、アプリケーション Id の値を`_LocalService`を確認してください、 `LocalServer32` CLSID の下にあるキーが正しく設定します。 (名前 DCOMCNFG を使用して、アプリケーションを別のコンピューターで実行することを指定することに注意してください、`LocalServer32`キーを`_LocalServer32`)。ローカル サーバーは複数数秒かかります起動時にあるため、プログラムを実行しているへの呼び出し**余分**で`CAtlServiceModuleT::Start`が失敗するまでに数秒かかります。  
  
## <a name="see-also"></a>参照  
 [デバッグのヒント](../atl/debugging-tips.md)

