---
title: "アプリケーション ドメインと Visual C |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- interop [C++], application domains
- application domains [C++], C++
- /clr compiler option [C++], application domains
- interoperability [C++], application domains
- mixed assemblies [C++], application domains
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a66731b9645458441f1c3e1f211c74be698e7231
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="application-domains-and-visual-c"></a>アプリケーション ドメインと Visual C++
ある場合、`__clrcall`仮想関数は、vtable なりますあたりのアプリケーション ドメイン (appdomain)。 1 つの appdomain でオブジェクトを作成する場合は、appdomain 内から仮想関数のみ呼び出すことができます。 定義されたすべての関数**/clr: 純粋な**コンパイル単位を使用して、`__clrcall`呼び出し規約です。 すべての vtable がで定義されているため、 **/clr: 純粋な**appdomain ごとのコンパイル単位です。 混在モードで (**/clr**)、型を持たない場合プロセス vtable あたりが`__clrcall`仮想関数。 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で使用されていません。  
  
 詳細については、次のトピックを参照してください。  
  
-   [appdomain](../cpp/appdomain.md)  
  
-   [__clrcall](../cpp/clrcall.md)  
  
-   [方法:/clr:pure に移行: 純粋な (C + + CLI)](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)  
  
-   [process](../cpp/process.md)  
  
## <a name="see-also"></a>参照  
 [混在 (ネイティブおよびマネージ) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)