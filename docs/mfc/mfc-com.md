---
title: "MFC COM | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MFC COM (MFC)"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Active テクノロジ [C++]"
  - "ActiveX コントロール [C++], COM オブジェクト モデル"
  - "COM [C++], MFC サポート"
  - "MFC [C++], COM サポート"
  - "MFC ActiveX コントロール [C++], COM サポート (MFC で)"
  - "MFC COM [C++]"
ms.assetid: 7646bdcb-3a06-4ed5-9386-9b00f3979dcb
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# MFC COM
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC のサブセットは COM をサポートするようにデザインされており、ATL \(Active Template Library\) の大部分は COM プログラミング用にデザインされています。  ここでは、MFC による COM のサポートについて説明します。  
  
 Active テクノロジー \(ActiveX コントロール、Active ドキュメント コンテインメント、OLE など\) は、ソフトウェア コンポーネントの開発言語に関係なく、コンポーネント オブジェクト モデル \(COM: Component Object Model\) を使ってネットワーク環境でのコンポーネント間通信を可能にする技術です。  Active テクノロジーで作成したアプリケーションは、デスクトップとインターネットの両方で実行できます。  詳細については、「[COM の概要](../atl/introduction-to-com.md)」または「[The Component Object Model](http://msdn.microsoft.com/library/windows/desktop/ms694363)」を参照してください。  
  
 Active テクノロジーは、クライアント機能とサーバー機能の両方を備えています。次は、その機能の一例です。  
  
-   [Active ドキュメント コンテインメント](../mfc/active-document-containment.md)は、MFC 4.2 以降でサポートされています。この技術を利用すると、[Active ドキュメント](../Topic/Active%20Documents.md) \(Microsoft Excel や Word ファイルなど\) を表示したり、ドキュメントのネイティブ アプリケーションのインターフェイス全体を [Active ドキュメント コンテナー](../mfc/active-document-containers.md) \(Microsoft Office バインダーや Microsoft Internet Explorer など\) のクライアント領域全体に表示したりできます。  [Active ドキュメント サーバー](../mfc/active-document-servers.md)がドキュメントを提供しているとき、コンテナーはクライアントとして動作します。  インターネット アプリケーションで Active ドキュメントを使用する方法の詳細については、「[インターネット上の Active ドキュメント](../Topic/Active%20Documents%20on%20the%20Internet.md)」を参照してください。  
  
-   ActiveX コントロールは、Web サイトなどのコンテナーで使用できるインタラクティブなオブジェクトです。  ActiveX コントロールの詳細については、以下のトピックを参照してください。  
  
    -   [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)  
  
    -   [インターネット上の ActiveX コントロール](../mfc/activex-controls-on-the-internet.md)  
  
    -   [MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)  
  
    -   [既存の ActiveX コントロールのアップグレード](../Topic/Upgrading%20an%20Existing%20ActiveX%20Control.md)  
  
    -   [ActiveX コントロールのデバッグ](../Topic/How%20to:%20Debug%20an%20ActiveX%20Control.md)  
  
-   Active スクリプトは、ActiveX コントロールの全体的な動作をブラウザーやサーバーから制御します。  Active スクリプトの詳細については、「[インターネット上の Active テクノロジ](../mfc/active-technology-on-the-internet.md)」を参照してください。  
  
-   [オートメーション](../mfc/automation.md) \(旧 OLE オートメーション\) を利用するアプリケーションは、ほかのアプリケーションで実装されているオブジェクトを操作できます。または、ほかのアプリケーションから操作できるように、オブジェクトを "公開" できます。  
  
     オートメーション オブジェクトはローカル オブジェクト、またはネットワークを経由して別のコンピューターからアクセス可能な[リモート オブジェクト](../mfc/remote-automation.md)のどちらかです。  OLE オブジェクトと COM オブジェクトは、どちらもオートメーションを利用できます。  
  
-   ここでは、MFC を使って COM コンポーネントを作成する方法についても説明します。「[コネクション ポイント](../mfc/connection-points.md)」を参照してください。  
  
 従来の OLE と新しく導入された Active テクノロジーの違いについては、[OLE](../mfc/ole-in-mfc.md) についてのトピックを参照してください。  
  
 また、サポート技術情報の「\[VC\] COM を使用した処理に長時間を要するとき \[サーバー使用中\] ダイアログ ボックスが表示されないようにする方法 \(JP248019 \)」も参照してください。  
  
## このセクションの内容  
 [Active ドキュメント コンテインメント](../mfc/active-document-containment.md)  
  
 [&#91;オートメーション&#93;](../mfc/automation.md)  
  
 [リモート オートメーション](../mfc/remote-automation.md)  
  
 [コネクション ポイント](../mfc/connection-points.md)  
  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)  
  
## 参照  
 [概念](../mfc/mfc-concepts.md)