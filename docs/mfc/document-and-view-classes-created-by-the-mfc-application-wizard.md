---
title: "MFC のアプリケーション ウィザードで作成されるドキュメント クラスとビュー クラス | Microsoft Docs"
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
  - "アプリケーション ウィザード [C++], ドキュメント/ビュー クラス (作成された)"
  - "ドキュメント クラス"
  - "ドキュメント クラス, 作成 (アプリケーション ウィザードで)"
  - "ビュー クラス, 作成 (アプリケーション ウィザードで)"
ms.assetid: 70c34a60-2701-4981-acea-c08a5787d8e6
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC のアプリケーション ウィザードで作成されるドキュメント クラスとビュー クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC アプリケーション ウィザードでは、のスケルトン ドキュメント クラスとビュー クラスを作成してプログラムの開発さい目的のクラスを構築します。  次 [それらのクラスのコマンドとメッセージ マップ](../Topic/Mapping%20Messages%20to%20Functions.md) メンバー関数は、Visual C\+\+ ソース・コード エディターを使用することもできます。  
  
 MFC アプリケーション ウィザードで作成されるドキュメント クラスは [CDocument](../Topic/CDocument%20Class.md)から派生されます。  ビュー クラスは [CView](../Topic/CView%20Class.md)から派生されます。  アプリケーション ウィザードでデータを含むファイルは、そのクラス名として指定する名前は、アプリケーション ウィザード ダイアログ ボックスで指定したプロジェクト名によって決まります。  アプリケーション ウィザードで、既定の名前を変更するには、生成されたクラス ページを使用できます。  
  
 アプリケーションに複数のドキュメント クラス、クラス ビュー、またはフレーム ウィンドウ クラスが必要な場合があります。  詳細については、「[複数のドキュメントの種類、ビュー、およびフレーム ウィンドウ](../mfc/multiple-document-types-views-and-frame-windows.md)」を参照してください。  
  
## 参照  
 [ドキュメント\/ビュー アーキテクチャ](../Topic/Document-View%20Architecture.md)