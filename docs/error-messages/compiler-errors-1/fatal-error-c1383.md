---
title: "致命的なエラー C1383 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1383
dev_langs: C++
helpviewer_keywords: C1383
ms.assetid: ca224d14-d687-4fd6-80c2-8b82f28924ea
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 24e9d7652c96c84f94bafbf2c808f2e5430037b2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1383"></a>致命的なエラー C1383
コンパイラ オプション /GL は、インストールされた共通言語ランタイムのバージョンと互換性がありません  
  
 C1383 は、共通言語ランタイムの以前のバージョンをそれより新しいコンパイラで使用しているときに、 **/clr** と **/GL.**を指定してコンパイルすると発生します。  
  
 解決するには、 **/GL** を **/clr** と共に使用しないようにするか、使用しているコンパイラに付属している共通言語ランタイムのバージョンをインストールします。  
  
 詳細については、 [/clr (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) および [/GL (Whole Program Optimization)](../../build/reference/gl-whole-program-optimization.md)を参照してください。