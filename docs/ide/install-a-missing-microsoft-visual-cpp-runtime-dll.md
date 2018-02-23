---
title: "不足している Microsoft Visual C ランタイム DLL をインストール |Microsoft ドキュメント"
description: "検索して見つからない Visual C ランタイム Dll をインストールする方法。"
ms.date: 08/30/2017
ms.topic: article
dev_langs:
- C++
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d40e1594b2190d4bbfd2fe52fddaad04af527573
ms.sourcegitcommit: a5a69d2dc3513261e9e28320e4e067aaf40d2ef2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2018
---
# <a name="install-a-missing-microsoft-visual-c-runtime-dll"></a>不足している Microsoft Visual C ランタイム DLL をインストールします。

多くの場合、Microsoft Visual C を使用して作成されたプログラムは、いくつかの他の Visual C ランタイム ライブラリ ファイル、または Dll を実行する必要があります。 これらのランタイム Dll で使用できる、*再頒布可能パッケージ*、Visual C のバージョンごとに、ライブラリ ファイルのインストーラー プログラムです。 インストーラーによって、任意のプログラムで必要な再頒布可能パッケージを含める必要があります。 そうでない場合も再頒布可能パッケージをインストールできプログラムを実行するときに、システム エラーを修正できます。 

あるプログラムを起動するときにシステム エラーが発生した場合に、プログラムで Visual C ランタイム DLL が見つからないことがわかる「VCRuntime140.dll がお使いのコンピューターから不足しているために、このプログラムを開始できません」と同じようにします。 多くの場合には、プログラムをアンインストールし、再度インストールしてこの問題を解決することができます。 強く勧めこの手順を最初に、しようとしている他の潜在的な修正前にします。

プログラムによってインストールされている再頒布可能パッケージが古い場合があります。 マイクロソフトは、更新されたバージョンのランタイム Dll 使用可能な時、バグに対処してセキュリティ上の問題。 安全かつ正常に実行しているコンピューターを保持するには、は任意のランタイム DLL に最新の更新プログラムを使用することをお勧めします。 更新済みインストーラーは、プログラムでは、この更新プログラムが提供される場合がありますの使用を確認します。 ある場合は、プログラムを再インストールする更新されたインストーラーを使用します。

プログラムを再インストールすると、システム エラーの解決がないため、し、プログラムのインストーラーが破損しているかが破損しているか、コンピューター上のランタイム Dll が壊れている可能性があります。 プログラムのインストーラーの新しいコピーをダウンロードして、最初の再インストールしようとします。 それでも、または、インストーラーが利用できない、し、価値があるコンピューターに Microsoft Visual C 再頒布可能インストールを確認します。 

次の表は、再頒布可能パッケージのコピーをダウンロードするへのリンクと共に、1 つまたは複数の再頒布可能パッケージに含まれている Dll の一覧を示します。 再頒布可能パッケージの新しいコピーをダウンロードする前に、かどうかは、既存のインストールを修復することができますが表示されます。

