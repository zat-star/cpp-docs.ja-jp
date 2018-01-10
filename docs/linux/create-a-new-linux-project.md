---
title: "Visual Studio で新しい C++ Linux プロジェクトを作成する | Microsoft Docs"
ms.custom: 
ms.date: 11/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-linux
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d7c1d67-bc31-4f96-8622-2b4cf91372fd
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 8b9eda4c238ae1a3ea3e59d0e5c39ee6b59cff02
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="create-a-new-linux-project"></a>新しい Linux プロジェクトを作成する
Linux のためにコーディングするとき、Visual Studio プロジェクトまたは CMake プロジェクトを作成できます。 このトピックでは、Visual Studio プロジェクトを作成する方法について説明します。 CMake プロジェクトに関する詳細については、「[Linux CMake プロジェクトを構成する](cmake-linux-project.md)」を参照してください。

Visual Studio で新しい Linux プロジェクトを作成するには、次のように操作します。

1. Visual Studio で **[ファイル]、[新しいプロジェクト]** の順に選択するか、**Ctrl + Shift + N** キーを押します。
1. **[Visual C++]、[クロス プラットフォーム]、[Linux]** ノードの順に選択し、作成するプロジェクト タイプを選択して名前と場所を入力し、[OK] をクリックします。

   ![新しい Linux プロジェクト](media/newproject.png)

   | プロジェクトの種類 | 説明
   | ------------ | ---
   | **点滅 (Raspberry)**           | Raspberry Pi デバイスを対象とするプロジェクト。LED を点滅させるようにサンプル コードが記述されています。
   | **C++ コンソール アプリケーション (Linux)** | あらゆる Linux コンピューターを対象とするプロジェクト。コンソールにテキストを出力するようにサンプル コードが記述されています。
   | **空のプロジェクト (Linux)**       | あらゆる Linux コンピューターを対象とするプロジェクト。サンプル コードは記述されていません。
   | **メイクファイル プロジェクト (Linux)**    | 標準のメイクファイル ビルド システムを使用して構築する Linux コンピューターを対象とするプロジェクト。

