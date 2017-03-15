---
title: "コントロールへのプロパティの追加 (ATL チュートリアル、パート 3) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
ms.assetid: f775fe34-103b-4f07-9999-400e987ee030
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# コントロールへのプロパティの追加 (ATL チュートリアル、パート 3)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`IPolyCtl` は、コントロールのカスタム プロパティとメソッドを含む、プロパティをそのに追加するインターフェイスです。  
  
### プロパティをプロパティの追加ウィザードを追加するには  
  
1.  クラス ビューで、多角形の分岐を展開します。  
  
2.  IPolyCtl を右クリックします。  
  
3.  ショートカット メニューのをクリック **追加**は、を **\[プロパティの追加\]**をクリックします。  
  
     プロパティの追加ウィザードが表示されます。  
  
4.  プロパティ型のドロップダウン リストで、を選択 `SHORT`。  
  
5.  **\*\*\* プロパティ名。\*\*\***として型 `[側面]`  
  
6.  プロパティの追加が終了をクリック **\[完了\]**。  
  
 インターフェイスにプロパティを追加すると、.idl ファイルをコンパイル MIDL \(プログラム\) は値を取得するための `Get` のメソッドと新しい値を設定するための `Put` のメソッドを定義します。  メソッドは、プロパティ名の `put_` と `get_` の追加によって示されます。  
  
 プロパティの追加ウィザードは、.idl ファイルに必要な行を追加します。  また、PolyCtl.h のクラス定義に `Get` と `Put` の関数プロトタイプを追加し、PolyCtl.cpp に空の実装を追加します。  PolyCtl.cpp を開き、関数 `get_Sides` と `put_Sides`を検索することによってこれをチェックできます。  
  
 これでプロパティを設定および取得するスケルトン関数がある場所が格納されていることが必要です。  プロパティを格納し、関数を適宜更新する変数を作成します。  
  
#### 変数をプロパティを格納し、設定された更新し、メソッドを取得するために作成するには  
  
1.  ソリューション エクスプローラーで、開いている PolyCtl.h は `m_clrFillColor`の定義の後に、次のコードを追加し、:  
  
     [!code-cpp[NVC_ATL_Windowing#44](../atl/codesnippet/CPP/adding-a-property-to-the-control-atl-tutorial-part-3_1.h)]  
  
2.  `m_nSides`の既定値を指定します。  PolyCtl.h のコンストラクターに行を追加すると、既定の図形に三角形をする:  
  
     [!code-cpp[NVC_ATL_Windowing#45](../atl/codesnippet/CPP/adding-a-property-to-the-control-atl-tutorial-part-3_2.h)]  
  
3.  `Get` メソッドと `Put` メソッドを実装します。  `get_Sides` と `put_Sides` の関数の宣言は PolyCtl.h に追加されました。  次のコードで `get_Sides` の PolyCtl.cpp と `put_Sides` のコードに置き換えます。:  
  
     [!code-cpp[NVC_ATL_Windowing#46](../atl/codesnippet/CPP/adding-a-property-to-the-control-atl-tutorial-part-3_3.cpp)]  
  
 `get_Sides` のメソッドは `pVal` のポインターを通じて `Sides` プロパティの現在の値を返します。  `put_Sides` のメソッドでは、コードはユーザーが指定できる値に `Sides` のプロパティを設定していることを確認します。  最小は最大値の適切な制限と 2 点の配列の両側に使用されるため、100 にする必要があります。  
  
 これ `Sides`というプロパティがあります。  次の手順では、を使用するように描画コードを変更します。  
  
 [手順 2 に戻します](../atl/adding-a-control-atl-tutorial-part-2.md) &#124; [手順 4 ~](../atl/changing-the-drawing-code-atl-tutorial-part-4.md)  
  
## 参照  
 [チュートリアル](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)