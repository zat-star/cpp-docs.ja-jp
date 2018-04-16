---
title: "Null と未定義マクロ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, undefined macros
- Null macros in NMAKE
- macros, null and undefined
- undefined macros and NMAKE
- NMAKE program, null macros
ms.assetid: 1db4611a-1755-4328-b00f-d35365af8b6c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9581b152057655c510f1cbcd4ab29ba8339070b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="null-and-undefined-macros"></a>Null マクロと未定義マクロ
Null と未定義の両方のマクロが null の文字列への展開が、null 文字列として定義されているマクロは、プリプロセス式で定義されていると見なされます。 マクロを定義する、null 文字列として、指定文字を含まないがコマンドラインまたはコマンド ファイルに等号 (=) の後のスペースまたはタブを除くし、null 文字列または定義を二重引用符で囲みます ("") です。 マクロを未定義を使用して**!UNDEF です。** 詳細については、次を参照してください。[メイクファイルのプリプロセス ディレクティブ](../build/makefile-preprocessing-directives.md)です。  
  
## <a name="see-also"></a>参照  
 [NMAKE マクロの定義](../build/defining-an-nmake-macro.md)