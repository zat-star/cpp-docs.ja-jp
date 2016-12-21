---
title: "コントロールの実行時の動作を変更する | Microsoft Docs"
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
  - "ActiveX コントロール [C++]、実行時の動作"
ms.assetid: 78b44b0f-0d5a-4da0-8aa2-595f5789c634
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# コントロールの実行時の動作を変更する
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[コントロールを挿入](../../data/ado-rdo/inserting-the-control-into-a-visual-cpp-application.md)して 1 つ以上の[ラッパー クラス](../../data/ado-rdo/wrapper-classes.md)を生成したら、コントロールのメソッドを呼び出して、コントロールのイベント ハンドラーをプログラムすることができます。  
  
 コントロールの [ラッパー クラス](../../data/ado-rdo/wrapper-classes.md)は、コントロールの実行時の動作を変更するために使用可能な機能を指定します。 適切なラッパー クラス ヘッダー ファイルをインクルードして、メソッドを使用します。 プロパティを設定するには、プロパティ名の前に Set が付いたアクセサー メソッドを探します。 プロパティを取得するには、プロパティ名の前に Get が付いたアクセサー メソッドを探します。 イベント ハンドラーは後で作成することができます。  
  
 コントロールはオートメーションを使用して実装されるため、渡される型は BSTR や VARIANT などのオートメーション セーフな型に限られます。 BSTR および VARIANT の割り当てと設定は、システム コールを使用して実行できます。または、ATL ラッパー クラス \([CComBSTR](../../atl/reference/ccombstr-class.md)、[CComVariant](../../atl/reference/ccomvariant-class.md)\)、Visual C\+\+ の COM コンパイラがサポートするラッパー クラス \([\_bstr\_t](../../cpp/bstr-t-class.md)、[\_variant\_t](../../cpp/variant-t-class.md)\)、または MFC ラッパー クラス \([COleVariant](../../mfc/reference/colevariant-class.md)\) を使用しても実行できます。  
  
 データ コントロールを追加すると、内部データ オブジェクトを操作するために、データ コントロールのコクラスのラッパー クラスが ActiveX コントロールの挿入ウィザードによって作成されます。 ラッパー クラスは、型ライブラリで宣言されている内部オブジェクトだけを表します。RDO または ADO の全体が取り込まれるわけではありません。  
  
 ADO または RDO を直接使用するには、[\#import ディレクティブ](../../preprocessor/preprocessor-directives.md)をサポートしている[コンパイラ COM サポート クラス](../../cpp/compiler-com-support-classes.md)、または該当する SDK を使用して、ADO または RDO の DLL \(Msado15.dll または Msrdo20.dll\) に直接接続する必要があります。  
  
## 実行時にコントロール プロパティを設定するには  
 ActiveX コントロールの一部のプロパティは、実行時に読み取り専用である場合があり、動的な作成が困難です。 サポート技術情報の記事「HOWTO: Set ActiveX Control Design\-Time Properties at Run Time \(Q260744\)」で説明されているように、コントロール コンテナーの [OnAmbientPropertyChange](../Topic/COleControl::OnAmbientPropertyChange.md) ハンドラーをオーバーライドすることにより、プロパティの初期化のためにデザイン モードを一時的にシミュレートできます。 サポート技術情報の記事は、[http:\/\/support.microsoft.com\/](http://support.microsoft.com/) で参照できます。  
  
## 参照  
 [ActiveX コントロールを使用する](../Topic/Using%20ActiveX%20Controls.md)