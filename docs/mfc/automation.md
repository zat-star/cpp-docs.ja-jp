---
title: "オートメーション | Microsoft Docs"
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
  - "オートメーション サーバー, オートメーション サーバーの概要"
  - "クライアント, オートメーション"
  - "プログラム コントロール [C++]"
  - "プロパティ [MFC], オートメーション"
  - "MFC [C++], COM サポート"
  - "OLE オートメーション"
  - "オートメーション"
  - "サーバー [C++], オートメーション"
  - "オートメーション クライアント"
  - "サンプル アプリケーション [MFC], オートメーション"
  - "メソッド [MFC]"
  - "渡す (パラメーターを), オートメーション"
  - "Automation メソッド"
  - "オートメーション, 渡す (パラメーターを)"
  - "オートメーション プロパティ"
  - "MFC COM, オートメーション"
  - "メソッド [MFC], オートメーション"
ms.assetid: 329117f0-c1aa-4680-a901-bfb71277dfba
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# オートメーション
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

オートメーション \(以前の OLE オートメーション\) を使うと、アプリケーションから、他のアプリケーションに実装されているオブジェクトを操作したり、他のアプリケーションから操作できるように自分のオブジェクトを公開したりできます。  
  
 [オートメーション サーバー](../mfc/automation-servers.md)は、COM インターフェイスを通して他のアプリケーション \([オートメーション クライアント](../mfc/automation-clients.md)\) に機能を公開するアプリケーション \(一種の COM サーバー\) です。 オートメーション クライアントは、この公開を通してオブジェクトに直接アクセスし、オブジェクトが提供するサービスを使用することで、特定の機能を自動化できます。  
  
 オートメーション サーバーとオートメーション クライアントは、COM インターフェイスを使用します。COM インターフェイスは、常に `IDispatch` から派生し、オートメーション型と呼ばれる一連のデータ型を受け取ったり返したりします。 他のアプリケーションからアクセス可能なメソッドやプロパティを提供し、オートメーション インターフェイスを公開するオブジェクトはすべて自動化できます。 OLE オブジェクトと COM オブジェクトは、どちらもオートメーションを利用できます。 オブジェクトの自動化は、ローカルでもリモートでも可能です。リモートとは、ネットワークでアクセス可能な別のコンピューターにあるという意味です。つまり、オートメーションには次の 2 つのカテゴリがあります。  
  
-   オートメーション \(ローカル\)。  
  
-   [リモート オートメーション](../mfc/remote-automation.md) \(分散 COM \(DCOM\) を使用したネットワーク経由\)。  
  
 アプリケーションが他のアプリケーションでも役に立つ機能を備えている場合は、オブジェクトを公開することは有益です。 たとえば、ActiveX コントロールは一種のオートメーション サーバーで、ActiveX コントロールをホストするアプリケーションは ActiveX コントロールのオートメーション クライアントです。  
  
 ワード プロセッサから他のプログラムに公開されているスペル チェック機能も、オブジェクト公開の例です。 オブジェクトを公開すると、他のアプリケーションの既製の機能を利用できるようになるので、そのアプリケーションの機能が向上します。 このように、オートメーションは、再利用性やカプセル化などのオブジェクト指向プログラミングの原理をアプリケーション自体のレベルで利用しています。  
  
 さらに重要なのは、オートメーションがユーザーやソリューション プロバイダーに提供するサポートです。 標準的な仕様のインターフェイスを介してアプリケーションの機能を公開すると、さまざまなアプリケーション固有のマクロ言語ではなく、Microsoft Visual Basic などの単一の汎用プログラミング言語で広範なソリューションを構築できます。  
  
 Microsoft Excel、Microsoft Visual C\+\+ など、多くの商用アプリケーションでは、その機能の大部分を自動化できます。 たとえば、Visual C\+\+ では、[VBScript](vtoriVBScript) のマクロを記述することで、ビルド、コード編集、デバッグ作業などを自動化できます。  
  
##  <a name="_core_passing_parameters_in_automation"></a> オートメーションにおけるパラメーターの受け渡し  
 オートメーション メソッドの作成で問題になるのは、オートメーション サーバーとオートメーション クライアント間でデータを "安全" に受け渡すための統一したメカニズムを提供することです。 オートメーションは、**VARIANT** 型を使ってデータを渡します。**VARIANT** 型はタグ付きの共用体であり、 値を示すデータ メンバー \(C\+\+ の匿名共用体\) と、この共用体に格納されている情報の型を示すデータ メンバーを持ちます。**VARIANT** 型は、標準データ型の数、つまり 2 および 4 バイトの整数、4 および 8 バイトの浮動小数点数、文字列、およびブール値をサポートしています。 また、`HRESULT` \(OLE エラー コード\)、**CURRENCY** \(固定小数点数値型\)、**DATE** \(絶対日付と時刻\) の各型のほか、**IUnknown** インターフェイスと `IDispatch` インターフェイスへのポインターもサポートします。  
  
 **VARIANT** 型は、[COleVariant](../mfc/reference/colevariant-class.md) クラスにカプセル化されています。 サポートしている **CURRENCY** クラスと **DATE** クラスは、[COleCurrency](../Topic/COleCurrency%20Class.md) クラスと [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) クラスにカプセル化されています。  
  
## オートメーションのサンプル  
  
-   [AUTOCLIK](../top/visual-cpp-samples.md) オートメーションの手法とリモート オートメーションの基礎を学習します。  
  
-   [ACDUAL](../top/visual-cpp-samples.md) オートメーション サーバー アプリケーションにデュアル インターフェイスを追加します。  
  
-   [CALCDRIV](../top/visual-cpp-samples.md) MFCCALC を起動するオートメーション クライアント アプリケーションです。  
  
-   [INPROC](../top/visual-cpp-samples.md) インプロセス オートメーション サーバー アプリケーションの例を示します。  
  
-   [IPDRIVE](../top/visual-cpp-samples.md) INPROC を起動するオートメーション クライアント アプリケーションです。  
  
-   [MFCCALC](../top/visual-cpp-samples.md) オートメーション クライアント アプリケーションの例を示します。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [オートメーション クライアント](../mfc/automation-clients.md)  
  
-   [オートメーション サーバー](../mfc/automation-servers.md)  
  
-   [リモート オートメーション](../mfc/remote-automation.md)  
  
-   [OLE](../mfc/ole-in-mfc.md)  
  
-   [Active テクノロジ](../mfc/mfc-com.md)  
  
## 実行する操作  
  
-   [オートメーション クラスを追加する](../mfc/automation-servers.md)  
  
-   [タイプ ライブラリを使用する](../Topic/Automation%20Clients:%20Using%20Type%20Libraries.md)  
  
-   [オートメーションでパラメーターを渡す](#_core_automation_topics)  
  
-   [オートメーション サーバーにアクセスする](../mfc/automation-servers.md)  
  
-   [C\+\+ でオートメーション クライアントを記述する](../mfc/automation-clients.md)  
  
## 参照  
 [MFC COM](../mfc/mfc-com.md)