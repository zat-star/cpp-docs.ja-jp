---
title: "ATL COM プロパティ ページ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL COM オブジェクト"
  - "ATL プロパティ ページ"
  - "COM オブジェクト, ATL"
  - "COM プロパティ ページ"
  - "プロパティ ページ, ATL"
  - "プロパティ ページ, COM"
ms.assetid: 663c7caa-2e5e-4b5c-b8ea-fd434ceb1654
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# ATL COM プロパティ ページ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

COM プロパティ ページには、一つ以上の COM オブジェクトのプロパティを設定またはメソッドを呼び出す\) ユーザー インターフェイスを提供します。  プロパティ ページには、コントロールのプロパティをデザイン時に設定できる豊富なユーザー インターフェイスを提供する ActiveX コントロールで広く使用されています。  
  
 プロパティ ページは [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) または [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996) のインターフェイスを実装する COM オブジェクトです。  これらのインターフェイスは、ページが `site` \(ページのコンテナーを表す COM オブジェクト\) といくつかの *オブジェクト* \(とメソッドがプロパティ ページのユーザーが行った変更に対する応答として呼び出される関連付けられている COM オブジェクト\) ようにするメソッドを提供します。  プロパティ ページのコンテナーは、ページを通知するためにプロパティ ページのインターフェイスでメソッドを呼び出します。いつユーザー インターフェイスを表示または非表示にするときと、ユーザーが行ったなるオブジェクトへの変更を追加するときにします。  
  
 各プロパティ ページには、プロパティを設定できるオブジェクトとは関係なく完全にビルドできます。  プロパティ ページで必要なすべて、特定のインターフェイス \(またはインターフェイスのセット\) を理解し、そのインターフェイスでメソッドを呼び出すためのユーザー インターフェイスを提供することです。  
  
 詳細については、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]の [プロパティ シート、プロパティ ページ](http://msdn.microsoft.com/library/windows/desktop/ms686577) を参照してください。  
  
## このセクションの内容  
 [プロパティ ページの指定](../atl/specifying-property-pages.md)  
 、のプロパティ ページを指定する手順を示し、コントロール クラスの例を示します。  
  
 [プロパティ ページの実装](../atl/implementing-property-pages.md)  
 メソッドを含むプロパティ ページをオーバーライドするために実装手順を示します。  ウォーク ATLPages サンプル プログラムに基づく完全な例で。  
  
## 関連項目  
 [ATLPages サンプル](../top/visual-cpp-samples.md)  
 `IPropertyPageImpl`を使用したプロパティ ページの実装する ATLPages サンプルの例を示します。  
  
 [&#91;ATL&#93;](../atl/active-template-library-atl-concepts.md)  
 Active Template Library を使用したプログラミングの概念を説明するトピックへのリンクを示します。  
  
## 参照  
 [概念](../atl/active-template-library-atl-concepts.md)