---
title: "Linux プロジェクトの構成 | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d7c6adf-54b9-4b23-bd23-5de0c825b768
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
ms.openlocfilehash: b110994cab92d2151f63912d2b08af56059b82d7
ms.lasthandoff: 02/24/2017

---

# <a name="configure-a-linux-project"></a>Linux プロジェクトの構成

## <a name="general-settings"></a>[全般設定]
Visual Studio で Linux プロジェクトに対して、さまざまなオプションを構成することができます。  これらのオプションを表示するには、**[プロジェクト]、[プロパティ]** メニューの順に選択するか、次のように、**ソリューション エクスプローラー**でプロジェクトを右クリックし、コンテキスト メニューから **[プロパティ]** を選択します。

![全般構成](media/settings_general.png)

既定では、実行可能ファイル (.out) は、ツールを使用してビルドされます。  静的または動的なライブラリをビルドする場合や、既存のメイクファイルを使用する場合は、**[構成の種類]** の選択項目を使用します。

## <a name="remote-settings"></a>リモート設定
リモートの Linux コンピューターに関する設定を変更するには、次のように、**[リモート設定]** 項目を選択します。

![リモート設定](media/settings_remote.png)

* ターゲットの Linux コンピューターを変更するには、**[対象コンピューター]** エントリを使用します。  これによって、以前に作成された接続のいずれかを選択できます。  新しいエントリを作成する場合は、「[Connecting to Your Remote Linux Computer](connect-to-your-remote-linux-computer.md)」 (リモートの Linux コンピューターへの接続) セクションを参照してください。

* **[リモート ルート ディレクトリ]** で、リモートの Linux コンピューター上のプロジェクトを構築するルート場所が決定します。  これは、変更しない限り、既定で **~/projects** に設定されます。

* **[リモート プロジェクト ディレクトリ]** は、リモートの Linux コンピューターでこの特定のプロジェクトが構築される場所です。  これは、既定で **$(RemoteRootDir)/$(ProjectName)** に設定され、上で設定したルート ディレクトリ下の、現在のプロジェクトから名前が付けられたディレクトリに展開されます。

* 最後に、既定の C および C++ コンパイラ、またはプロジェクトのビルドに使用したリンカーとアーカイバーを変更する場合は、**[ツールの既定値]** セクションで適切なエントリを使用します。  これらは特定のバージョンの GCC (Clang コンパイラなど) を使用する際に設定する場合があります。

## <a name="vc-directories"></a>VC++ ディレクトリ
既定では、Visual Studio に Linux コンピューターのシステム レベルのインクルード ファイルは含まれません。  たとえば、**/usr/include** ディレクトリの項目は Visual Studio には存在しません。  完全に [IntelliSense](/visualstudio/ide/using-intellisense) をサポートするには、これらのファイルを、開発用コンピューターの任意の場所にコピーし、Visual Studio でこの場所を指定する必要があります。  scp (セキュア コピー) を使用して、ファイルをコピーすることもできます。  Windows 10 では、[Bash on Windows](https://msdn.microsoft.com/commandline/wsl/about) を使用して scp を実行することができます。  以前のバージョンの Windows では、[PSCP (PuTTY セキュア コピー)](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html) などを使用できました。

次のようなコマンドを使用して、ファイルをコピーすることができます。

`scp -r linux_username@remote_host:/usr/include .`

もちろん、上記の **linux_username** と **remote_host** の値は、実際の環境に適したものに置き換えます。

ファイルがコピーされたら、プロジェクト プロパティの **[VC++ ディレクトリ]** 項目を使用して、コピーされた追加のインクルード ファイルがある場所を Visual Studio に示します。

![VC++ ディレクトリ](media/settings_directories.png)

## <a name="copy-sources"></a>ソースのコピー
ビルド時に、開発用 PC 上のソース ファイルは、Linux コンピューターにコピーされ、そこでコンパイルされます。  既定では、Visual Studio プロジェクトのすべてのソースは、上記の設定で指定された場所にコピーされます。  ただし、リストにさらにソースを追加するこもできます。あるいは、ソースのコピーを完全にオフ (メイクファイル プロジェクトではこれが既定) にすることもできます。

* **[コピーするソース]** で、リモート コンピューターにコピーするソースが決定します。  既定では、**@(SourcesToCopyRemotely)** はプロジェクトのすべてのファイルに設定されます。

* **[ソースのコピー]** をオンまたはオフにして、リモート コンピューターへのソース ファイルのコピーを有効または無効にすることができます。

* **[コピーする追加ソース]** では、リモート システムにコピーするソース ファイルを追加することができます。  セミコロンで区切ったリストを指定することも、次のように、**:=** 構文で使用するローカルおよびリモート名を指定することもできます。

  `C:\Projects\ConsoleApplication1\MyFile.cpp:=~/projects/ConsoleApplication1/ADifferentName.cpp;C:\Projects\ConsoleApplication1\MyFile2.cpp:=~/projects/ConsoleApplication1/ADifferentName2.cpp;`

## <a name="build-events"></a>ビルド イベント
すべてのコンパイルはリモート コンピューターで実行されるため、プロジェクト プロパティの [ビルド イベント] セクションにいくつかのビルド イベントが追加されています。  追加されたのは **[リモートのビルド前イベント]**、**[リモートのリンク前イベント]**、および **[Remove Post-Build Event]** (リモートのビルド後イベント) で、リモート コンピューターでプロセスの個々のステップの前後に発生します。

![ビルド イベント](media/settings_buildevents.png)

## <a name="see-also"></a>関連項目
[プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)
