---
title: "リモート オートメーションのインストール |Microsoft ドキュメント"
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
- Remote Automation [MFC], installation
- installing Remote Automation [MFC]
ms.assetid: 9a02c9f6-dfc6-4489-b240-a1afe25fa0c5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: acd8ee55261dfa03c68aef506dc90188d8d27d37
ms.sourcegitcommit: fa7a6dccddce3747389c91277a53e296f905305c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="remote-automation-installation"></a>リモート オートメーションのインストール
リモート オートメーションでは、比較的少数のコンポーネントがあります。  
  
-   リモート オートメーションのクライアント プロキシ、AUTPRX32 です。DLL です。  
  
-   リモート オートメーション サーバー側コンポーネント、オートメーション マネージャー AUTMGR32 です。EXE です。  
  
-   RAC マネージャーで、RACMGR32 です。EXE をクリックし、その照合 RACREG32 とします。DLL です。  
  
 これらのうち、RAC マネージャーは、Visual Basic で記述されたおよびため必要な Visual Basic ランタイムをサポートします。 これらおよびその他のリモート オートメーション ファイルは、Visual C++ Enterprise Edition をインストールするときにセットアップによってインストールされます。  
  
 リモート オートメーションのコンポーネントをコンピューターにコピーする場合は、Enterprise Edition がインストールされていない Visual C バージョン、ことを確認する REGSRV32 です。Exe ファイルは、コンピューターのパスにし、RACREG32 を登録します。次のコマンドラインを使用して DLL:  
  
 REGSRVR32 RACREG32.DLL  
  
> [!NOTE]
>  バージョンの RAC マネージャーを使用して Visual C 5.0 GUAGE32 が必要です.Ocx ファイルおよび TABCTL32 です。OCX です。 どちらの方法は、RAC マネージャーの付属している Visual C++ Enterprise edition、バージョン 5.0 またはそれ以降のバージョンについては必要があります。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [オートメーション マネージャー](../mfc/automation-manager-mfc.md)  
  
 [リモート オートメーション接続マネージャー](../mfc/remote-automation-connection-manager.md)  
  
 [リモート オートメーションのユーザー コンポーネント](../mfc/remote-automation-user-components.md)  
  
## <a name="see-also"></a>参照  
 [リモート オートメーション](../mfc/remote-automation.md)

