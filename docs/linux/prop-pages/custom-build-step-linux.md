---
title: "カスタム ビルド ステップのプロパティ (Linux C++) | Microsoft Docs"
ms.custom: 
ms.date: 10/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77a9c1fb-7c41-4a9b-9418-18ac17ce4e74
author: mikeblome
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.IVCEventTool.CommandLine
- VC.Project.IVCEventTool.Description
- VC.Project.IVCEventTool.ExcludedFromBuild
- VC.Project.VCConfiguration.BuildLogFile
ms.openlocfilehash: 77d483e9d4dc74cbe9ba2736a26561bb410fa6ca
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="custom-build-step-properties-linux-c"></a>カスタム ビルド ステップのプロパティ (Linux C++)


プロパティ | 説明
--- | ---
コマンド ライン | カスタム ビルド ステップによって実行されるコマンド。
説明 | カスタム ビルド ステップを実行するときに表示されるメッセージ。
出力 | カスタム ビルド ステップが生成する出力ファイル。 この設定は、インクリメンタル ビルドが正しく機能するために必要です。
[追加の依存ファイル] | カスタム ビルド ステップで使用する追加の入力ファイルの、セミコロンで区切られた一覧。
[以後に実行] および [以前に実行] | ビルド プロセスでカスタム ビルド ステップが実行されるタイミングを、表示されているターゲットを基準にして定義します。 最もよく表示されるターゲットは BuildGenerateSources、BuildCompile、および BuildLink です。これらはビルド プロセスの主なステップを表しています。 また、Midl、CLCompile、および Link もよく表示されるターゲットです。
[出力をコンテンツとして扱う] | このオプションは、.appx パッケージにすべてのコンテンツ ファイルが含まれる Windows ストアまたは Windows Phone アプリに対してのみ意味を持ちます。