---
title: "致命的なエラー C1902 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1902
dev_langs: C++
helpviewer_keywords: C1902
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 89354565f67c8704eee8c8b5f9dcb94523800c63
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1902"></a>致命的なエラー C1902
プログラム データベース マネージャーが一致しません。インストールを確認してください。  
  
プログラム データベース ファイル (.pdb) が新しいバージョンの mspdb を使用して作成された*XXX*.dll、コンパイラは、システムで見つかったものです。 このエラーは、通常 mspdbsrv.exe または mspdbcore.dll が見つからないか、mspdb とは異なるバージョンがあることに示す*XXX*.dll です。 (、 *XXX* 、mspdb 内のプレース ホルダー*XXX*製品リリースされるたびに .dll ファイル名の変更。 例については、Visual Studio 2015 では、ファイル名は mspdb140.dll です。)  
  
Mspdbsrv.exe、mspdbcore.dll、および mspdb の一致するバージョンを確認してください*XXX*.dll は、システムにインストールします。 バージョンが一致しませんが、ターゲット プラットフォームのコンパイラおよびリンクのツールが含まれているディレクトリにコピーされていないことを確認します。 たとえば、可能性がありますがファイルをコピーした、設定を指定せず、コマンド プロンプトから、コンパイラやリンク ツールを起動できるように、**パス**環境変数に応じて。