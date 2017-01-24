---
title: "ウィンドウの特徴について | Microsoft Docs"
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
  - "ウィンドウの特徴"
ms.assetid: c90cf850-9e91-49da-9cf3-ad4efb30347d
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ウィンドウの特徴について
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ウィンドウの特性のクラスは、ATL ウィンドウ オブジェクトの作成に使用するスタイルを標準化するための簡単な方法を提供します。  ウィンドウの特性は [CWindowImpl](../Topic/CWindowImpl%20Class.md) によってテンプレート パラメーターとクラス レベルの既定のウィンドウ スタイルを提供する方法として、他の ATL ウィンドウ クラスとして使用されます。  
  
 ウィンドウのインスタンスの作成者が [&#91;作成&#93;](../Topic/CWindowImpl::Create.md)の呼び出しでスタイルを明示的に指定するウィンドウが正しいスタイルで作成されるようにするために、並べ替え特性を使用できます。  インスタンスごとに設定する他のスタイルの中に特定のスタイルがそのウィンドウ クラスのすべてのインスタンスに設定されていることを確認できます。  
  
## ATL ウィンドウの特性のテンプレート  
 ATL はテンプレート パラメーターを使用して、コンパイル時に既定のスタイルを設定できる 2 種類のウィンドウ特性のテンプレートが用意されています。  
  
|Class|説明|  
|-----------|--------|  
|[CWinTraits](../atl/reference/cwintraits-class.md)|他のスタイルが **\[作成\]**への呼び出しで指定されていない場合にのみ使用される既定のウィンドウ スタイルを指定する場合は、このテンプレートを使用します。  実行時に指定されたスタイルはコンパイル時に設定されているスタイルに優先されます。|  
|[CWinTraitsOR](../atl/reference/cwintraitsor-class.md)|ウィンドウ クラスに対して常に設定するスタイルを指定する場合は、このクラスを使用します。  実行時に指定されたスタイルはビットごとに設定されているスタイルと OR 演算子を使用して、コンパイル時に結合されます。|  
  
 これらのテンプレートに加えて、ATL はウィンドウ スタイルの一般的な組み合わせに `CWinTraits` テンプレートの一部の定義済み特殊な形式を指定します。  詳細については [CWinTraits](../atl/reference/cwintraits-class.md) のリファレンス ドキュメントを参照してください。  
  
## カスタム ウィンドウの特性  
 ATL によって提供されるテンプレートの 1 を特化することが十分ではなく、独自の特性クラスを作成する必要があるほとんどない状態では、実装する 2 種類の静的関数を実装するクラスを作成する必要があります: `GetWndStyle` と **GetWndStyleEx**:  
  
 [!code-cpp[NVC_ATL_Windowing#68](../atl/codesnippet/CPP/understanding-window-traits_1.h)]  
  
 これらの関数は値の新しいスタイルの値を生成するために使用できる、実行時に渡されます。  、ウィンドウの特性のクラスが ATL ウィンドウ クラスへのテンプレート引数として使用する場合は、スタイル値は、これらの静的関数に渡された内容が、[&#91;作成&#93;](../Topic/CWindowImpl::Create.md)にスタイル引数として渡されたです。  
  
## 参照  
 [ウィンドウ クラス](../Topic/ATL%20Window%20Classes.md)