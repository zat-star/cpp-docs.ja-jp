---
title: "致命的なエラー C1853 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1853
dev_langs:
- C++
helpviewer_keywords:
- C1853
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
caps.latest.revision: 10
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: d312a819b5e91386d805635fdd588b72ee842cfe
ms.lasthandoff: 02/24/2017

---
# <a name="fatal-error-c1853"></a>致命的なエラー C1853
'filename' プリコンパイル済みヘッダー ファイルには、コンパイラの以前のバージョンまたはプリコンパイル済みヘッダーは、C++ および C から (またはその逆) に使用します。  
  
 以下の原因が考えられます。  
  
-   プリコンパイル済みヘッダーは、旧バージョンのコンパイラでコンパイルされました。 現在のコンパイラでヘッダーを再コンパイルしてください。  
  
-   プリコンパイル済みヘッダーは、C++ および C C で使用するためのヘッダーからのいずれかを指定して使用している、 [/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)コンパイラ オプション、または"c"にソース ファイルのサフィックスを変更します。 詳細については、次を参照してください。[コードをプリコンパイルする&2; つの選択肢](../../build/reference/two-choices-for-precompiling-code.md)します。
