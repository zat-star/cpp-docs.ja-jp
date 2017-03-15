---
title: "デュアル インターフェイスの実装 | Microsoft Docs"
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
  - "デュアル インターフェイス, 実装"
  - "IDispatchImpl クラス, 実装 (デュアル インターフェイスを)"
ms.assetid: d1da3633-b445-4dcd-8a0a-3efdafada3ea
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# デュアル インターフェイスの実装
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

デュアル インターフェイスの `IDispatch` のメソッドの既定の実装を提供する [IDispatchImpl](../atl/reference/idispatchimpl-class.md) のクラスを使用してデュアル インターフェイスを実装できます。  詳細については、「[Implementing the IDispatch Interface](http://msdn.microsoft.com/ja-jp/0e171f7f-0022-4e9b-ac8e-98192828e945)」を参照してください。  
  
 このクラスを使用するには、次の手順に従います。  
  
-   タイプ ライブラリのデュアル インターフェイスを定義します。  
  
-   `IDispatchImpl` \(テンプレート引数としてインターフェイスとタイプ ライブラリに関するパス情報\) の特化したクラスからクラスを派生します。  
  
-   `QueryInterface`によってデュアル インターフェイスを公開するための COM マップにエントリ \(複数可\) を追加します。  
  
-   クラスの vtable インターフェイスの一部を実装します。  
  
-   インターフェイス定義を含むタイプ ライブラリが実行時にオブジェクトで使用できることを確認します。  
  
## ATL シンプル オブジェクト ウィザード  
 次によって、実行時に新しいインターフェイスおよび新しいクラスを作成する場合は、[ATL クラスの追加&#93;ダイアログ ボックス](../ide/add-class-dialog-box.md)と [&#91;ATL シンプル オブジェクト ウィザード&#93;](../atl/reference/atl-simple-object-wizard.md)を使用できます。  
  
## \[インターフェイス実装ウィザード\]  
 既存のインターフェイスがある場合は、必要な基本クラスを追加するに [&#91;インターフェイス実装ウィザード&#93;](../Topic/Adding%20a%20New%20Interface%20in%20an%20ATL%20Project.md) を使用して、既存の COM クラスにエントリとスケルトン メソッドの実装をマップします。  
  
> [!NOTE]
>  タイプ ライブラリのメジャー バージョン番号とマイナー バージョン番号が `IDispatchImpl` の基本クラスにテンプレートの引数として渡すように生成された基本クラスを調整する必要がある場合があります。  インターフェイス実装ウィザードは、のタイプ ライブラリのバージョン番号をチェックしません。  
  
## IDispatch の実行  
 COM マップに該当するエントリを指定することで、ディスパッチ インターフェイスの実装を `IDispatchImpl` の基本クラスを使用して、対応するデュアル インターフェイスを記述するタイプ ライブラリが存在する限り用意するために [COM\_INTERFACE\_ENTRY2](../Topic/COM_INTERFACE_ENTRY2.md) \(または [COM\_INTERFACE\_ENTRY\_IID](../Topic/COM_INTERFACE_ENTRY_IID.md) のマクロを使用\)。  これは、共通 `IDispatch` のインターフェイスを実装するにしたがって、たとえばです。  ATL シンプル オブジェクト ウィザード実装とは `IDispatch` をこのように実行するために適切なマップ エントリの追加とはどちらも想定するウィザードを実装します。  
  
> [!NOTE]
>  ATL は、互換性のあるデュアル インターフェイスの定義を含むタイプ ライブラリを必要とせずに、ディスパッチ インターフェイスを実行できるように [IDispEventImpl](../atl/reference/idispeventimpl-class.md) と [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) のクラスを提供します。  
  
## 参照  
 [デュアル インターフェイスと ATL](../atl/dual-interfaces-and-atl.md)