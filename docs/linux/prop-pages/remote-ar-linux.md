---
title: "リモート アーカイブ プロパティ (C++ Linux) | Microsoft Docs"
ms.custom: 
ms.date: 9/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ee1e44c-8337-4c3a-b2f3-35e4be954f9f
author: mikeblome
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.Ar.CreateIndex
- VC.Project.Ar.CreateThinArchive
- VC.Project.Ar.NoWarnOnCreate
- VC.Project.Ar.TruncateTimestamp
- VC.Project.Ar.SuppressStartupBanner
- VC.Project.Ar.Verbose
- vc.project.AdditionalOptionsPage
- VC.Project.Ar.OutputFile
- VC.Project.VCConfiguration.BuildLogFile
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 83b69c8aea824f08f3db6aa5f5b7bf01cacb339e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="remote-archive-properties-c-linux"></a>リモート アーカイブ プロパティ (C++ Linux)

プロパティ | 説明
--- | ---
アーカイブ インデックスの作成 | アーカイブ インデックス (cf. ranlib) を作成します。  これにより、リンク処理を高速化し、ライブラリ内の依存関係を削減できます。
シン アーカイブの作成 | シン アーカイブを作成します。  シン アーカイブにはオブジェクトの相対パスが含まれます。相対パスを含めることは、オブジェクトを組み込むことの代わりになります。  シンと標準を切り替えるには、既存のライブラリを削除する必要があります。
作成時の警告なし | ライブラリが作成されても警告を出しません。
タイムスタンプの切り捨て | タイムスタンプおよび UID/GID に 0 を使用します。
著作権情報の非表示 | バージョン番号を表示しません。
詳細 | 詳細
その他のオプション | その他のオプションです。
出力ファイル | /OUT オプションを使用すると、lib によって作成されるプログラムの既定の名前と場所がオーバーライドされます。
アーカイブ処理 | スタティック オブジェクトのリンク中に起動するプログラムか、またはリモート システム上のアーカイブ処理へのパスを指定します。
アーカイブ処理のタイムアウト | リモート アーカイブ処理のタイムアウト (ミリ秒)。
出力データをコピーします | リモート システムからローカル コンピューターにビルドの出力ファイルをコピーするかどうかを指定します。
