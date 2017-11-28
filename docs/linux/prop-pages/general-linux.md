---
title: "全般プロパティ (Linux C++ プロジェクト)| Microsoft Docs"
ms.custom: 
ms.date: 9/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56c800a9-3df9-4196-87b2-81adb00e4767
author: mikeblome
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.VCConfiguration.OutputDirectory
- VC.Project.VCConfiguration.IntermediateDirectory
- VC.Project.VCConfiguration.TargetName
- VC.Project.VCConfiguration.TargetExt
- VC.Project.VCConfiguration.DeleteExtensionsOnClean
- VC.Project.VCConfiguration.PlatformToolset
- VC.Project.VCConfiguration.BuildLogFile
- VC.Project.VCConfiguration.ConfigurationType
- VC.Project.VCConfiguration.UseOfSTL
ms.openlocfilehash: 4de08a00ddedf1eec97d1872646a986e09c22547
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="general-properties-linux-c"></a>全般プロパティ (Linux C++)

プロパティ | 説明 | オプション
--- | ---| ---
出力ディレクトリ | 出力ファイル ディレクトリへの相対パスを指定します。環境変数を含めることができます。
中間ディレクトリ | 中間ファイル ディレクトリへの相対パスを指定します。環境変数を含めることができます。
ターゲット名 | このプロジェクトにより生成されるファイル名を指定します。
ターゲットの拡張子 | このプロジェクトにより生成されるファイル拡張子を指定します。 (例: .a)
消去時に削除する拡張子 | クリーンまたはリビルドの実行時に中間ディレクトリから削除するファイルをセミコロンで区切って指定します。ワイルドカードを指定できます。
ビルド ログ ファイル | ビルドのログが有効になっている場合、書き込むビルド ログ ファイルを指定します。
プラットフォームのツールセット | 現在の構成の作成に使用するツールセットを指定します。設定しない場合は、既定のツールセットが使用されます。
リモート ビルド マシン | リモートでのビルド、配置およびデバッグに使用する対象のコンピューターまたはデバイス。
リモート ビルド ルート ディレクトリ | リモート コンピューターまたはデバイス上のディレクトリへのパスを指定します。
リモート ビルド プロジェクト ディレクトリ | プロジェクトに対してリモート コンピューターまたはデバイス上のディレクトリへのパスを指定します。
構成の種類 | この構成が生成する出力の種類を指定します。 | **ダイナミック ライブラリ (.so)** - ダイナミック ライブラリ (.so)<br>**スタティック ライブラリ (.a)** - スタティック ライブラリ (.a)<br>**アプリケーション (.out)** - アプリケーション (.out)<br>**メイクファイル** - メイクファイル<br>
STL の使用 | この構成で使用する C++ 標準ライブラリを指定します。 | **共有されている GNU 標準 C++ ライブラリ**<br>**スタティック GNU 標準 C++ ライブラリ (-static)**<br>
