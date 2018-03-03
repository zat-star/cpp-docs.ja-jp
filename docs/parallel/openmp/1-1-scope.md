---
title: "1.1 スコープ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: a8570a3c-1dd6-4c3d-b368-a10fcb3534a6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 07859a95b739cf649ab6516cb2e8b605efe442dc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="11-scope"></a>1.1 スコープ
この仕様では、ユーザーが明示的に並列でプログラムを実行するために、コンパイラとランタイム システムで実行されるアクションを指定、のみのユーザー向けの並列について説明します。 OpenMP C および C++ の実装は、依存関係、競合、デッドロック、競合状態、または正しくないプログラムの実行と、その他の問題を確認する必要はありません。 ユーザーは、OpenMP C および C++ API コンストラクトを使用して、アプリケーションが正しく実行されることを保証します。 コンパイラによって生成された自動並列化し、このような並列処理を支援するために、コンパイラ ディレクティブは、このドキュメントでは説明しません。