---
title: "リモート オートメーションにおけるセキュリティ |Microsoft ドキュメント"
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
- AllowRemoteActivation [MFC]
- Remote Automation [MFC], security
- activating objects [MFC]
- security [MFC]
- Automation objects [MFC], security options
- object activation [MFC]
- security [MFC], Remote Automation
ms.assetid: 276b300d-c0b5-4bd8-8bf5-0270994b9cfa
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e535fac6330d6268629e8e3681fec47c7b0d65d3
ms.sourcegitcommit: fa7a6dccddce3747389c91277a53e296f905305c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="security-in-remote-automation"></a>リモート オートメーションにおけるセキュリティ
リモート オートメーションは、サーバー アプリケーション ライター (またはの管理者ではなく、) を特定のオブジェクトをリモートから起動する可能性がある方法を指定できるように、セキュリティの基本的なレベルをサポートします。 特定のシステム上のすべてのオートメーション オブジェクトは、「リモートからアクティブ化が行われないよう」または「リモートからアクティブ化を許可する」ためグローバルに設定することがあります。 またより多くの場合はこのような機能を個々 のオブジェクトに指定できます。 リモート オートメーションの各オブジェクトのレジストリ設定、キーを使用して**AllowRemoteActivation**が特定のサーバーをリモートから起動する場合があるかどうかを決定します。 場合は、システム全体の設定は、このモードを使用して、し、レジストリ内の各オブジェクト割り当てることができます、このキーと 1 つずつの個々 の状態を"yes"または適切なとして"no"に設定することがあります。  
  
 サーバー システムが Windows NT または Windows 2000 を実行して、セキュリティの別の形が許可されます。 ここでは、リモート オートメーションでは、NT アクセス制御リスト (ACL) を使用して、どのユーザーまたはグループまたはユーザー グループをリモートでをアクティブ化できる特定のサーバーを指定します。  
  
 セキュリティ オプションは、オブジェクト全体に適用されるに注意してください。そのオブジェクトに対する特定のインターフェイス、または個々 のプロパティまたはメソッドの属性を設定することはできません。  
  
 リモート オートメーション接続 (RAC) マネージャーを通じて、すべてのセキュリティ オプションを設定する場合があります。  
  
## <a name="see-also"></a>参照  
 [リモート オートメーション](../mfc/remote-automation.md)