|DLL が見つからない  |再頒布可能パッケージ  |
|---------|---------|
|atl80.dll<br />msvcm80.dll<br />msvcp80.dll<br />msvcr80.dll<br />mfc80.dll<br />mfc80u.dll<br />mfcm80.dll<br />mfcm80u.dll|[Microsoft Visual C 2005 再頒布可能パッケージ (x86)](https://www.microsoft.com/en-us/download/details.aspx?id=5638)<br />[Microsoft Visual C 2005 再頒布可能パッケージ (x64)](https://www.microsoft.com/en-us/download/details.aspx?id=18471)<br />[Microsoft Visual C 2005 のサービス パック 1 再頒布可能パッケージ MFC セキュリティ更新プログラム](https://www.microsoft.com/en-us/download/details.aspx?id=26347)|
|atl90.dll<br />msvcr90.dll<br />msvcm90.dll<br />msvcp90.dll<br />mfc90.dll<br />mfc90u.dll<br />mfcmifc80.dll<br />mfcm90.dll<br />mfcm90u.dll|[Microsoft Visual C 2008 再頒布可能パッケージ - x86](https://www.microsoft.com/en-us/download/details.aspx?id=5582)<br />[Microsoft Visual C 2008 再頒布可能パッケージの x64](https://www.microsoft.com/en-us/download/details.aspx?id=2092)<br />[Microsoft Visual C 2008 のサービス パック 1 再頒布可能パッケージ MFC セキュリティ更新プログラム](https://www.microsoft.com/en-us/download/details.aspx?id=26368)|
|atl100.dll<br />msvcr100.dll<br />msvcp100.dll<br />msdia71.dll<br />vcomp100.dll<br />mfc100.dll<br />mfc100u.dll<br />mfcmifc80.dll<br />mfcm100.dll<br />mfcm100u.dll|[Microsoft Visual C 2010 x86 再頒布可能パッケージ](https://www.microsoft.com/en-us/download/details.aspx?id=8328)<br />[Microsoft Visual C 2010 x64 再頒布可能パッケージ](https://www.microsoft.com/en-us/download/details.aspx?id=13523)<br />[Microsoft Visual C++ 2010 Service Pack 1 再頒布可能パッケージ MFC セキュリティ更新プログラム](https://www.microsoft.com/en-us/download/details.aspx?id=26999)|
|atl110.dll<br />msvcr110.dll<br />msvcp110.dll<br />mfc110.dll<br />mfc110u.dll<br />mfcmifc80.dll<br />mfcm110.dll<br />mfcm110u.dll<br />concrt110.dll<br />vccorlib110.dll<br />vcamp110.dll<br />vcomp110.dll|[Microsoft Visual C 2012 再頒布可能パッケージ (Visual Studio 2012 Update 4)](https://www.microsoft.com/en-us/download/details.aspx?id=30679)|
|msvcr120.dll<br />msvcp120.dll<br />mfc120.dll<br />mfc120u.dll<br />mfcmifc80.dll<br />mfcm120.dll<br />mfcm120u.dll<br />concrt120.dll<br />vccorlib120.dll<br />vcamp120.dll<br />vcomp120.dll|[Microsoft Visual C 2013 再頒布可能 (個別のダウンロード パッケージへのリンク)](https://support.microsoft.com/en-us/help/3179560/update-for-visual-c-2013-and-visual-c-redistributable-package)<br />[Visual Studio 2013 のマルチバイト MFC ライブラリ](https://www.microsoft.com/en-us/download/details.aspx?id=40770)<br />[サイドロードした Windows 8.1 アプリ (.zip ダウンロード) 用の visual C 2013 ランタイム](http://download.microsoft.com/download/5/F/0/5F0F8404-9329-44A9-8176-ED6F7F746F25/VCLibs_Redist_Packages.zip)|
|vcruntime140.dll<br />vcruntime140_app.dll<br />msvcp140.dll<br />mfc140.dll<br />mfc140u.dll<br />mfcmifc80.dll<br />mfcm140.dll<br />mfcm140u.dll<br />concrt140.dll<br />vccorlib140.dll<br />vcamp140.dll<br />vcomp140.dll|[Microsoft Visual C++ 2017 再頒布可能パッケージ (x86)](https://go.microsoft.com/fwlink/?LinkId=746571)<br />[Microsoft Visual C++ 2017 再頒布可能パッケージ (x64)](https://go.microsoft.com/fwlink/?LinkId=746572)|
|msvcr100_clr0400.dll<br />msvcr110_clr0400.dll<br />msvcr120_clr0400.dll|[.NET Framework のダウンロード](https://www.microsoft.com/net/download/framework)|

### <a name="to-repair-an-existing-redistributable-package"></a>既存の再頒布可能パッケージを修復するには

1. コントロール パネルを開きます。 Windows 10 では、次のように入力します。*コントロール パネルの* デスクトップで、タスク バーにコントロールを検索し、**コントロール パネルの**  、のいずれか。

2. コントロール パネル で、**プログラム** > **プログラムと機能**します。 Microsoft Visual C 再頒布可能 DLL で欠落している場合に対応するバージョンを選択します。 場合、**変更**選択して、一覧の上部にあるボタンが表示されます。 唯一の選択肢が場合**アンインストール**、このバージョンの再頒布可能パッケージを修復することはできません。

3. 選択**修復**再頒布可能パッケージのセットアップ ダイアログ ボックスでします。 修復が完了すると、再起動する必要があります。 