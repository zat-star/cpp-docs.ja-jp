---
title: "リモート ビルド イベント (Linux C++) | Microsoft Docs"
ms.custom: 
ms.date: 9/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 165d3690-5bd8-4b0b-bc66-8b699d85a61b
author: mikeblome
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.IVCEventTool.CommandLine
- VC.Project.IVCEventTool.Description
- VC.Project.IVCEventTool.ExcludedFromBuild
- VC.Project.VCConfiguration.BuildLogFile
ms.openlocfilehash: 951b383708740aa4cd7571afc007f6fb328c254c
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="build-event-properties-linux-c"></a>ビルド イベント プロパティ (Linux C++) 


## <a name="pre-build-event"></a>ビルド前のイベント
プロパティ | 説明
--- | ---
コマンド ライン | 実行するビルド前イベント ツールのコマンド ラインを指定します。
説明 | 表示するビルド前イベント ツールの説明を指定します。
ビルドで使用 | このビルド イベントを現在の構成のビルドから除外するかどうかを指定します。
コピーする追加ファイル | リモート システムにコピーする追加ファイルを指定します。 オプションで、次のような構文を使用して、一覧をリモート マッピング ペアにローカルとして指定することができます: fulllocalpath1:=fullremotepath1;fulllocalpath2:=fullremotepath2。ここで、ローカル ファイルをリモート システム上の指定したリモートの場所にコピーできます。

## <a name="pre-link-event"></a>リンク前のイベント
プロパティ | 説明
--- | ---
コマンド ライン | 実行するリンク前イベント ツールのコマンド ラインを指定します。
説明 | 表示するリンク前イベント ツールの説明を指定します。
ビルドで使用 | このビルド イベントを現在の構成のビルドから除外するかどうかを指定します。
コピーする追加ファイル | リモート システムにコピーする追加ファイルを指定します。 オプションで、次のような構文を使用して、一覧をリモート マッピング ペアにローカルとして指定することができます: fulllocalpath1:=fullremotepath1;fulllocalpath2:=fullremotepath2。ここで、ローカル ファイルをリモート システム上の指定したリモートの場所にコピーできます。

## <a name="post-build-event"></a>ビルド後のイベント
プロパティ | 説明
--- | ---
コマンド ライン | 実行するビルド後イベント ツールのコマンド ラインを指定します。
説明 | 表示するビルド後イベント ツールの説明を指定します。
ビルドで使用 | このビルド イベントを現在の構成のビルドから除外するかどうかを指定します。
コピーする追加ファイル | リモート システムにコピーする追加ファイルを指定します。 オプションで、次のような構文を使用して、一覧をリモート マッピング ペアにローカルとして指定することができます: fulllocalpath1:=fullremotepath1;fulllocalpath2:=fullremotepath2。ここで、ローカル ファイルをリモート システム上の指定したリモートの場所にコピーできます。

## <a name="remote-pre-build-event"></a>リモートのビルド前イベント
プロパティ | 説明
--- | ---
コマンド ライン | リモート システムで実行するビルド前イベント ツールのコマンド ラインを指定します。
説明 | 表示するビルド前イベント ツールの説明を指定します。
ビルドで使用 | このビルド イベントを現在の構成のビルドから除外するかどうかを指定します。
コピーする追加ファイル | リモート システムからコピーする追加ファイルを指定します。 オプションで、次のような構文を使用して、一覧をローカル マッピング ペアにリモートとして指定することができます: fullremotepath1:=fulllocalpath1;fullremotepath2:=fulllocalpath2。ここで、リモート ファイルをローカル コンピューター上の指定した場所にコピーできます。

## <a name="remote-pre-link-event"></a>リモートのリンク前イベント
プロパティ | 説明
--- | ---
コマンド ライン | リモート システムで実行するリンク前イベント ツールのコマンド ラインを指定します。
説明 | 表示するリンク前イベント ツールの説明を指定します。
ビルドで使用 | このビルド イベントを現在の構成のビルドから除外するかどうかを指定します。
コピーする追加ファイル | リモート システムからコピーする追加ファイルを指定します。 オプションで、次のような構文を使用して、一覧をローカル マッピング ペアにリモートとして指定することができます: fullremotepath1:=fulllocalpath1;fullremotepath2:=fulllocalpath2。ここで、リモート ファイルをローカル コンピューター上の指定した場所にコピーできます。

## <a name="remote-post-build-event"></a>リモートのビルド後イベント
プロパティ | 説明
--- | ---
コマンド ライン | リモート システムで実行するビルド後イベント ツールのコマンド ラインを指定します。
説明 | 表示するビルド後イベント ツールの説明を指定します。
ビルドで使用 | このビルド イベントを現在の構成のビルドから除外するかどうかを指定します。
コピーする追加ファイル | リモート システムからコピーする追加ファイルを指定します。 オプションで、次のような構文を使用して、一覧をローカル マッピング ペアにリモートとして指定することができます: fullremotepath1:=fulllocalpath1;fullremotepath2:=fulllocalpath2。ここで、リモート ファイルをローカル コンピューター上の指定した場所にコピーできます。
