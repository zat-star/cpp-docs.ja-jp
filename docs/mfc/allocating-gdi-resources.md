---
title: "GDI リソースの割り当て | Microsoft Docs"
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
  - "GDI オブジェクト, 割り当て (印刷時に)"
  - "印刷 [MFC], 割り当て (GDI リソースの)"
  - "リソース [MFC], 印刷"
ms.assetid: cef7e94d-5a27-4aea-a9ee-8369fc895d3a
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# GDI リソースの割り当て
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

この記事では、印刷に必要な Windows グラフィックス デバイス インターフェイス \(GDI\) オブジェクトの割り当てと割り当て解除の方法について説明します。  
  
> [!NOTE]
>  GDI\+ は Windows XP に含まれており、Windows NT 4.0 SP6、Windows 2000、Windows 98、および Windows Me の再頒布可能物として使用できます。  最新の再頒布可能パッケージをダウンロードするには、[http:\/\/www.microsoft.com\/msdownload\/platformsdk\/sdkupdate\/psdkredist.htm](http://www.microsoft.com/msdownload/platformsdk/sdkupdate/psdkredist.htm) を参照してください。  詳細については、MSDN で GDI\+ SDK ドキュメント \([http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/gdicpp\/GDIPlus\/GDIPlus.asp](http://msdn.microsoft.com/library/default.asp?url=/library/gdicpp/GDIPlus/GDIPlus.asp)\) を参照してください。  
  
 印刷の場合は、特定のフォント、ペン、またはその他の GDI オブジェクトを使用する必要があり、画面表示の場合は、その必要がないとします。  これらのオブジェクトはメモリを必要としますが、アプリケーションの起動時に割り当てるのは効率的ではありません。  アプリケーションがドキュメントを印刷していないときに、そのメモリが他の目的で必要になるかもしれません。  印刷の開始時にオブジェクトを割り当て、印刷の終了時に削除することをお勧めします。  
  
 これらの GDI オブジェクトを割り当てるには、[OnBeginPrinting](../Topic/CView::OnBeginPrinting.md) メンバー関数をオーバーライドします。  この関数は、2 つの理由でこの目的に適しています。フレームワークが各印刷ジョブの開始時に 1 回この関数を呼び出すことと、[OnPreparePrinting](../Topic/CView::OnPreparePrinting.md) とは異なり、この関数はプリンター デバイス ドライバーを表す [CDC](../Topic/CDC%20Class.md) オブジェクトにアクセスできることです。  印刷ジョブで使用するためにこれらのオブジェクトを格納しておくには、GDI オブジェクトを指すビュー クラスでメンバー変数を定義します \(たとえば、**CFont \*** メンバーなど\)。  
  
 作成した GDI オブジェクトを使用するには、[OnPrint](../Topic/CView::OnPrint.md) メンバー関数内のプリンター デバイス コンテキストで選択します。  ドキュメントの別のページで別の GDI オブジェクトが必要な場合は、[CPrintInfo](../mfc/reference/cprintinfo-structure.md) 構造体の `m_nCurPage` メンバーを調べて、対応する GDI オブジェクトを選択できます。  いくつかの連続するページで GDI オブジェクトが必要な場合は、`OnPrint` を呼び出すたびにデバイス コンテキストで選択する必要があります。  
  
 これらの GDI オブジェクトの割り当てを解除するには、[OnEndPrinting](../Topic/CView::OnEndPrinting.md) メンバー関数をオーバーライドします。  フレームワークによって、各印刷ジョブの終了時に、この関数が呼び出されます。そのため、アプリケーションが他のタスクに戻る前に、印刷に固有の GDI オブジェクトの割り当てを解除できます。  
  
## 参照  
 [印刷](../mfc/printing.md)   
 [既定の印刷プロセス](../Topic/How%20Default%20Printing%20Is%20Done.md)