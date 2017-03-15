---
title: "Web ブラウザー形式の MFC アプリケーションの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfcweb.project
dev_langs:
- C++
helpviewer_keywords:
- MFC, Web applications
- Web browsers, creating from MFC architecture
- Web browsers
- Web applications, creating
ms.assetid: 257f8c03-33c3-428c-832e-0b70aff6168d
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ccfb093a65c3f9a72b6180c4f415a92ebaf18684
ms.lasthandoff: 02/24/2017

---
# <a name="creating-a-web-browser-style-mfc-application"></a>Web ブラウザー形式の MFC アプリケーションの作成
ローカル ファイル システムとネットワーク Web ブラウザー形式のアプリケーション (HTML アクティブ ドキュメントなど)、インターネットまたはイントラネットでは、フォルダーから情報にアクセスできます。 アプリケーションのビュー クラスを派生させて[CHtmlView](../../mfc/reference/chtmlview-class.md)かつ効果的に WebBrowser コントロールにビューを提供することで、Web ブラウザー アプリケーションを作成します。  
  
### <a name="to-create-a-web-browser-application-based-on-the-mfc-documentview-architecture"></a>MFC ドキュメント/ビュー アーキテクチャに基づく Web ブラウザー アプリケーションを作成するには  
  
1.  手順に従い[MFC アプリケーションの作成](../../mfc/reference/creating-an-mfc-application.md)します。  
  
2.  MFC アプリケーション ウィザードで[アプリケーションの種類](../../mfc/reference/application-type-mfc-application-wizard.md) ページであることを確認、**ドキュメント/ビュー アーキテクチャ**ボックスをオンにします。 (いずれかを選択することができます**1 つのドキュメント**または**複数のドキュメント**、ではなく**ダイアログ ベース**)。  
  
3.  [生成されたクラス](../../mfc/reference/generated-classes-mfc-application-wizard.md) ページで、使用して、**基本クラス**を選択するドロップダウン メニュー`CHtmlView`します。  
  
4.  その他のオプションをスケルトン アプリケーションに組み込まれているを選択します。  
  
5.  **[完了]**をクリックします。  
  
 WebBrowser コントロールでは、ハイパーリンクおよびナビゲーションの Uniform Resource Locator (URL) からの Web 参照をサポートしています。 コントロールは、ユーザーが前後に参照できる履歴一覧を維持しを旧バージョンと以前に参照サイト、フォルダー、およびドキュメントです。 コントロールは、ナビゲーション、ハイパーリンク、履歴の一覧、お気に入り、およびセキュリティを直接処理します。 アプリケーションは、WebBrowser コントロールをホストのアクティブなドキュメントもへの active ドキュメント コンテナーとして使用できます。 このため、Microsoft Excel スプレッドシートなどの表現力豊かな書式設定されたドキュメントまたは Word 文書を開くし、編集が可能から WebBrowser コントロール内で。 WebBrowser コントロールが ActiveX コントロールをホストできる ActiveX コントロール コンテナーもできます。  
  
> [!NOTE]
>  WebBrowser ActiveX コントロール (したがって`CHtmlView`) はどの Internet Explorer 4.0 でのバージョンの Windows で実行されるアプリケーションでのみ使用できますか以降がインストールされています。  
  
 `CHtmlView`だけ印刷が他の Microsoft の Web ブラウザー コントロールのサポートを実装[CView](../../mfc/reference/cview-class.md)-クラスを派生します。 代わりに、WebBrowser コントロールは、印刷、プリンターのユーザー インターフェイスを実装します。 その結果、`CHtmlView`は印刷プレビューをサポートしていないと、フレームワークはその他の印刷のサポート機能を提供しません: たとえば、[き](../../mfc/reference/cview-class.md#onprepareprinting)、[値](../../mfc/reference/cview-class.md#onbeginprinting)と[CView::OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting)、ほかの MFC アプリケーションで使用可能なです。  
  
 `CHtmlView`アプリケーションは、Web または HTML ページに、参照によって、Web ブラウザー コントロール用のラッパーとして機能します。 上書きを作成、 [OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) Microsoft Visual C++ Web サイトへのナビゲーション リンクを提供するビュー クラスの関数。  
  
```  
void CWebView::OnInitialUpdate()  
{  
    CHtmlView::OnInitialUpdate();

 *// TODO: This code navigates to a popular spot on the web. *//  change the code to go where you'd like.  
    Navigate2(_T("http://www.msdn.microsoft.com/vstudio/"),
    NULL,
    NULL);

} 
```  
  
 このサイトは、独自のいずれかで置き換えることができますか、使用して、 [LoadFromResource](../../mfc/reference/chtmlview-class.md#loadfromresource)メンバー関数、ビューの既定のコンテンツとして、プロジェクトのリソースのスクリプトに存在する HTML ページを開きます。 例:  
  
```  
void CWebView::OnInitialUpdate()  
{  
    CHtmlView::OnInitialUpdate();

 *// TODO: This code navigates to a popular spot on the web. *//  change the code to go where you'd like.  
    LoadFromResource(IDR_HTML1);

} 
```  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MFCIE](http://msdn.microsoft.com/en-us/7391aa0c-fca8-4994-a6c9-6c5c7470fba0)   
 [MFC アプリケーション ウィザード](../../mfc/reference/mfc-application-wizard.md)   
 [プロジェクトのプロパティの使用](../../ide/working-with-project-properties.md)   
 [プロパティ ページ](../../ide/property-pages-visual-cpp.md)   
 [プロジェクトのプロパティの使用](../../ide/working-with-project-properties.md)   
 [アプリケーションを展開します。](http://msdn.microsoft.com/en-us/4ff8881d-0daf-47e7-bfe7-774c625031b4)


