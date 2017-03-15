---
title: "マルチページ ドキュメント | Microsoft Docs"
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
  - "CPrintInfo 構造体, マルチページ ドキュメント"
  - "ドキュメント ページとプリンター ページ"
  - "ドキュメント, ページ番号付け"
  - "ドキュメント, 印刷"
  - "DoPreparePrinting メソッドとページ数チェック"
  - "マルチページ ドキュメント"
  - "OnBeginPrinting メソッド"
  - "OnDraw メソッド, 印刷"
  - "OnEndPrinting メソッド"
  - "OnPrepareDC メソッド"
  - "OnPreparePrinting メソッド"
  - "OnPrint メソッド"
  - "オーバーライド, ビュー クラスの関数 (印刷のための)"
  - "ページ, 印刷"
  - "ページ数チェック"
  - "ページ数チェック, 印刷 (マルチページ ドキュメントを)"
  - "プリンター モード"
  - "プリンター, プリンター モード"
  - "印刷 [MFC], マルチページ ドキュメント"
  - "印刷 [MFC], ページ数チェック"
  - "印刷 [MFC], プロトコル"
  - "プロトコル, 印刷 (プロトコルを)"
ms.assetid: 69626b86-73ac-4b74-b126-9955034835ef
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# マルチページ ドキュメント
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、プロトコルを印刷するウィンドウを記述し、複数のページを含むドキュメントを印刷する方法について説明します。  ここでは、次のトピックについて説明します。:  
  
