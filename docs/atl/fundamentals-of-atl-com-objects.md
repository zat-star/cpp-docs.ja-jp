---
title: "ATL COM オブジェクトの基本事項 | Microsoft Docs"
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
  - "ATL COM オブジェクト"
  - "ATL, COM"
  - "COM オブジェクト, ATL"
  - "COM, および ATL"
ms.assetid: 0f9c9d98-cc28-45da-89ac-dc94cee422fe
caps.latest.revision: 25
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL COM オブジェクトの基本事項
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次の図は、ATL COM オブジェクトの定義に使用するクラスとインターフェイスとの関係を示しています。  
  
 ![ATL 構造](../atl/media/vc307y1.png "vc307Y1")  
  
> [!NOTE]
>  この図は、`CComObject` が `CYourClass` から派生し、`CComAggObject` および `CComPolyObject` に `CYourClass` がメンバー変数として含まれていることを示しています。  
  
 ATL COM オブジェクトを定義するには、3 とおりの方法があります。  標準的な方法は、`CYourClass` から派生する `CComObject` クラスを使用する方法です。  2 つ目は、`CComAggObject` クラスを使用して集約オブジェクトを作成する方法です。  3 つ目は、`CComPolyObject` クラスを使用する方法です。  `CComPolyObject` はハイブリッドとして動作します。つまり、最初に作成された方法に応じて、`CComObject` クラスまたは `CComAggObject` クラスとして機能します。  `CComPolyObject` クラスの使用方法の詳細については、「[CComPolyObject クラス](../atl/reference/ccompolyobject-class.md)」を参照してください。  
  
 標準 ATL COM を使用する場合は、外部オブジェクトと内部オブジェクトの 2 つのオブジェクトを使用します。  外部クライアントは、外部オブジェクトで定義されたラッパー関数を通じて内部オブジェクトの機能にアクセスします。  外部オブジェクトの型は `CComObject` です。  
  
 集約オブジェクトを使用する場合、外部オブジェクトは、内部オブジェクトの機能に対するラッパーを提供しません。  代わりに、外部オブジェクトは、外部クライアントによって直接アクセスされるポインターを提供します。  このシナリオでは、外部オブジェクトの型は `CComAggObject` です。  内部オブジェクトは、外部オブジェクトのメンバー変数であり、その型は `CYourClass` です。  
  
 クライアントは内部オブジェクトと対話する際に外部オブジェクトを経由する必要がないため、通常は集約オブジェクトの方が効率的です。  また、集約オブジェクトのインターフェイスがクライアントから直接使用可能であれば、外部オブジェクトは集約オブジェクトの機能を認識する必要がありません。  ただし、すべてのオブジェクトを集約できるとは限りません。  オブジェクトを集約するには、そのオブジェクトが集約を考慮してデザインされている必要があります。  
  
 ATL は、次の 2 段階で [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) を実装します。  
  
-   [CComObject](../atl/reference/ccomobject-class.md)、[CComAggObject](../atl/reference/ccomaggobject-class.md)、または [CComPolyObject](../atl/reference/ccompolyobject-class.md) が、**IUnknown** メソッドを実装します。  
  
-   [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) または [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) が、**IUnknown** の参照カウントと外部ポインターを管理します。  
  
 ATL COM オブジェクトのその他の部分は、ほかのクラスで処理します。  
  
-   [CComCoClass](../Topic/CComCoClass%20Class.md) は、オブジェクトの既定のクラス ファクトリと集約モデルを定義します。  
  
-   [IDispatchImpl](../atl/reference/idispatchimpl-class.md) は、オブジェクトのデュアル インターフェイスの `IDispatch Interface` 部分について、既定の実装を用意します。  
  
-   [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) は、エラー情報が正しく呼び出しチェイン上に反映されるか確認する **ISupportErrorInfo** インターフェイスを実装します。  
  
## このセクションの内容  
 [CComObjectRootEx の実装](../Topic/Implementing%20CComObjectRootEx.md)  
 `CComObjectRootEx` を実装するための COM マップ エントリの例を示します。  
  
 [CComObject、CComAggObject、および CComPolyObject の実装](../atl/implementing-ccomobject-ccomaggobject-and-ccompolyobject.md)  
 **DECLARE\_\*\_AGGREGATABLE** マクロが `CComObject`、`CComAggObject`、および `CComPolyObject` にどのように影響するかについて説明します。  
  
 [IDispatch と IErrorInfo のサポート](../atl/supporting-idispatch-and-ierrorinfo.md)  
 `IDispatch` インターフェイスと **IErrorInfo** インターフェイスのサポートに使用する ATL 実装クラスを示します。  
  
 [IDispEventImpl のサポート](../atl/supporting-idispeventimpl.md)  
 クラスに対するコネクション ポイントの実装手順について示します。  
  
 [既定のクラス ファクトリと集約モデルの変更](../atl/changing-the-default-class-factory-and-aggregation-model.md)  
 既定のクラス ファクトリおよび集約モデルの変更に使用するマクロを示します。  
  
 [集約オブジェクトの作成](../atl/creating-an-aggregated-object.md)  
 集約オブジェクトの作成手順を示します。  
  
## 関連項目  
 [ATL プロジェクトの作成](../atl/reference/creating-an-atl-project.md)  
 ATL COM オブジェクトの作成に関する情報を提供します。  
  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Active Template Library を使用したプログラミングの概念を説明するトピックへのリンクを示します。  
  
## 参照  
 [概念](../atl/active-template-library-atl-concepts.md)