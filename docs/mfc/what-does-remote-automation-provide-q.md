---
title: "リモート オートメーションの機能 | Microsoft Docs"
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
  - "リモート オートメーション, DCOM"
ms.assetid: 269ad218-e164-40ef-9b87-25fcc8ba21de
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# リモート オートメーションの機能
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

リモート オートメーションは、プログラムを別の 1 台のコンピューターで `IDispatch` の実装を呼び出すことができます。  また、オートメーション、特にコレクション サポートの **IEnumVARIANT** で必要なそのほかのインターフェイスをサポートしていません。  これは **IUnknown**を除き、他の COM が配布機能を提供します \(、\)、提供されず、定期的なオートメーションと同様に、オートメーションがサポートするデータ型に対してのみ、マーシャリングのサポートが含まれています。  
  
 機能のセットは、プログラムがオブジェクトのコレクションまたはアクセス可能なネットワークのノードで実行されるオブジェクトのオートメーション オブジェクトを簡単にするため、これらを使用するメソッドとプロパティにアクセスできます。  クライアント コンピューターが適切なソフトウェアを実行する場合、同じ機能を使用しないがオートメーション\) 機能を使用してクライアントにコールバックにサーバーの名前と、再度です。これは、32 ビットと 64 ビットのクライアントの場合にのみ機能し、イベントと概念的に類似しています。  
  
 リモート オートメーション サーバーとして操作できるアプリケーションの実行可能ファイルとして実装されなければなりません \(つまり、「インプロセス サーバー」ではなく「ローカル サーバーとして」\)。  
  
## 参照  
 [リモート オートメーションを使用する場合](../mfc/where-does-remote-automation-fit-in-q.md)   
 [DCOM の歴史](../mfc/history-of-dcom.md)