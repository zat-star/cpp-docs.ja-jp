---
title: "ATL のコレクションと列挙子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コレクション インターフェイス"
  - "コレクション, ATL クラス"
  - "列挙子インターフェイス"
  - "列挙子, ATL クラス"
ms.assetid: b2d37119-3ab2-4e0a-b65b-f377f07e4098
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL のコレクションと列挙子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`collection` は、データ項目 \(生データなどのオブジェクト\) のグループへのアクセスを許可するインターフェイスを提供する COM オブジェクトです。  オブジェクトのグループへのアクセスを提供する標準に準拠のインターフェイスは、*コレクションのインターフェイス*と呼びます。  
  
 少なくとも、コレクション インターフェイスのコレクションは、インデックスに基づいてコレクションの項目を返すとコレクションの列挙子を返す `_NewEnum` のプロパティ返す **\[アイテム\]** のプロパティ項目の数を **Count** のプロパティを提供する必要があります。  オプションで、コレクションのインターフェイスは、**\[クリア\]** のメソッドを **追加** と項目がに挿入またはすべての項目を削除するには、コレクションから削除されるように **\[削除\]** のメソッドを提供します。  
  
 `enumerator` はコレクション内の項目を反復処理するためのインターフェイスを提供する COM オブジェクトです。  列挙子インターフェイスは 4 個の要求されたメソッドによってコレクションの要素への順次アクセスを提供します: `Next`、**\[スキップ\]**、**\[リセット\]**と `Clone`。  
  
 [IEnumXXXX](https://msdn.microsoft.com/en-us/library/ms680089.aspx) の原型的な \(完全に\) とインターフェイスについて説明します。して列挙子インターフェイスについて学習できます。  
  
## このセクションの内容  
 [ATL のコレクションと列挙子クラス](../atl/atl-collection-and-enumerator-classes.md)  
 簡単に説明しすると、列挙子がコレクションを実行できる ATL クラスについて説明し、リンクを提供します。  
  
 [コレクションと列挙子インターフェイスのデザイン原則](../atl/design-principles-for-collection-and-enumerator-interfaces.md)  
 インターフェイスの種類に関するさまざまなデザイン原則について説明します。  
  
 [STL ベースのコレクションの実行](../atl/implementing-an-stl-based-collection.md)  
 標準テンプレート ライブラリの \(STL\) のベースのコレクションの実装によって拡張する例です。  
  
## 関連項目  
 [&#91;ATL&#93;](../atl/active-template-library-atl-concepts.md)  
 Active Template Library を使用したプログラミングの概念を説明するトピックへのリンクを示します。  
  
 ATLCollections sample  
 `ICollectionOnSTLImpl` と `CComEnumOnSTL`の使用方法を示すサンプル、およびカスタム コピー ポリシー クラスの実装します。  
  
## 参照  
 [概念](../atl/active-template-library-atl-concepts.md)