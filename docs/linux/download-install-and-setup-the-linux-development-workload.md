---
title: "Linux ワークロードのダウンロード、インストール、セットアップ | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-linux
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e11b40b2-f3a4-4f06-b788-73334d58dfd9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 13201f9fd397eaf191b7621ec0807a9901e961f8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="download-install-and-setup-the-linux-workload"></a>Linux ワークロードのダウンロード、インストール、セットアップ

## <a name="visual-studio-setup"></a>Visual Studio のセットアップ
1. Visual Studio インストーラーを起動し、**[C++ による Linux 開発]** ワークロードを選びます。

   ![Visual C++ for Linux Development 拡張機能](media/linuxworkload.png)

2. **[インストール]** をクリックしてインストールを続けます。

## <a name="linux-setup"></a>Linux のセットアップ
インストール先の Linux コンピューターには **openssh-server**、**g++**、**gdb**、**gdbserver** がインストールされていて、ssh デーモンが実行している必要があります。  これらがまだない場合は、次のようにしてインストールできます。
 
1. Linux コンピューターのシェル プロンプトで次のコマンドを実行します。

   `sudo apt-get install openssh-server g++ gdb gdbserver`

   sudo コマンドにより、root パスワードの入力を求められる場合があります。  その場合は、入力して続行します。  完了すると、これらのサービスとツールがインストールされます。

1. 次のコマンドを実行し、Linux コンピューターで ssh サービスを実行します。

   `sudo service ssh start`
   
   サービスが開始されてバックグラウンドで実行し、接続を受け付けられる状態になります。
