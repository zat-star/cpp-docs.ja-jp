---
title: "プロセス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: process_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], process
- process __declspec keyword
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6754adcb348cb6eb061e32fc58e78f43663b1a90
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="process"></a>process
マネージ アプリケーション プロセスが、プロセス内のすべてのアプリケーション ドメイン間で共有される特定のグローバル変数、静的メンバー変数、または静的ローカル変数のコピーを 1 つ持つことを指定します。 これは、主に使用するためでコンパイルするときに**/clr: 純粋な**ため、 **/clr: 純粋な**グローバルと静的変数は、既定では、アプリケーション ドメインごとです。 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で使用されていません。 コンパイルするときに**/clr**、グローバル変数と静的変数は既定ではプロセスごと (を使用する必要はありません`__declspec(process)`です。  
  
 `__declspec(process)` でマークできるのは、グローバル変数、静的メンバー変数、またはネイティブ型の静的ローカル変数だけです。  
  
 コンパイルするときに**/clr: 純粋な**、としてプロセスに従ってマークされている変数を宣言する必要がありますも`const`します。 これにより、プロセスごとの変数は 1 つのアプリケーション ドメイン内で変更されなくなり、他のアプリケーション ドメインに予測できない結果を与えることもなくなります。 主な用途`__declspec(process)`グローバル変数、静的メンバー変数、または静的ローカル変数のコンパイル時の初期化を有効にするのには、 **/clr: 純粋な**します。  
  
 `process`コンパイルする場合にのみ有効[/clr](../build/reference/clr-common-language-runtime-compilation.md)または**/clr: 純粋な**でコンパイルするときは無効と**/clr:safe**です。  
  
 使用する場合は、グローバル変数の独自のコピーが存在する場合は、各アプリケーション ドメイン、 [appdomain](../cpp/appdomain.md)です。  
  
 参照してください[アプリケーション ドメインと Visual C](../dotnet/application-domains-and-visual-cpp.md)詳細についてはします。  
  
## <a name="see-also"></a>参照  
 [_ _declspec](../cpp/declspec.md)   
 [キーワード](../cpp/keywords-cpp.md)