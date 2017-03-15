---
title: "STL/CLR ライブラリ リファレンス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cliext ディレクトリ"
  - "STL/CLR ライブラリ"
  - "STL/CLR, 再配布"
ms.assetid: a9d9ca00-7bf2-48c1-b205-3ae6f8c25f82
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# STL/CLR ライブラリ リファレンス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

STL\/CLR ライブラリは、標準 C\+\+ ライブラリのサブセットである標準テンプレート ライブラリ \(STL: Standard Template Library\) のパッケージであり、C\+\+ と .NET Framework の共通言語ランタイム \(CLR: Common Language Runtime\) で使用します。  STL\/CLR を使用すると、マネージ環境で STL のすべてのコンテナー、反復子、およびアルゴリズムを利用できます。  
  
 STL\/CLR を使用するには  
  
-   **cliext** の Include ヘッダーには、通常の Standard C\+\+ ライブラリではなくサブディレクトリが含まれています。  
  
-   ライブラリ名は、`std::` ではなく `cliext::` で修飾します。  
  
 STL\/CLR は、.NET アセンブリ **Microsoft.VisualC.STLCLR.dll** のアセンブリ間シナリオで使用されるジェネリック型とインターフェイスを開示します。  この DLL は、.NET Framework 3.5 に含まれています。  STL\/CLR を使用するアプリケーションを再配布する場合、.NET Framework 3.5 とプロジェクトで使用する他のすべての Visual C\+\+ ライブラリをセットアップ プロジェクトの依存関係セクションに含める必要があります。  
  
## このセクションの内容  
 [cliext 名前空間](../Topic/cliext%20Namespace.md)  
 STL\/CLR ライブラリのすべての型を含む名前空間について説明します。  
  
 [STL\/CLR コンテナー](../dotnet/stl-clr-containers.md)  
 コンテナー要素の要件、挿入できる要素の種類、所有権の問題など、標準 C\+\+ ライブラリにあるコンテナーの概要を説明します。  
  
 [STL\/CLR コンテナー要素の要件](../Topic/Requirements%20for%20STL-CLR%20Container%20Elements.md)  
 STL コンテナーに挿入されるすべての参照型の最小要件について説明します。  
  
 [方法: .NET コレクションを STL\/CLR コンテナーに変換する](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)  
 .NET コレクションを STL\/CLR コンテナーに変換する方法について説明します。  
  
 [方法: STL\/CLR コンテナーを .NET コレクションに変換する](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)  
 STL\/CLR コンテナーを .NET コレクションに変換する方法について説明します。  
  
 [方法: アセンブリから STL\/CLR コンテナーを公開する](../dotnet/how-to-expose-an-stl-clr-container-from-an-assembly.md)  
 C\+\+ アセンブリで記述された複数の STL\/CLR コンテナー要素を表示する方法を示します。  
  
 また、このセクションでは STL\/CLR の次のコンポーネントについても説明します。  
  
|||  
|-|-|  
|[adapter](../dotnet/adapter-stl-clr.md)|[algorithm](../Topic/algorithm%20\(STL-CLR\).md)|  
|[deque](../dotnet/deque-stl-clr.md)|[for each、in](../dotnet/for-each-in.md)|  
|[functional](../dotnet/functional-stl-clr.md)|[hash\_map](../dotnet/hash-map-stl-clr.md)|  
|[hash\_multimap](../dotnet/hash-multimap-stl-clr.md)|[hash\_multiset](../dotnet/hash-multiset-stl-clr.md)|  
|[hash\_set](../dotnet/hash-set-stl-clr.md)|[一覧](../dotnet/list-stl-clr.md)|  
|[マップ](../dotnet/map-stl-clr.md)|[multimap](../dotnet/multimap-stl-clr.md)|  
|[multiset](../dotnet/multiset-stl-clr.md)|[数値](../dotnet/numeric-stl-clr.md)|  
|[priority\_queue](../Topic/priority_queue%20\(STL-CLR\).md)|[キュー](../Topic/queue%20\(STL-CLR\).md)|  
|[設定](../dotnet/set-stl-clr.md)|[スタック](../dotnet/stack-stl-clr.md)|  
|[utility](../dotnet/utility-stl-clr.md)|[ベクター](../dotnet/vector-stl-clr.md)|  
  
## 参照  
 [C\+\+ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)