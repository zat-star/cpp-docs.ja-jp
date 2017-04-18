---
title: "致命的なエラー C1383 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: bbd890a7506059f939ca6d8957f71e20cba771f8
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1383"></a>致命的なエラー C1383
コンパイラ オプション /GL は、インストールされた共通言語ランタイムのバージョンと互換性がありません  
  
 C1383 は、共通言語ランタイムの以前のバージョンをそれより新しいコンパイラで使用しているときに、 **/clr** と **/GL.**を指定してコンパイルすると発生します。  
  
 解決するには、 **/GL** を **/clr** と共に使用しないようにするか、使用しているコンパイラに付属している共通言語ランタイムのバージョンをインストールします。  
  
 詳細については、次を参照してください。 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)と[/GL (プログラム全体の最適化)](../../build/reference/gl-whole-program-optimization.md)です。
