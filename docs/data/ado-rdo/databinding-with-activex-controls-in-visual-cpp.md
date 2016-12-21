---
title: "Visual C++ で ActiveX コントロールによるデータ連結を行う | Microsoft Docs"
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
  - "ActiveX コントロール [C++], データ バインド"
  - "バインド コントロール [C++], ActiveX"
  - "コントロール [C++], データ バインド"
  - "データ バインディング [C++], ActiveX コントロール"
  - "データ バインド コントロール [C++], ActiveX"
ms.assetid: afe11d2b-eefe-43ce-958d-82d3d4dee158
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Visual C++ で ActiveX コントロールによるデータ連結を行う
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

データ バインド機構を実装するには、2 種類の ActiveX コントロールを使用します。1 つはデータ コントロール、もう 1 つはデータ バインド コントロールです。  
  
 **Data コントロール**  
 データ コントロールは、データベース クエリと取得した行セットをカプセル化します。  Microsoft データ コントロールのユーザー インターフェイスは、データを繰り返し処理するためのボタンで構成されています。  Visual C\+\+ では、データ コントロールに対するデータ アクセス技術として、[ADO と RDO](../../data/ado-rdo/data-access-ado-and-rdo.md) の 2 つを使用できます。  
  
> [!IMPORTANT]
>  ADO データ コントロールと RDO データ コントロールは、以前のバージョンの Visual Studio でリリースされた使用していないテクノロジで、現在のバージョンでは使用できない可能性があります。  このセクションの情報を使用する場合は、適切なコントロールを入手するために以前のリリースの取得が必要になる場合があります。  
  
 **データ バインド コントロール**  
 データ バインド コントロールは、データを表示します。  データ バインド コントロールは、接続先のデータ コントロールからデータを受け取り、各種のユーザー インターフェイスにデータを表示します。  Visual C\+\+ アプリケーションでは、データ バインド コントロールに設定されているデータ値にも変数をバインドできます。「[CWnd::BindProperty](../Topic/CWnd::BindProperty.md)」を参照してください。  
  
 データ バインドの詳細については、以下のトピックを参照してください。  
  
-   [MFC ActiveX コントロール : ActiveX コントロールにおけるデータ バインディングの使用](../../mfc/mfc-activex-controls-using-data-binding-in-an-activex-control.md)  
  
-   [データ アクセス : ADO および RDO](../../data/ado-rdo/data-access-ado-and-rdo.md)  
  
-   [ADO データ バインド](../../data/ado-rdo/ado-databinding.md)  
  
-   [RDO データ バインド](../../data/ado-rdo/rdo-databinding.md)  
  
-   [ラッパー クラス](../../data/ado-rdo/wrapper-classes.md)  
  
-   [ActiveX コントロールのイベント ハンドラーを設定する](../../data/ado-rdo/setting-event-handlers-on-activex-controls.md)  
  
-   [エラー トラッピング](../../data/ado-rdo/error-trapping.md)  
  
-   [データ バインドの制限事項](../../data/ado-rdo/limitations-of-databinding.md)  
  
## 参照  
 [データ連結コントロール \(ADO および RDO\)](../Topic/Data-Bound%20Controls%20\(ADO%20and%20RDO\).md)