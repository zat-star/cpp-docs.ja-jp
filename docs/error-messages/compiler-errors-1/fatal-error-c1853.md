---
title: "致命的なエラー C1853 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1853
dev_langs: C++
helpviewer_keywords: C1853
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 23b5302428fc216a8349e8cf022c184caa57202c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1853"></a>致命的なエラー C1853
  
> '*filename*' プリコンパイル済みヘッダー ファイルが以前のバージョンのコンパイラでからまたはプリコンパイル済みヘッダーは、C++ および C から (またはその逆) に使用します。  
  
以下の原因が考えられます。  
  
-   プリコンパイル済みヘッダーは、旧バージョンのコンパイラでコンパイルされました。 現在のコンパイラでヘッダーを再コンパイルしてください。  
  
-   プリコンパイル済みヘッダーは、C++ および C C で使用するヘッダーからのいずれかを指定して使用している、 [/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)コンパイラ オプション、またはソース ファイルのサフィックスの"c"に変更します。 詳細については、次を参照してください。[コードをプリコンパイルする 2 つの選択肢](../../build/reference/creating-precompiled-header-files.md#two-choices-for-precompiling-code)です。