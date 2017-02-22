---
title: "CArchive オブジェクトとは | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CArchive"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アーカイブ オブジェクト [C++]"
  - "アーカイブ [C++], シリアル化の"
  - "バッファリング, シリアル化できるオブジェクト"
  - "バッファー, シリアル化できるオブジェクト"
  - "CArchive クラス, CArchive クラスの概要"
ms.assetid: 843f1825-288d-4d89-a1fa-70e1f92d9b8b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# CArchive オブジェクトとは
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CArchive` オブジェクトは作成にタイプ セーフなバッファリング能力を提供するか、`CFile` への読み取りシリアル化可能なオブジェクトを指定します。  通常 `CFile` オブジェクトは、ディスク ファイル;を表します。ただし、メモリ ファイル \(`CSharedFile` オブジェクト\) にすることができ、クリップボードを表します。  
  
 `CArchive` のオブジェクト \(のシリアル化する書き込み\) データまたはロード \(読み取り、逆シリアル化\) データ、どちらも保存されません。  `CArchive` オブジェクトの有効期間は、ファイルの書き込みオブジェクトまたはファイルからの読み取りオブジェクトによる 1 個のパスに限定されます。  したがって、データをファイルにシリアル化し、ファイルから逆シリアル化するには、`CArchive` の 2 個の連続して作成されたオブジェクトが必要です。  
  
 アーカイブがファイルにオブジェクトを保存すると、アーカイブをオブジェクトに `CRuntimeClass` の名前を追加します。  アーカイブが、個別のファイルからメモリへのオブジェクトを読み込む場合、`CObject`\-派生オブジェクトが動的にオブジェクトの `CRuntimeClass` に基づいて構築されます。  指定したオブジェクトが格納のアーカイブしてファイルに記述どおりに複数回参照される場合があります。  ただし、読み込みのアーカイブは一度だけオブジェクトを構築します。  アーカイブがどのようにオブジェクトに `CRuntimeClass` 情報をアタッチし、オブジェクトを構築する方法の詳細に [テクニカル ノート 2](../mfc/tn002-persistent-object-data-format.md)で、可能な複数の参照を考慮して送信、説明されています。  
  
 データがアーカイブをシリアル化すると、アーカイブ、バッファーがいっぱいになるまでデータを収集します。  その後、アーカイブは `CArchive` オブジェクトが指す `CFile` オブジェクトにバッファーを書き込みます。  同様に、アーカイブからデータを読み取るため、ファイル バッファーとバッファーから逆シリアル化されたオブジェクトにデータを読み込みます。  このイベントは、ハード ディスクを物理的に読み込まれる回数を減らし、アプリケーションのパフォーマンスが向上します。  
  
## 参照  
 [シリアル化 : オブジェクトのシリアル化](../Topic/Serialization:%20Serializing%20an%20Object.md)