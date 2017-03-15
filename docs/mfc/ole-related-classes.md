---
title: "OLE 関連クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX クラス [C++]"
  - "OLE [C++], クラス"
  - "OLE クラス [C++]"
ms.assetid: 2135cf54-1d9d-4e0e-91b4-943b3440effa
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# OLE 関連クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これらのクラスは、複数の複数の異なるサービスをからファイル入出力に提供します。  
  
 [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md)  
 他のコンテナーから要求されたときに項目を作成するために使用します。  このクラスは `COleTemplateServer`を含むファクトリのより具体的な種類の基本クラスとして機能します。  
  
 [COleMessageFilter](../mfc/reference/colemessagefilter-class.md)  
 OLE 軽量のリモート プロシージャ コール \(LRPC\) での同時実行を管理するために使用します。  
  
 [COleStreamFile](../Topic/COleStreamFile%20Class.md)  
 COM `IStream` インターフェイスを `CFile` 複合ファイルへのアクセスを提供します。  このクラス `CFile` \(から派生\) は、MFC のシリアル化が OLE 構造化記憶を使用できるようになります。  
  
 [CRectTracker](../mfc/reference/crecttracker-class.md)  
 埋め込み先アイテムの移動、サイズ変更、および向きかえを付与するために使用します。  
  
## 参照  
 [クラスの概要](../mfc/class-library-overview.md)