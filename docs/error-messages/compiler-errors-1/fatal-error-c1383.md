---
title: "致命的なエラー C1383 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1383
dev_langs:
- C++
helpviewer_keywords:
- C1383
ms.assetid: ca224d14-d687-4fd6-80c2-8b82f28924ea
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ff620211470e82cd53a893bdee94fb1ca5d405c9
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="fatal-error-c1383"></a>致命的なエラー C1383
コンパイラ オプション /GL は、インストールされた共通言語ランタイムのバージョンと互換性がありません  
  
 C1383 は、共通言語ランタイムの以前のバージョンをそれより新しいコンパイラで使用しているときに、 **/clr** と **/GL.**を指定してコンパイルすると発生します。  
  
 解決するには、 **/GL** を **/clr** と共に使用しないようにするか、使用しているコンパイラに付属している共通言語ランタイムのバージョンをインストールします。  
  
 詳細については、 [/clr (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) および [/GL (Whole Program Optimization)](../../build/reference/gl-whole-program-optimization.md)を参照してください。
