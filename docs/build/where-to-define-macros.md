---
title: マクロを定義する場所 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c2e646de4cf67fc249d69fb07789f4c8a3e14bf0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="where-to-define-macros"></a>マクロを定義する場所
コマンドライン、コマンド ファイル、メイクファイルでも tools.ini マクロを定義します。  
  
 メイクファイルまたは Tools.ini ファイルでは、各マクロ定義は個別の行に表示する必要があり、スペースまたはタブで始めることはできません。スペースや、等号の隣のタブは無視されます。 すべて[文字の文字列](../build/defining-an-nmake-macro.md)リテラルを囲む引用符と埋め込み型スペースなどです。  
  
 コマンドラインまたはコマンド ファイルは、引数を区切るスペースとタブと、等号 (=) を囲むことはできません。 場合`string`スペースまたはタブが埋め込まれる、文字列自体または全体のマクロのいずれかを二重引用符で囲みます ("") です。  
  
## <a name="see-also"></a>参照  
 [NMAKE マクロの定義](../build/defining-an-nmake-macro.md)