---
title: "OLE の背景知識 : 実装の方法 | Microsoft Docs"
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
  - "アプリケーション [OLE], 実装 (OLE を)"
  - "OLE [C++], 開発方法"
  - "OLE アプリケーション [C++], 実装 (OLE を)"
ms.assetid: 0875ddae-99df-488c-82c6-164074a81058
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE の背景知識 : 実装の方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

アプリケーションによっては、OLE サポートを追加するには、次の 4 とおりの実装方法があります:  
  
-   新しいアプリケーションを作成しています。  
  
     この状況は、最小作業が必要です。  MFC アプリケーション ウィザードを実行し、スケルトン アプリケーションを作成するための高度な機能または複合ドキュメント サポートを選択します。  これらのオプションの詳細については、技術情報 [MFC EXE プログラムの作成](../Topic/MFC%20Application%20Wizard.md)を参照し、何か、します。  
  
-   OLE をサポートしない Microsoft Foundation Class ライブラリのバージョン 2.0 以降である書き込まれるプログラムがあります。  
  
     新しいアプリケーションを MFC アプリケーション ウィザードは、前に説明したように作成し、既存のアプリケーションに新しいアプリケーションからコードをコピーして貼り付けます。  これにより、サーバー、コンテナー、自動化されたアプリケーションに適しています。  この方法の例については、" MFC [Scribble](../top/visual-cpp-samples.md) サンプルを参照してください。  
  
-   OLE バージョン 1.0 のサポートを実装する Microsoft Foundation Class ライブラリのプログラムがあります。  
  
     この変換方法の [MFC のテクニカル ノート 41](../Topic/TN041:%20MFC-OLE1%20Migration%20to%20MFC-OLE%202.md) を参照してください。  
  
-   書き込まれていない Microsoft Foundation Class を使用して可能性がなく、OLE サポートを実装し、アプリケーションがあります。  
  
     この状況は、最も多くの作業が必要です。  1 番目の方法は、最初の方法では、新しいアプリケーションを作成し、そこに既存のコードをコピーして貼り付けます。  既存のコードが C で記述されている場合、このファイルを修正する必要が生じるたびに、C\+\+ コード コンパイルできます。  C コードに Windows API を呼び出すと、Microsoft Foundation Class を使用するように変更する必要はありません。  この方法は、プログラムの建て直しが Microsoft Foundation Class のバージョン 2.0 によって、より高い使用されたドキュメント\/ビュー アーキテクチャをサポートする必要があります。  このアーキテクチャの詳細については、「[テクニカル ノート 25](../mfc/tn025-document-view-and-frame-creation.md)」を参照してください。  
  
 方法を決定する、またはその両方を [コンテナー](../mfc/containers.md) または [サーバー](../mfc/servers.md) の記事を \(ユーザーが記述した種類のアプリケーションによって読み取るまたはサンプル プログラムを調べる必要があります。  MFC の OLE サンプル [OCLIENT](../top/visual-cpp-samples.md) と [HIERSVR](../top/visual-cpp-samples.md) はコンテナーとサーバーのさまざまな側面を実装する方法をそれぞれ示します。  以下の記事全体のさまざまな時点で、これらのサンプルに参照した特定の関数に説明した手法の例です。  
  
## 参照  
 [OLE の背景知識](../mfc/ole-background.md)   
 [コンテナー : コンテナーの実装](../mfc/containers-implementing-a-container.md)   
 [サーバー : サーバーの実装](../mfc/servers-implementing-a-server.md)   
 [MFC アプリケーション ウィザード](../Topic/MFC%20Application%20Wizard.md)