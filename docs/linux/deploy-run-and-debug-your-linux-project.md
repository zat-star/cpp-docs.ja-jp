---
title: "Linux プロジェクトを配置、実行、デバッグする | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-linux
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7084cdb-17b1-4960-b522-f84981bea879
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
ms.translationtype: Human Translation
ms.sourcegitcommit: dff1e9e03911f65dfcffcd078e0739224f73f4aa
ms.openlocfilehash: db868094a8f10ad05ed6f95bf8a4c8a29a2c941e
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---

# <a name="deploy-run-and-debug-your-project"></a>プロジェクトを配置、実行、デバッグする

プロジェクトを作成したので、コードがコンパイル、実行、およびデバッグされる Linux コンピューターに接続する必要があります。

1. 次に示すように、Visual Studio の標準ドロップダウンを使って、リモート ターゲット アーキテクチャを設定します。![リモート アーキテクチャ](media/architecture.png)

Linux プロジェクトと対話してデバッグするには、いくつかの方法があります。

* ブレークポイント、ウォッチ ウィンドウ、変数のポイントなど、Visual Studio の従来の機能はすべて同じように動作するので、通常どおりにデバッグすることができます。
* **[デバッグ] > [Linux Console]** (Linux コンソール) メニュー項目で、専用の Linux コンソール ウィンドウを開くことができます。

  ![[Linux Console] (Linux コンソール) メニュー](media/consolemenu.png)

  このコンソールでは、ターゲット コンピューターからのコンソール出力が表示され、値を入力してターゲット コンピューターに送信できます。

  ![Linux コンソール ウィンドウ](media/consolewindow.png)

* プロジェクトの **[デバッグ]** プロパティ ページの **[プログラムの引数]** 項目を使って、実行可能ファイルにコマンド ライン引数を渡すことができます。
  
  ![プログラムの引数](media/settings_programarguments.png)

* Linux で実行されているアプリケーションのデバッグには、GDB を使います。  ただし、GDB は&2; 種類のモードで実行でき、プロジェクトの **[デバッグ]** プロパティ ページの **[デバッグ モード]** オプションで選ぶことができます。

  ![GDB のオプション](media/settings_debugger.png)

  | 選択内容 | 説明
  | --------- | ---
  | gdbserver | GDB はローカルに実行され、リモート システムで実行している gdbserver に接続します。  Linux コンソール ウィンドウはこのモードだけをサポートすることに注意してください。 
  | gdb       | Visual Studio のデバッガーがリモート システム上の GDB を駆動します。GDB のローカル バージョンとターゲット コンピューターにインストールされているバージョンの間に互換性がない場合、互換性が高くなります。

* **[追加のデバッガー コマンド]** エントリを使って、特定のデバッガー オプションを GDB に渡すことができます。  たとえば、SIGILL (無効な命令) シグナルを無視することができます。  これを行うには、**handle** コマンドを使います。  上の図のように、次のコードを **[追加のデバッガー コマンド]** エントリに追加します。

  ```handle SIGILL nostop noprint```

