---
title: "リンカ ツール エラー LNK1223 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1223
dev_langs: C++
helpviewer_keywords: LNK1223
ms.assetid: c4728c36-daee-462f-a1c7-8733dcdec88e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c330077e8de73b8eeb71b0a418eb89d2ec0ebfdc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1223"></a>リンカ ツール エラー LNK1223
ファイルが無効かまたは壊れています: ファイルに無効な .pdata のコントリビューションが含まれています。  
  
 pdata を使用する RISC プラットフォームにおいては、コンパイラによって出力された .pdata セクションのエントリが並べ替えられていない場合に、このエラーが発生します。  
  
 この問題を解決するには、なしでコンパイルしてください[/GL (プログラム全体の最適化)](../../error-messages/tool-errors/linker-tools-error-lnk1223.md)有効にします。 また、このエラーは、関数本体が空である場合にも発生することがあります。