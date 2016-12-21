---
title: "Web ブラウザー形式の MFC アプリケーションの作成 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfcweb.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC, Web アプリケーション"
  - "Web アプリケーション, 作成"
  - "Web ブラウザー"
  - "Web ブラウザー, 作成 (MFC アーキテクチャから)"
ms.assetid: 257f8c03-33c3-428c-832e-0b70aff6168d
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Web ブラウザー形式の MFC アプリケーションの作成
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Web ブラウザー形式のアプリケーションは、インターネットの情報 \(HTML やアクティブ ドキュメントなど\) やイントラネットの情報のほか、ローカル ファイル システムとネットワーク上のフォルダーにもアクセスできます。  アプリケーションのビュー クラスを [CHtmlView](../../mfc/reference/chtmlview-class.md) から派生すると、ビューに WebBrowser コントロールが追加されるため、アプリケーションを Web ブラウザーとして使用できます。  
  
### MFC ドキュメント\/ビュー アーキテクチャに基づいて Web ブラウザー アプリケーションを作成するには  
  
1.  「[MFC アプリケーションの作成](../../mfc/reference/creating-an-mfc-application.md)」の手順に従って操作します。  
  
2.  MFC アプリケーション ウィザードの [&#91;アプリケーションの種類&#93;](../Topic/Application%20Type,%20MFC%20Application%20Wizard.md) ページの \[ドキュメント ビュー アーキテクチャ サポート\] ボックスがオンになっていることを確認します。\[シングル ドキュメント\] または \[マルチ ドキュメント\] を選択できますが、\[ダイアログ ベース\] は選択しないでください。  
  
3.  \[[生成されたクラス](../../mfc/reference/generated-classes-mfc-application-wizard.md)\] ページの \[基本クラス\] ドロップダウン メニューの \[`CHtmlView`\] を選択します。  
  
4.  スケルトン アプリケーションに組み込むほかのオプションを必要に応じて選択します。  
  
5.  \[完了\] をクリックします。  
  
 WebBrowser コントロールでは、ハイパーリンクと URL \(Uniform Resource Locator \) による Web の閲覧をサポートします。  このコントロールの履歴リストでは、参照済みのサイト、フォルダー、およびドキュメント間を前後に参照できます。  移動、ハイパーリンク、履歴リスト、お気に入り、およびセキュリティは、WebBrowser コントロールによって直接処理されます。  アプリケーションは、WebBrowser コントロールをアクティブ ドキュメント コンテナーとして使用し、アクティブ ドキュメントをホストします。  したがって、Microsoft Excel スプレッドシートや Word 文書などの書式付きドキュメントを WebBrowser コントロール内で開き、その場で編集できます。  WebBrowser コントロールは、ActiveX コントロール コンテナーとして機能することによって、ActiveX コントロールをホストすることもできます。  
  
> [!NOTE]
>  WebBrowser ActiveX コントロールと `CHtmlView` を使用するには、Internet Explorer 4.0 以降がインストールされている Windows でアプリケーションを実行する必要があります。  
  
 `CHtmlView` は Microsoft Web ブラウザー コントロールを実装するだけなので、印刷のサポートはほかの [CView](../Topic/CView%20Class.md) の派生クラスとは異なります。  WebBrowser コントロールではプリンターのユーザー インターフェイスと印刷が実装されます。  つまり、`CHtmlView` では印刷プレビューがサポートされません。また、ほかの MFC アプリケーションとは異なり、フレームワークに印刷サポート関数 [CView::OnPreparePrinting](../Topic/CView::OnPreparePrinting.md)、[CView::OnBeginPrinting](../Topic/CView::OnBeginPrinting.md)、[CView::OnEndPrinting](../Topic/CView::OnEndPrinting.md) などが用意されていません。  
  
 `CHtmlView` は Web ブラウザー コントロールのラッパー クラスとして機能し、アプリケーションに Web または HTML ページのビューを表示します。  ウィザードによって、このビュー クラスの [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) 関数がオーバーライドされ、Microsoft Visual C\+\+ Web サイトへのナビゲート リンクが用意されます。  
  
```  
void CWebView::OnInitialUpdate()  
{  
   CHtmlView::OnInitialUpdate();  
  
   // TODO: This code navigates to a popular spot on the web.  
   //  change the code to go where you'd like.  
   Navigate2(_T("http://www.msdn.microsoft.com/vstudio/"),NULL,NULL);  
}  
```  
  
 このサイトを独自のサイトに置き換えることもできます。また、メンバー関数 [LoadFromResource](../Topic/CHtmlView::LoadFromResource.md) を使用して、ビューの既定の内容として、プロジェクトのリソース スクリプトにある HTML ページを開くこともできます。  たとえば、次のようになります。  
  
```  
void CWebView::OnInitialUpdate()  
{  
   CHtmlView::OnInitialUpdate();  
  
   // TODO: This code navigates to a popular spot on the web.  
   //  change the code to go where you'd like.  
   LoadFromResource(IDR_HTML1);  
}  
```  
  
## 参照  
 [MFC Sample MFCIE](http://msdn.microsoft.com/ja-jp/7391aa0c-fca8-4994-a6c9-6c5c7470fba0)   
 [MFC アプリケーション ウィザード](../Topic/MFC%20Application%20Wizard.md)   
 [プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)   
 [プロパティ ページ](../../ide/property-pages-visual-cpp.md)   
 [プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)   
 [Deploying Applications](http://msdn.microsoft.com/ja-jp/4ff8881d-0daf-47e7-bfe7-774c625031b4)