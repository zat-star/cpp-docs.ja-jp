---
title: "Linux ワークロードのダウンロード、インストール、セットアップ | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e11b40b2-f3a4-4f06-b788-73334d58dfd9
author: BrianPeek
ms.author: brpeek
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: dff1e9e03911f65dfcffcd078e0739224f73f4aa
ms.openlocfilehash: 09ce0024b7a98729b28968fff081ed105b5463e1

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



<!--HONumber=Feb17_HO4-->


