---
title: "Web ページ (ATL チュートリアル、パート 7) 上のコントロールの配置 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
ms.assetid: 50dc4c95-c95b-4006-b88a-9826f7bdb222
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 523086c70d9f974c014f5d33a71bf9309b8e017d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="putting-the-control-on-a-web-page-atl-tutorial-part-7"></a>Web ページへのコントロールの配置 (ATL チュートリアル、パート 7)
これで、コントロールが完成しました。 コントロールの動作を実際の環境で確認するには、Web ページに配置します。 コントロールを含む HTML ファイルは、コントロールを定義したときに作成されています。 PolyCtl.htm ファイルを開く**ソリューション エクスプ ローラー**、Web ページにコントロールを表示できます。  
  
 このステップでは、イベントに応答できるように Web ページのスクリプティングを行います。 また、コントロールのスクリプトが安全であることを Internet Explorer に通知できるように、コントロールを変更します。  
  
## <a name="scripting-the-web-page"></a>Web ページのスクリプティング  
 コントロールではまだ何も実行されないので、送られたイベントに応答できるように、Web ページを変更します。  
  
#### <a name="to-script-the-web-page"></a>Web ページをスクリプティングするには  
  
1.  PolyCtl.htm を開き、HTML ビューを選択します。 次のコードを HTML コードに追加します。 追加する場所は `</OBJECT>` の後、`</BODY>` の前です。  
  
 ```  
 
 <SCRIPT LANGUAGE="VBScript">  
 <!--  
    Sub PolyCtl_ClickIn(x, y)  
    PolyCtl.Sides = PolyCtl.Sides + 1  
    End Sub  
    Sub PolyCtl_ClickOut(x, y)  
    PolyCtl.Sides = PolyCtl.Sides - 1  
    End Sub  
 -->  
 </SCRIPT>  
 ```  
  
2.  HTM ファイルを保存します。  
  
 追加した VBScript コードでは、コントロールの内側がクリックされるとコントロールから Sides プロパティを取得して辺の数を 1 ずつ増やします。 コントロールの外側がクリックされた場合は、辺の数を 1 ずつ減らします。  
  
## <a name="indicating-that-the-control-is-safe-for-scripting"></a>コントロールのスクリプトが安全であることを示す  
 コントロールが含まれた Web ページは、Internet Explorer で表示できます。Visual C++ に組み込まれている Web ブラウザー ビューを使用すると、さらに便利です。 Web ブラウザー ビューでのコントロールを表示するには、PolyCtl.htm を右クリックし、クリックして**ブラウザーで表示**です。  
  
 Internet Explorer の現在のセキュリティ設定によっては、コントロールのスクリプトが安全ではなく、損害を被る危険性があることを示す [セキュリティの警告] ダイアログ ボックスが表示されることがあります。 たとえば、ファイルを表示するコントロールに、ファイルを削除する `Delete` メソッドも含まれている場合、このコントロールは、ページを表示するだけの場合は安全です。 ただし、`Delete` メソッドが呼び出される可能性もあるため、このコントロールのスクリプトは安全ではありません。  
  
> [!IMPORTANT]
>  このチュートリアルでは、安全としてマークされていない ActiveX コントロールを実行できるように、Internet Explorer のセキュリティ設定を変更できます。 コントロール パネルで、をクリックして**インターネット プロパティ** をクリック**セキュリティ**適切な設定を変更します。 チュートリアルを完了したら、セキュリティ設定を元の状態に戻してください。  
  
 このコントロールに関しては [セキュリティの警告] ダイアログ ボックスを表示する必要がないことを、Internet Explorer にプログラムで通知することもできます。 これを行うことができます、`IObjectSafety`インターフェイス、および ATL クラスでこのインターフェイスの実装を提供[IObjectSafetyImpl](../atl/reference/iobjectsafetyimpl-class.md)です。 このインターフェイスをコントロールに追加するには、継承するクラスのリストに `IObjectSafetyImpl` を追加し、対応するエントリを COM マップに追加します。  
  
#### <a name="to-add-iobjectsafetyimpl-to-the-control"></a>コントロールに IObjectSafetyImpl を追加するには  
  
1.  PolyCtl.h で、継承するクラスのリストの末尾に次の行を追加し、直前の行にコンマを追加します。  
  
 [!code-cpp[NVC_ATL_Windowing#62](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_1.h)]  
  
2.  PolyCtl.h の COM マップに次の行を追加します。  
  
 [!code-cpp[NVC_ATL_Windowing#63](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_2.h)]  
  
## <a name="building-and-testing-the-control"></a>コントロールのビルドとテスト  
 コントロールをビルドします。 ビルドが完了したら、PolyCtl.htm をブラウザー ビューで再度開きます。 今回は、[セキュリティの警告] ダイアログ ボックスが表示されず、Web ページが直接表示されます。 多角形の内側をクリックすると、辺の数が 1 つ増えます。 多角形の外側をクリックすると、辺の数が減ります。 辺の数を 3 未満に減らそうとすると、設定したエラー メッセージが表示されます。  
  
 [手順 6 に戻る](../atl/adding-a-property-page-atl-tutorial-part-6.md)  
  
## <a name="next-steps"></a>次の手順  
 これで ATL チュートリアルは終わりです。 ATL に関する詳細情報へのリンクを参照してください、 [ATL のスタート ページ](../atl/active-template-library-atl-concepts.md)です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル](../atl/active-template-library-atl-tutorial.md)

