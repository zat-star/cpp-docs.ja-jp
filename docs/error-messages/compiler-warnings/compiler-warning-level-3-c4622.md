---
title: "コンパイラの警告 (レベル 3) C4622 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4622
dev_langs: C++
helpviewer_keywords: C4622
ms.assetid: d3c879f0-4492-4f4b-b26d-230993f3a933
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 52f4491d26cfa56f48ed479b30daeafe9cc01adf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4622"></a>コンパイラの警告 (レベル 3) C4622
オブジェクト ファイル 'file' でデバッグ情報はプリコンパイル済みヘッダーを作成したときに上書きされました  
  
 指定されたファイルの CodeView 情報が、(プリコンパイル済みヘッダーを使用する) [/Yu](../../build/reference/yu-use-precompiled-header-file.md) オプションを指定してコンパイルしたときに失われました。  
  
 プリコンパイル済みヘッダー ファイルを作成または使用する場合は、( [/Fo](../../build/reference/fo-object-file-name.md)を使用して) オブジェクト ファイルの名前を変更し、新しいオブジェクト ファイルを使用してリンクします。