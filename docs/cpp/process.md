---
title: "プロセス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- process_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], process
- process __declspec keyword
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2c50948d613a40a03d0249e1930943ef61c855b9
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="process"></a>process
マネージ アプリケーション プロセスが、プロセス内のすべてのアプリケーション ドメイン間で共有される特定のグローバル変数、静的メンバー変数、または静的ローカル変数のコピーを 1 つ持つことを指定します。 これが、主に使用するためでコンパイルするときに**/clr: 純粋な**、廃止し、コンパイラの将来のバージョンで削除される予定です。 コンパイルするときに**/clr**、グローバル変数と静的変数は既定ではプロセスごと (を使用する必要はありません`__declspec(process)`です。  
  
 `__declspec(process)` でマークできるのは、グローバル変数、静的メンバー変数、またはネイティブ型の静的ローカル変数だけです。  
  
  
 `process` コンパイルするときに、有効なのみ[/clr](../build/reference/clr-common-language-runtime-compilation.md)です。  
  
 使用する場合は、グローバル変数の独自のコピーが存在する場合は、各アプリケーション ドメイン、 [appdomain](../cpp/appdomain.md)です。  
  
 参照してください[アプリケーション ドメインと Visual C](../dotnet/application-domains-and-visual-cpp.md)詳細についてはします。  
  
## <a name="see-also"></a>参照  
 [__declspec](../cpp/declspec.md)   
 [キーワード](../cpp/keywords-cpp.md)