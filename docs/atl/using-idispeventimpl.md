---
title: "IDispEventImpl の使い方 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDispEventImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDispEventImpl クラス, 使用"
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# IDispEventImpl の使い方
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

イベントを処理するために `IDispEventImpl` を使用するときに必要とする:  
  
-   [IDispEventImpl](../atl/reference/idispeventimpl-class.md)からクラスを派生します。  
  
-   クラスに [イベント シンク マップ](../Topic/BEGIN_SINK_MAP.md) を追加します。  
  
-   [SINK\_ENTRY](../Topic/SINK_ENTRY.md) または [SINK\_ENTRY\_EX](../Topic/SINK_ENTRY_EX.md) マクロを使用してイベント シンク マップにエントリを追加します。  
  
-   処理の対象となるメソッドを実装します。  
  
-   unadvise イベント ソースをお勧めします。  
  
## 例  
 次の例 **\[アプリケーション\]** Word のオブジェクトから発生した **DocumentChange** のイベントを処理する方法を示します。  このイベントは **ApplicationEvents** ディスパッチ インターフェイスのメソッドとして定義されます。  
  
 この例では [ATLEventHandling sample](../top/visual-cpp-samples.md)からです。  
  
 `[`  
  
 `uuid(000209F7-0000-0000-C000-000000000046),`  
  
 `hidden`  
  
 `]`  
  
 `dispinterface ApplicationEvents {`  
  
 `properties:`  
  
 `methods:`  
  
 `[id(0x00000001), restricted, hidden]`  
  
 `void Startup();`  
  
 `[id(0x00000002)]`  
  
 `void Quit();`  
  
 `[id(0x00000003)]`  
  
 `void DocumentChange();`  
  
 `};`  
  
 例では、Word のタイプ ライブラリから必要なヘッダー ファイルを生成するために `#import` を使用します。  Word の他のバージョンでこの例を使用する場合は、正しい mso dll ファイルを指定する必要があります。  たとえば、Office 2000 は mso9.dll を提供し、Office XP では mso.dll を提供します。  このコードは、stdafx.h から単純化されています:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/CPP/using-idispeventimpl_1.h)]  
  
 次のコードは NotSoSimple.h に表示されます。  関連するコードをコメント アウトしても表示されます:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#2](../atl/codesnippet/CPP/using-idispeventimpl_2.h)]  
  
## 参照  
 [イベント処理](../Topic/Event%20Handling%20and%20ATL.md)   
 [ATLEventHandling sample](../top/visual-cpp-samples.md)