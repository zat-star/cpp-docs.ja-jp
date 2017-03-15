---
title: "ATL (Active Template Library) の概念 | Microsoft Docs"
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
  - "[ATL], 概要 (ATL の)"
ms.assetid: a3960991-4d76-4da5-9568-3fa7fde53ff4
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# ATL (Active Template Library) の概念
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL \(Active Template Library\) は、テンプレート ベースの一連の C\+\+ クラスです。これらの C\+\+ クラスを使用することにより、小規模で、高速なコンポーネント オブジェクト モデル \(COM: Component Object Model\) オブジェクトを作成できます。  ATL では、ストック実装、デュアル インターフェイス、標準の COM 列挙子インターフェイス、コネクション ポイント、ティアオフ インターフェイス、ActiveX コントロールなど、重要な COM 機能を特別にサポートしています。  
  
 ATL プログラミングを大量に行う場合は、COM プログラミングを簡単にするためにデザインされた、Visual C\+\+ .NET の新機能である属性について習得します。  詳細については、「[属性付きプログラミング](../windows/attributed-programming-concepts.md)」を参照してください。  
  
## このセクションの内容  
 [ATL チュートリアル](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)  
 ATL の基本に関する説明を交えながら、コントロールの作成手順を紹介します。  
  
 [COM および ATL の概要](../atl/introduction-to-com-and-atl.md)  
 コンポーネント オブジェクト モデル \(COM: Component Object Model\) の背後にある主要な概念を紹介します。  ここでは、ATL の意味や使用する時期についても簡単に説明します。  
  
 [ATL COM オブジェクトの基本事項](../atl/fundamentals-of-atl-com-objects.md)  
 さまざまな ATL クラス間の関係と、クラスの実装方法について説明します。  
  
 [デュアル インターフェイスと ATL](../atl/dual-interfaces-and-atl.md)  
 デュアル インターフェイスを ATL の観点から説明します。  
  
 [ATL のコレクションと列挙子](../atl/atl-collections-and-enumerators.md)  
 ATL のコレクションと列挙子の実装および作成について説明します。  
  
 [複合コントロールの基本](../Topic/ATL%20Composite%20Control%20Fundamentals.md)  
 複合コントロールを作成するための手順について説明します。  複合コントロールは ActiveX コントロールの一種であり、ほかの ActiveX コントロールまたは Windows コントロールを含むことができます。  
  
 [ATL コントロール コンテインメントの FAQ](../atl/atl-control-containment-faq.md)  
 ATL によるコントロール ホストに関する基本的な Q & A 集を紹介します。  
  
 [ATL COM プロパティ ページ](../atl/atl-com-property-pages.md)  
 COM プロパティ ページの指定と実装の方法を示します。  
  
 [DHTML コントロールに対する ATL のサポート](../atl/atl-support-for-dhtml-controls.md)  
 DHTML コントロールを作成するための詳細な手順について説明します。  
  
 [ATL コネクション ポイント](../atl/atl-connection-points.md)  
 コネクション ポイントの意味や ATL のコネクション ポイントの実装について説明します。  
  
 [イベント処理と ATL](../Topic/Event%20Handling%20and%20ATL.md)  
 ATL の [IDispEventImpl](../atl/reference/idispeventimpl-class.md) クラスと [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) クラスを使用して COM イベントを処理するために必要な手順について説明します。  
  
 [ATL とフリー スレッド マーシャラー](../Topic/ATL%20and%20the%20Free%20Threaded%20Marshaler.md)  
 クラスでフリー スレッド マーシャラー \(FTM: Free Threaded Marshaler\) を集約できるようにする、ATL シンプル オブジェクト ウィザードのオプションの詳細について説明します。  
  
 [プロジェクトのスレッド モデルの指定](../atl/specifying-the-threading-model-for-a-project-atl.md)  
 プロジェクトのスレッド処理に関連して実行時のパフォーマンスを制御するために使用できるマクロについて説明します。  
  
 [ATL モジュール クラス](../Topic/ATL%20Module%20Classes.md)  
 ATL 7.0 の新しいモジュール クラスについて説明します。  モジュール クラスは、ATL で必要とされる基本機能を実装します。  
  
 [ATL サービス](../atl/atl-services.md)  
 サービスが実装されるときに発生する一連のイベントについて説明します。  サービスの開発に関連する概念についても説明します。  
  
 [ATL ウィンドウ クラス](../Topic/ATL%20Window%20Classes.md)  
 ATL でウィンドウを作成、スーパークラス化、およびサブクラス化する方法について説明します。  ATL ウィンドウ クラスは COM クラスではありません。  
  
 [ATL コレクション クラス](../atl/atl-collection-classes.md)  
 ATL での配列とマップの使い方について説明します。  
  
 [ATL レジストリ コンポーネント \(レジストラー\)](../atl/atl-registry-component-registrar.md)  
 ATL スクリプト構文と置き換え可能パラメーターについて説明します。  レジスタへ静的にリンクする設定方法についても説明します。  
  
 [ATL および C ランタイム コードによるプログラミング](../atl/programming-with-atl-and-c-run-time-code.md)  
 C ランタイム ライブラリ \(CRT: C Run\-Time Library\) に静的または動的にリンクすることの利点について説明します。  
  
 [CComBSTR を使用したプログラミング](../atl/programming-with-ccombstr-atl.md)  
 `CComBSTR` でのプログラミングに関する注意事項について説明します。  
  
 [エンコーディングのリファレンス](../Topic/ATL%20Encoding%20Reference.md)  
 atlenc.h の関数とマクロについて説明します。これらは、uuencode、16 進、UTF8 などの一般的なインターネット規格に含まれるエンコーディングをサポートします。  
  
 [ユーティリティのリファレンス](../Topic/ATL%20Utilities%20Reference.md)  
 [CPathT](../atl/reference/cpatht-class.md) および [CUrl](../atl/reference/curl-class.md) の形式でパスや URL を操作するためのコードについて説明します。  スレッド プール [CThreadPool](../Topic/CThreadPool%20Class.md) は、ユーザー独自のアプリケーションで使用できます。  このコードは atlpath.h および atlutil.h にあります。  
  
## 関連項目  
 [ATL のサンプル](../top/visual-cpp-samples.md)  
 ATL サンプル プログラムについて説明し、リンクを提供します。  
  
 [ATL プロジェクトの作成](../atl/reference/creating-an-atl-project.md)  
 ATL プロジェクト ウィザードに関する情報が含まれます。  
  
 [ATL コントロール ウィザード](../atl/reference/atl-control-wizard.md)  
 クラスの追加方法について説明します。  
  
 [属性付きプログラミング](../windows/attributed-programming-concepts.md)  
 属性を使用した COM プログラミングの簡略化の概要を示し、詳細なトピックへのリンクの一覧を提供します。  
  
 [ATL クラスの概要](../atl/atl-class-overview.md)  
 ATL クラスの参照情報とリンクを提供します。