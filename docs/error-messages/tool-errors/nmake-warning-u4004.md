---
title: "NMAKE の警告 U4004 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U4004
dev_langs:
- C++
helpviewer_keywords:
- U4004
ms.assetid: 5086bbcb-42d7-4677-a877-1a02202a86a2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fcbda9dd9d7ca5ecb99e46b9916fb95c2c560e49
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-warning-u4004"></a>NMAKE の警告 U4004
ターゲット 'targetname' のルールが多すぎます  
  
 1 つ以上の記述ブロックでは、1 つのコロンを使用して指定されたターゲットが指定されました (**:**) 区切り記号として。 (Nmake の) は、最初の記述ブロックのコマンドを実行し、後のブロックを無視します。  
  
 同じターゲットを複数の依存関係を指定するには、2 つのコロンを使用して (`::`) で各依存関係行区切り記号として。