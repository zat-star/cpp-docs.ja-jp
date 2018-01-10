---
title: "リンカ ツール エラー LNK2008 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2008
dev_langs: C++
helpviewer_keywords: LNK2008
ms.assetid: bbcd83c5-c8ae-439e-a033-63643a5bb373
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a7c2fecff55677653c25c7d87fb22fa984526159
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2008"></a>リンカ ツール エラー LNK2008
Fixup ターゲットは、アラインされた 'symbol_name' ではありません。  
  
 リンクは、配置が正しくがないをオブジェクト ファイルに fixup ターゲットを検出します。  
  
 このエラーは、カスタムのセクション配置によって発生することができます (たとえば、#pragma[パック](../../preprocessor/pack.md))、[整列](../../cpp/align-cpp.md)修飾子は、またはセクション配置を変更するアセンブリ言語のコードを使用しています。  
  
 コードは使用しない場合、上記のいずれか、コンパイラこれによる可能性があります。