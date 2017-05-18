---
title: "リンカ ツール エラー LNK1245 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1245
dev_langs:
- C++
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 11b00a11f617f8ee5eb17e53510b6f97300298fa
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk1245"></a>リンカ ツール エラー LNK1245
無効なサブシステム 'サブシステム' が指定されてWINDOWS、windows CE、またはコンソール/SUBSYSTEM 必要があります。  
  
 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)オブジェクトをコンパイルするために使用された、次の条件の&1; つは、true を指定します。  
  
-   カスタムのエントリ ポイントが定義されている ([/ENTRY](../../build/reference/entry-entry-point-symbol.md)) ようなリンカーは、サブシステムを推論できませんでした。  
  
-   渡された値、 [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md)リンカー オプションは/clr オブジェクトに対して無効です。  
  
 どちらの場合は、解像度は、/SUBSYSTEM リンカー オプションを有効な値を指定します。
