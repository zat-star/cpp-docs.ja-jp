---
title: "プロジェクト ビルド エラー PRJ0009 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0009
dev_langs: C++
helpviewer_keywords: PRJ0009
ms.assetid: 89291778-cda4-495d-983f-ddcc06dfc98b
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0ee183c24cf330b54a335efbd0bbe2b00e18d209
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0009"></a>プロジェクト ビルド エラー PRJ0009
ビルドを書き込み用ログを開くことができませんでした。  
  
 **ファイルが別のプロセスによって開かれていないと、書き込み保護されていないことを確認してください。**  
  
 設定した後、**ビルドのログ**プロパティを**はい**ビルドまたはリビルドを実行する、Visual C なしで排他モードでは、ビルド ログを開くことができません。  
  
 検査、**ビルドのログ**設定を開いて、**オプション** ダイアログ ボックス (上、**ツール** メニューのをクリックして**オプション**コマンド) し、選択すると**vc++ ビルド**で、**プロジェクト**フォルダーです。 ビルド ファイルを使用して、BuildLog.htm 呼びます、中間ディレクトリ $(IntDir) に書き込まれます。  
  
 このエラーの考えられる理由:  
  
-   Visual C の 2 つのプロセスを実行している同時に、同じ構成の両方で同じプロジェクトをビルドしようとしています。  
  
-   ビルド ログ ファイルは、ファイルをロックするプロセスで開かれます。  
  
-   ユーザーには、ファイルを作成するアクセス許可がありません。  
  
-   現在のユーザーには、BuildLog.htm ファイルに書き込みアクセス権がありません。