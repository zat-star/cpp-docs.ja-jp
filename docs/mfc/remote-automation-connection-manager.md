---
title: "リモート オートメーション接続マネージャー |Microsoft ドキュメント"
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
- Automation clients [MFC], configuring for Remote Automation
- registry [MFC], remote Automation
- Automation servers [MFC], configuring for Remote Automation
- Remote Automation Connection Manager [MFC]
- Remote Automation [MFC], configuring client and server machines
- RAC Manager tool [MFC]
ms.assetid: 562eb7bc-f95c-46ad-ac97-f0dfa98362af
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ee78c1fb5c66974c946d0571db981d899f405fe3
ms.sourcegitcommit: fa7a6dccddce3747389c91277a53e296f905305c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="remote-automation-connection-manager"></a>リモート オートメーション接続マネージャー
クライアントとサーバー コンピューターの両方を構成するのには、レジストリ変更を行う必要があります。 これを行うことを手動ではなくリモート オートメーション接続 (RAC) Manager ツールを使用してはるかに簡単です。 このツールは RACMGR32 です。EXE、RACREG32 と共にします。DLL は、任意のディレクトリにコピーする必要があります。 パスに配置したり、実行を使用してタスク バーから実行できます。 または、ショートカットを作成したり、[スタート] メニューへの参照を配置できます。  
  
 RACMGR32 は Visual Basic で記述され、したがって必要があるいくつかの Visual Basic、Dll をサポートします。 これらのファイルは、RACMGR32 と同じディレクトリに配置されます。CD-ROM 上の exe ファイル。 ビジュアルの C++ の Enterprise Edition のセットアップによってインストールされているこれらのファイルのバージョンとは、同等または Visual Basic の Enterprise Edition 5.0 に同梱されているものよりも新しいです。 Visual C のセットアップは、一般的にこれは C:\Windows\System32 システム ディレクトリに新しいバージョンの Visual Basic ファイルをコピーします。 また、セットアップは、オペレーティング システムにこれらのファイルを登録します。 Visual Basic インストールから、それらを削除することがあります。  
  
## <a name="see-also"></a>参照  
 [オートメーション マネージャー (MFC)](../mfc/automation-manager-mfc.md)   
 [リモート オートメーションのユーザー コンポーネント](../mfc/remote-automation-user-components.md)   
 [リモート オートメーションのインストール](../mfc/remote-automation-installation.md)

