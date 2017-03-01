---
title: "致命的なエラー C1902 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1902
dev_langs:
- C++
helpviewer_keywords:
- C1902
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
caps.latest.revision: 13
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: b551b1a7e0ae03a7de5108a1d114155786972847
ms.openlocfilehash: 79987719614dfa3075f9a9090ca1d97f6546ceb3
ms.lasthandoff: 02/24/2017

---
# <a name="fatal-error-c1902"></a>致命的なエラー C1902
プログラム データベース マネージャーが一致しません。インストールを確認してください。  
  
プログラム データベース ファイル (.pdb) は、新しいバージョンの mspdb を使用して作成された*XXX*.dll、コンパイラは、システムで見つかったものです。 このエラー通常またはことを示して mspdbsrv.exe mspdbcore.dll が欠落する mspdb とは異なるバージョンがある*XXX*.dll です。 (、 *XXX* 、mspdb 内のプレース ホルダー*XXX*製品リリースされるたびに .dll ファイルの名前変更します。 たとえば、Visual Studio 2015 でファイル名は mspdb140.dll) です。  
  
一致するバージョン mspdbsrv.exe、mspdbcore.dll、および mspdb のできるように*XXX*.dll は、システムにインストールします。 バージョンが一致しませんが、ターゲット プラットフォームのコンパイラおよびリンクのツールが含まれているディレクトリにコピーされていないことを確認します。 たとえば、するコピーした場合、ファイルが設定されていないコマンド プロンプトから、コンパイラまたはリンクのツールを起動できるように、**パス**環境変数それに応じて。
