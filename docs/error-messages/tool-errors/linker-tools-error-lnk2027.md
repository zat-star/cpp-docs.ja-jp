---
title: "リンカ ツール エラー LNK2027 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2027
dev_langs: C++
helpviewer_keywords: LNK2027
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b9cefb948ffd09421a6d4a9c1c540ef22f8736fc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk2027"></a>リンカ ツール エラー LNK2027
未解決のモジュール参照 ' module'  
  
 リンカーに渡されたファイルで指定されているモジュールに依存している**/ASSEMBLYMODULE**もリンカーに直接渡されません。  
  
 Lnk2027 エラーを解決するには、次のいずれかの操作を行います。  
  
-   渡さないでくださいリンカーをモジュールの依存関係を持つファイルです。  
  
-   モジュールを指定**/ASSEMBLYMODULE**です。  
  
-   モジュールが安全な .netmodule の場合は、モジュールをリンカーに直接渡します。  
  
 詳細については、次を参照してください。 [/ASSEMBLYMODULE (MSIL モジュールをアセンブリに追加)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)と[リンカー入力としての .netmodule ファイル](../../build/reference/netmodule-files-as-linker-input.md)です。