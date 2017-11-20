---
title: "マクロを定義する場所 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cfb17f531df5c232f1f376cd003acb7bf5a62206
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="where-to-define-macros"></a>マクロを定義する場所
コマンドライン、コマンド ファイル、メイクファイルでも tools.ini マクロを定義します。  
  
 メイクファイルまたは Tools.ini ファイルでは、各マクロ定義は個別の行に表示する必要があり、スペースまたはタブで始めることはできません。スペースや、等号の隣のタブは無視されます。 すべて[文字の文字列](../build/defining-an-nmake-macro.md)リテラルを囲む引用符と埋め込み型スペースなどです。  
  
 コマンドラインまたはコマンド ファイルは、引数を区切るスペースとタブと、等号 (=) を囲むことはできません。 場合`string`スペースまたはタブが埋め込まれる、文字列自体または全体のマクロのいずれかを二重引用符で囲みます ("") です。  
  
## <a name="see-also"></a>関連項目  
 [NMAKE マクロの定義](../build/defining-an-nmake-macro.md)