-   [印刷プロトコル](#_core_the_printing_protocol)  
  
-   [オーバーライドのビュー クラスの関数](#_core_overriding_view_class_functions)  
  
-   [改ページ](#_core_pagination)  
  
-   [プリンターのページとドキュメント ページ](#_core_printer_pages_vs.._document_pages)  
  
-   [印刷時の改ページ調整](#_core_print.2d.time_pagination)  
  
##  <a name="_core_the_printing_protocol"></a> 印刷プロトコル  
 マルチページ形式のドキュメント、フレームワークとビューを次のように出力します。  最初に、フレームワークは **印刷** ダイアログ ボックスを表示し、プリンターのデバイス コンテキストを作成し、[CDC](../Topic/CDC%20Class.md) オブジェクトの [StartDoc](../Topic/CDC::StartDoc.md) メンバー関数を呼び出します。  次に、ドキュメントの各ページで、フレームワークは `CDC` オブジェクトの [StartPage](../Topic/CDC::StartPage.md) のメンバー関数を求め、ページを印刷するように、オブジェクトに送信し、[EndPage](../Topic/CDC::EndPage.md) メンバー関数を呼び出します。  プリンター モードが特定のページを開始する前に変更する必要がある場合 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) を含む構造体を新しいプリンター モード情報更新するビューは [ResetDC](../Topic/CDC::ResetDC.md)を呼び出します。  文書全体を印刷する場合、フレームワークは [EndDoc](../Topic/CDC::EndDoc.md) メンバー関数を呼び出します。  
  
##  <a name="_core_overriding_view_class_functions"></a> オーバーライドのビュー クラスの関数  
 [CView](../Topic/CView%20Class.md) クラスは印刷時にフレームワークによって、複数のメンバー関数を定義します。  ビュー クラスの関数をオーバーライドして、フレームワークの印刷ロジックとビュー クラスの印刷ロジックの間の接続を提供します。  次の表は、これらのメンバー関数の一覧です。  
  
### 印刷の CView のオーバーライドできるな関数  
  
|名前|オーバーライドの理由|  
|--------|----------------|  
|[OnPreparePrinting](../Topic/CView::OnPreparePrinting.md)|印刷ダイアログ ボックスの値を挿入するには、ドキュメントの特に期間|  
|[OnBeginPrinting](../Topic/CView::OnBeginPrinting.md)|フォントや他の GDI のリソースを割り当てます。|  
|[OnPrepareDC](../Topic/CView::OnPrepareDC.md)|デバイス コンテキストの属性を特定のページに調整したり、印刷時の改ページ調整します。|  
|[OnPrint](../Topic/CView::OnPrint.md)|特定のページを印刷するには|  
|[OnEndPrinting](../Topic/CView::OnEndPrinting.md)|GDI のリソースを解放するには|  
  
 他の関数でも出力関連の処理を行うことができますが、これらの関数は印刷プロセスを推進するものです。  
  
 次の図は印刷プロセスの手順を示し、メンバー関数を印刷する `CView` でどこに呼び出されるかを示します。  ここからは、これらの手順の多くを詳しく説明します。  印刷プロセスの追加部分は、記事 [GDI のリソースを割り当てます。](../mfc/allocating-gdi-resources.md)で説明します。  
  
 ![印刷ループ処理](../Image/vc37C71.gif "vc37C71")  
印刷ループ  
  
##  <a name="_core_pagination"></a> 改ページ  
 フレームワークは [CPrintInfo](../mfc/reference/cprintinfo-structure.md) 構造体で印刷ジョブについての詳細を格納します。  `CPrintInfo` の値の一部は改ページ調整に関係します; これらの値は、次の表に示すようにアクセスできます。  
  
### CPrintInfo に格納されている情報ページ番号  
  
|メンバー変数または<br /><br /> 関数名|参照されるページ番号|  
|-----------------------|----------------|  
|`GetMinPage`\/`SetMinPage`|ドキュメントの最初のページ|  
|`GetMaxPage`\/`SetMaxPage`|ドキュメントの最後のページ|  
|`GetFromPage`|印刷される最初のページ|  
|`GetToPage`|印刷する最後のページ|  
|`m_nCurPage`|現在印刷するページ|  
  
 ページ番号は 1 から始まります。つまり、最初に 1、0 番号が異なっています。  これらの [CPrintInfo](../mfc/reference/cprintinfo-structure.md)やそのほかのメンバーに関する詳細については、*MFC の参照を*参照します。  
  
 印刷プロセスの先頭に、フレームワークは `CPrintInfo` 構造体へのポインターを渡す [OnPreparePrinting](../Topic/CView::OnPreparePrinting.md) ビューのメンバー関数を呼び出します。  アプリケーション ウィザードは [DoPreparePrinting](../Topic/CView::DoPreparePrinting.md)を呼び出す `OnPreparePrinting` の実装、`CView`の別のメンバー関数を提供します。  `DoPreparePrinting` は 印刷ダイアログ ボックスを表示し、プリンター デバイス コンテキストを作成する関数です。  
  
 この時点で、アプリケーションはページ数がドキュメントにあるかわかりません。  これは、1 番目の数とドキュメントの最後のページで既定値 1 ~ 0xFFFF を使用します。  ページ数をドキュメントにあるかがわかっている場合は、`DoPreparePrinting`に送信する前に `OnPreparePrinting` をオーバーライドし、`CPrintInfo` 構造体の [SetMaxPage](../Topic/CPrintInfo::SetMaxPage.md) を呼び出します。  これはドキュメントの長さを指定することができます。  
  
 `DoPreparePrinting` は、印刷ダイアログ ボックスが表示されます。  これが返されると、`CPrintInfo` 構造体は、ユーザーが指定した値が含まれます。  ユーザーがページの選択範囲だけを印刷する場合、またはその印刷ダイアログ ボックスの開始と終了のページ番号を指定できます。  フレームワークは [CPrintInfo](../mfc/reference/cprintinfo-structure.md)の `GetFromPage` と `GetToPage` 関数を使用してこれらの値を取得します。  ユーザーがページ範囲を指定しない場合、フレームワークは `GetMinPage` と `GetMaxPage` を呼び出し、ドキュメント全体を印刷するためにより返される値が設定されます。  
  
 印刷されるドキュメントの各ページに対するフレームワークは、ビュー クラス、[OnPrepareDC](../Topic/CView::OnPrepareDC.md) と [OnPrint](../Topic/CView::OnPrint.md)の 2 種類のメンバー関数を呼び出して各関数に 2 個のパラメーターを渡して: `CPrintInfo` 構造体への [CDC](../Topic/CDC%20Class.md) オブジェクトへのポインターのポインター。  フレームワークが `OnPrepareDC` と `OnPrint`では、`CPrintInfo` 構造体の `m_nCurPage` メンバーの異なる値を渡すたび。  このように、フレームワークは、ページが印刷されるかビューに指示します。  
  
 [OnPrepareDC](../Topic/CView::OnPrepareDC.md) のメンバー関数は、画面の表示のために使用されます。  これはデバイス コンテキストに描画が行われる前に変更します。  `OnPrepareDC` が 印刷の同様の動作をしますが、いくつかの相違点があります: まず、`CDC` オブジェクトは画面デバイス コンテキストの代わりにプリンター デバイス コンテキストを表し、二つ目は、`CPrintInfo` オブジェクトは、2 番目のパラメーターとして渡されます。このパラメーターは `OnPrepareDC` 画面が表示されていた場合 **NULL** です\)。どのページに基づいてデバイス コンテキストに `OnPrepareDC` を印刷されるかに調整をオーバーライドします。  たとえば、ビューポートの原点とドキュメントの適切な部分が印刷されるようにクリッピング領域を移動できます。  
  
 [OnPrint](../Topic/CView::OnPrint.md) のメンバー関数は、実際のページの印刷を実行します。  印刷を実行するために、フレームワークがプリンター デバイス コンテキストの [OnDraw](../Topic/CView::OnDraw.md) を呼び出す [既定の印刷がどのように行われるか](../Topic/How%20Default%20Printing%20Is%20Done.md) またはトピックを示します。  より正確には、フレームワークは `OnDraw`に `CPrintInfo` 構造体とデバイス コンテキストの `OnPrint`、`OnPrint` のパスをデバイス コンテキスト呼び出します。  印刷時にだけ表示され、画面に表示される描画を実行するに `OnPrint` をオーバーライドします。  たとえば、ヘッダーやフッターを印刷します \(詳細については、" [ヘッダーとフッター](../mfc/headers-and-footers.md) 記事を参照してください。  その後、画面表示と印刷の両方に共通の描画を行う `OnPrint` のオーバーライドの呼び出し `OnDraw`。  
  
 `OnDraw` が画面表示と印刷の両方の描画を行うということは、アプリケーションが WYSIWYG であることを意味する: 参照する「」、What You になります。ただし、WYSIWYG アプリケーションを作成しているとします。  たとえば、画面上に太字を示す出力表示コントロール コードで太字フォントを使用してテキスト エディターを検討してください。  このような場合、画面の表示に `OnDraw` をのみ使用します。  `OnPrint`をオーバーライドすると、別の描画関数の呼び出しで `OnDraw` の呼び出しで置き換えます。  この関数はドキュメントを方法、描画して表示画面に表示されない属性を使用してフォームです。  
  
##  <a name="_core_printer_pages_vs.._document_pages"></a> プリンターのページとドキュメント ページ  
 ページ番号を参照する場合、プリンターのページの概念とドキュメント ページの概念を区別することが必要な場合があります。  プリンターの観点から見た場合、ページは 1 枚の紙です。  ただし、1 枚の紙は必ずしもドキュメントの 1 ページではありません。  たとえば、シートが圧縮ニュースレターを 1 枚の紙ドキュメントの最初と最後のページが含まれる可能性がある場合は、side\-by\-side 実行に出力します。  同様に、スプレッドシートを印刷し、ドキュメントがページからも構成されません。  代わりに、1 枚の紙は行 1 から 20 の 6 ~ 10.列を含む場合があります。  
  
 [CPrintInfo](../mfc/reference/cprintinfo-structure.md) 構造体のすべてのページ番号はプリンターのページを参照してください。  フレームワークは、プリンターを通る紙につき `OnPrepareDC` と `OnPrint` を一度呼び出されます。  ドキュメントの長さを指定するに [OnPreparePrinting](../Topic/CView::OnPreparePrinting.md) の関数をオーバーライドするときはプリンターのページを使用する必要があります。  1 対 1 の対応が \(つまり、1 個のプリンターのページは 1 のドキュメント ページに等しい\) 場合、これは簡単です。  一方、ドキュメント ページとプリンターのページが直接対応しない場合は、その中に変換する必要があります。  たとえば、スプレッドシートを印刷することをお勧めします。  `OnPreparePrinting`をオーバーライドする場合、`CPrintInfo`の `SetMaxPage` メンバー関数を呼び出すときに全体のスプレッドシートを出力し、その値を使用し、その一つ紙が必要か計算する必要があります。  同様に、オーバーライドの `OnPrepareDC`の特定シートに表示され、ビューポートの原点を適宜変更する列と行の範囲に `m_nCurPage` を変換する必要があります。  
  
##  <a name="_core_print.2d.time_pagination"></a> 印刷時の改ページ調整  
 状況によっては、ビュー クラスは実際に出力されるまでドキュメントがどの程度あるかを事前に確認できない場合があります。  たとえば印刷時にアプリケーションが WYSIWYG ではありません。したがって、画面のドキュメントの長さが期間に対応しないとします。  
  
 これは、ビュー クラスの [OnPreparePrinting](../Topic/CView::OnPreparePrinting.md) をオーバーライドすると問題が発生する: ドキュメントの長さがわからないため、[CPrintInfo](../mfc/reference/cprintinfo-structure.md) 構造体の `SetMaxPage` 関数に値を渡すことはできません。  ユーザーが印刷ダイアログ ボックスの使用で停止するページ番号を指定する印刷ループをいつ停止またはフレームワークはわかりません。  確認する唯一の方法は、印刷ループをいつ停止またはドキュメントを印刷し、終了時に参照することです。  クラス ビューはドキュメントの末尾が末尾に到達すると確認して印刷中、フレームワークを通知する必要があります。  
  
 フレームワークは、ビュー クラスの [OnPrepareDC](../Topic/CView::OnPrepareDC.md) 関数にいつ停止に指示します。  `OnPrepareDC`への呼び出しの後に、フレームワークは `m_bContinuePrinting`という `CPrintInfo` 構造体のメンバーをチェックします。  その既定値は **TRUE.**ですこの場合の間、フレームワークは印刷ループが継続されます。  これは **FALSE**に設定されている場合、フレームワークは停止します。  使用する場合の印刷時の改ページ位置の自動修正、オーバーライド `OnPrepareDC` 設定し、`m_bContinuePrinting` を実行するドキュメントの末尾に到達した **FALSE** するかどうかを確認します。  
  
 `OnPrepareDC` の既定の実装では、**FALSE** に現在のページが 1 よりも大きい場合 `m_bContinuePrinting` .を設定します。  このドキュメントは、1 ページであることをドキュメントの長さが指定されていない場合、フレームワークが使用されることを意味します。  次の 1 種類の結果は `OnPrepareDC`の基本クラス バージョンを呼び出すように注意が必要です。  `m_bContinuePrinting` が基本クラスのバージョンを呼び出した後 **TRUE** であると仮定しないでください。  
  
### さらに詳しくは次のトピックをクリックしてください  
  
-   [ヘッダーとフッター](../mfc/headers-and-footers.md)  
  
-   [GDI のリソースを割り当てます。](../mfc/allocating-gdi-resources.md)  
  
## 参照  
 [印刷](../mfc/printing.md)   
 [CView クラス](../Topic/CView%20Class.md)   
 [CDC クラス](../Topic/CDC%20Class.md)